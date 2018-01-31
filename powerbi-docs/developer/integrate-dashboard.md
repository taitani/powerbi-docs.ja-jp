---
title: "ダッシュボードを組織向けのアプリに統合する"
description: "Power BI API を使って Web アプリにダッシュボードを統合する (埋め込む) 方法を説明します。"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: maghan
ms.openlocfilehash: 36b19588d76c99cb712dc481752ebdee0c867f0d
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2018
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>ダッシュボードを組織向けのアプリに統合する
REST API の呼び出しと Power BI JavaScript API を使って組織向けの Web アプリにダッシュボードを統合する (埋め込む) 方法を説明します。

![埋め込まれたダッシュボード](media/integrate-dashboard/powerbi-embed-dashboard.png)

このチュートリアルを開始するには、**Power BI** アカウントが必要です。 Power BI アカウントをお持ちでない場合、[無料で新規登録](../service-self-service-signup-for-power-bi.md)できます。あるいは、テスト目的で独自の [Azure Active Directory テナント](create-an-azure-active-directory-tenant.md)を作成できます。

> [!NOTE]
> 代わりに embedtoken を使って顧客のためにダッシュボードを埋め込む場合は、 [顧客のためにダッシュボード、タイル、レポートをアプリケーションに統合する方法](embed-sample-for-customers.md)に関する記事をご覧ください。
> 
> 

ダッシュボードを Web アプリに統合するには、**Power BI** REST API または Power BI C# SDK と、Azure Active Directory (AD) 承認**アクセス トークン**を使って、ダッシュボードを取得します。 そして、同じアクセス トークンを使って、ダッシュボードを読み込みます。 **Power BI** API は、特定の **Power BI** リソースへのプログラムによるアクセスを提供します。 詳しくは、「[Power BI REST API の概要](https://msdn.microsoft.com/library/dn877544.aspx)」と「[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)」(Power BI の JavaScript API) をご覧ください。

## <a name="download-the-sample"></a>サンプルをダウンロードする
この記事では、GitHub の [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) で使用されているコードを示します。 このチュートリアルの手順を試してみるには、サンプルをダウンロードできます。

## <a name="step-1---register-an-app-in-azure-ad"></a>ステップ 1 - Azure AD にアプリを登録する
REST API の呼び出しを行うには、Azure AD にアプリケーションを登録する必要があります。 詳しくは、「[Azure AD アプリを登録して Power BI コンテンツを埋め込む](register-app.md)」をご覧ください。

[ダッシュボード統合サンプル](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)をダウンロードした場合は、サンプルが Azure AD で認証を受けられるように、登録後に取得する**クライアント ID** と**クライアント シークレット**を使います。 サンプルを構成するには、*cloud.config* ファイルで**クライアント ID** と**クライアント シークレット**を変更します。

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>ステップ 2 - Azure AD からアクセス トークンを取得する
アプリケーションでは、Power BI REST API の呼び出しを行う前に、まず、Azure AD から**アクセス トークン**を取得する必要があります。 詳しくは、「[ユーザーを認証し、Power BI アプリ用の Azure AD アクセス トークンを取得する](get-azuread-access-token.md)」をご覧ください。

## <a name="step-3---get-a-dashboard"></a>ステップ 3 - ダッシュボードを取得する
**Power BI** ダッシュボードを取得するためには、[ダッシュボードを取得する](https://msdn.microsoft.com/library/mt465739.aspx)操作を使用して、**Power BI** ダッシュボードの一覧を表示します。 ダッシュボードの一覧から、ダッシュボード ID を取得できます。

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>アクセス トークンを使ってダッシュボードを取得する
[ステップ 2](#step-2-get-an-access-token-from-azure-ad) で取得した**アクセス トークン**を使って、[ダッシュボード取得](https://msdn.microsoft.com/library/mt465739.aspx)操作を呼び出すことができます。 [ダッシュボードを取得する](https://msdn.microsoft.com/library/mt465739.aspx)操作によって、ダッシュボードの一覧が返されます。 ダッシュボードの一覧から 1 つのダッシュボードを取得できます。 ダッシュボードを取得するための完全な C# メソッドを以下に示します。 

REST API 呼び出しを行うには、*Authorization* ヘッダーを "*ベアラー {アクセス トークン}*" の形式で含める必要があります。

#### <a name="get-dashboards-with-the-rest-api"></a>REST API を使ってダッシュボードを取得する
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>.NET SDK を使ってダッシュボードを取得する
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
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>ステップ 4 - JavaScript を使用してダッシュボードを読み込む
JavaScript を使用して、Web ページの div 要素にダッシュ ボードを読み込むことができます。

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

[ダッシュボードの統合サンプル](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)をダウンロードして実行した場合、サンプルは次のようになります。

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>タイル クリック イベント
上記のサンプルでお気づきかもしれませんが、ダッシュボード上でタイルがクリックされた場合にイベントを処理することができます。 イベントの詳細については、「[Handling Events within the JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events)」 (JavaScript API 内でのイベントの処理) をご覧ください。

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

[ダッシュボードの統合サンプル](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app)をダウンロードして実行した場合、タイルをクリックすると、ダッシュボードの下にテキストが出力されます。 そのテキストは次のようなものです。 この場合だと、タイルがクリックされたことをログに記録し、ユーザーを適切な場所にナビゲートすることができます。

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>グループの使用 (アプリ ワークスペース)
グループ (アプリ ワークスペース) からダッシュボードを埋め込むには、次の REST API 呼び出しを使って、グループで使用可能なすべてのダッシュボードの一覧を取得する必要があります。 この REST API 呼び出しについて詳しくは、「[ダッシュボードを取得する](https://msdn.microsoft.com/library/mt465739.aspx)」をご覧ください。 要求から結果が返るようにするには、グループでのアクセス許可が必要です。

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

上記の API は、使用可能なダッシュボードの一覧を返します。 各ダッシュボードには EmbedUrl プロパティがあり、グループの埋め込みをサポートするように既に構成されています。

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>制限事項
* 埋め込まれたダッシュボードにアクセスするエンド ユーザーは、Power BI アカウントを持ち、ダッシュボードにアクセスできる必要があります。 ダッシュ ボードを所有しているか、他のユーザーからダッシュボードの共有を受けている必要があります。
* 現在、埋め込まれたダッシュボードでは Q&A はサポートされていません。
* 一時的な制限として、ダッシュボードをセキュリティ グループと共有するときは、ユーザーは最初に PowerBI.com でダッシュボードにアクセスする必要があります。その後でないと、ダッシュボードは表示されません。

## <a name="next-steps"></a>次の手順
GitHub でサンプル アプリケーションを入手して確認できます。 上の例はそのサンプルに基づいています。 詳細については、「[integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)」をご覧ください。

JavaScript API の詳細については、「[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)」(Power BI の JavaScript API) をご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

