---
title: Power BI のタイルを組織向けのアプリに統合する
description: タイルをアプリに統合するチュートリアルのサンプルコード
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: afed2bc87e7e358d9ba02a465c43d223f6e7cba3
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813781"
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>タイルをアプリに統合する (ユーザーがデータを所有)
REST API の呼び出しと Power BI JavaScript API を使って組織向けの Web アプリにタイルを統合する (埋め込む) 方法を説明します。

![Web アプリケーションに埋め込まれたタイル](media/integrate-tile/powerbi-embedded-tile.png)

このチュートリアルを開始するには、**Power BI** アカウントが必要です。 Power BI アカウントをお持ちでない場合、[無料で新規登録](../service-self-service-signup-for-power-bi.md)できます。あるいは、テスト目的で独自の [Azure Active Directory テナント](create-an-azure-active-directory-tenant.md)を作成できます。

> [!NOTE]
> 代わりに embedtoken を使って顧客のためにタイルを埋め込む場合は、 [顧客のためにダッシュボード、タイル、レポートをアプリケーションに統合する方法](embed-sample-for-customers.md)に関する記事をご覧ください。
> 
> 

タイルを Web アプリに統合するには、**Power BI** REST API または Power BI C# SDK と、Azure Active Directory (AD) 承認**アクセス トークン**を使って、タイルを取得します。 そして、同じアクセス トークンを使って、タイルを読み込みます。 **Power BI** API は、特定の **Power BI** リソースへのプログラムによるアクセスを提供します。 詳細については、「[Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)」(Power BI REST API) と [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) に関するページを参照してください。

## <a name="download-the-sample"></a>サンプルをダウンロードする
この記事では、GitHub の [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) で使用されているコードを示します。 このチュートリアルの手順を試してみるには、サンプルをダウンロードできます。

## <a name="step-1---register-an-app-in-azure-ad"></a>ステップ 1 - Azure AD にアプリを登録する
REST API の呼び出しを行うには、Azure AD にアプリケーションを登録する必要があります。 詳しくは、「[Azure AD アプリを登録して Power BI コンテンツを埋め込む](register-app.md)」をご覧ください。

[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) をダウンロードした場合は、登録した後で取得する**クライアント ID** と**クライアント シークレット**を使います。そうすることにより、サンプルは Azure AD で認証できるようになります。 サンプルを構成するには、*cloud.config* ファイルで**クライアント ID** と**クライアント シークレット**を変更します。

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>ステップ 2 - Azure AD からアクセス トークンを取得する
アプリケーションでは、Power BI REST API の呼び出しを行う前に、まず、Azure AD から**アクセス トークン**を取得する必要があります。 詳しくは、「[ユーザーを認証し、Power BI アプリ用の Azure AD アクセス トークンを取得する](get-azuread-access-token.md)」をご覧ください。

## <a name="step-3---get-a-tile"></a>ステップ 3 - タイルを取得する
**Power BI** タイルを取得するには、[タイルの取得](https://docs.microsoft.com/rest/api/power-bi/dashboards/gettiles)操作を使って、指定したダッシュボードから **Power BI** タイルの一覧を取得します。 タイルの一覧から、タイル ID を取得し、URL を埋め込むことができます。

タイルを取得する前に、ダッシュボード ID を取得する必要があります。 ダッシュボードを取得する方法については、「[ダッシュボードをアプリに統合する (ユーザーがデータを所有)](integrate-dashboard.md)」をご覧ください。

### <a name="get-tiles-using-an-access-token"></a>アクセス トークンを使ってタイルを取得する
[ステップ 2](#step-2-get-an-access-token-from-azure-ad) で取得した**アクセス トークン**を使って、[タイル取得](https://docs.microsoft.com/rest/api/power-bi/dashboards/gettiles)操作を呼び出すことができます。 [タイル取得](https://docs.microsoft.com/rest/api/power-bi/dashboards/gettiles)操作は、タイルの一覧を返します。 タイルの一覧から 1 つのタイルを取得できます。 タイルを取得するための完全な C# メソッドを以下に示します。 

REST API 呼び出しを行うには、*Authorization* ヘッダーを "*ベアラー {アクセス トークン}*" の形式で含める必要があります。

#### <a name="get-tiles-with-the-rest-api"></a>REST API でタイルを取得する
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>.NET SDK を使ってタイルを取得する
REST API を直接呼び出すのではなく、.NET SDK を使ってダッシュボードの一覧を取得することもできます。

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>ステップ 4 - JavaScript を使ってタイルを読み込む
JavaScript を使って、Web ページの div 要素にタイルを読み込むことができます。

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) をダウンロードして実行する場合、サンプルは次のようになります。

![Web アプリケーションに埋め込まれたタイル](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>グループの使用 (アプリ ワークスペース)
グループ (アプリ ワークスペース) からタイルを埋め込むには、次の REST API 呼び出しを使って、グループのダッシュボードで使用可能なすべてのタイルの一覧を取得する必要があります。 この REST API 呼び出しについて詳しくは、「[タイルを取得する](https://docs.microsoft.com/rest/api/power-bi/dashboards/gettiles)」をご覧ください。 要求から結果が返るようにするには、グループでのアクセス許可が必要です。

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

上記の API は、使用可能なタイルの一覧を返します。 各タイルには EmbedUrl プロパティがあり、グループの埋め込みをサポートするように既に構成されています。

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>次の手順
[タイルの埋め込み](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed) (PowerBI-JavaScript Wiki)

[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)。

[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) サンプル (GitHub)。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

