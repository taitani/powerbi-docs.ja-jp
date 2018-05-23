---
title: Power BI レポートを組織向けのアプリに統合する
description: Power BI API を使って Web アプリにレポートを統合する (埋め込む) 方法を説明します。
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 10/05/2017
ms.author: maghan
ms.openlocfilehash: d2fa65587fdbd85aabd429d531b79e9e614d2f49
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>レポートを組織向けのアプリに統合する
REST API の呼び出しと Power BI JavaScript API を使って組織向けの Web アプリにレポートを統合する (埋め込む) 方法を説明します。

![埋め込まれたレポートのサンプル](media/integrate-report/powerbi-embedded-report.png)

このチュートリアルを開始するには、**Power BI** アカウントが必要です。 Power BI アカウントをお持ちでない場合、[無料で新規登録](../service-self-service-signup-for-power-bi.md)できます。あるいは、テスト目的で独自の [Azure Active Directory テナント](create-an-azure-active-directory-tenant.md)を作成できます。

> [!NOTE]
> 代わりに embedtoken を使って顧客向けのレポートを埋め込む場合は、 [顧客のためにダッシュボード、タイル、レポートをアプリケーションに統合する方法](embed-sample-for-customers.md)に関する記事をご覧ください。
> 
> 

レポートを Web アプリに統合するには、**Power BI** REST API または Power BI C# SDK と、Azure Active Directory (AD) 承認**アクセス トークン**を使って、レポートを取得します。 そして、同じアクセス トークンを使って、レポートを読み込みます。 **Power BI** API は、特定の **Power BI** リソースへのプログラムによるアクセスを提供します。 詳しくは、「[Power BI REST API の概要](https://msdn.microsoft.com/library/dn877544.aspx)」と「[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)」(Power BI の JavaScript API) をご覧ください。

## <a name="download-the-sample"></a>サンプルをダウンロードする
この記事では、GitHub の [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) で使用されているコードを示します。 このチュートリアルの手順を試してみるには、サンプルをダウンロードできます。

## <a name="step-1---register-an-app-in-azure-ad"></a>ステップ 1 - Azure AD にアプリを登録する
REST API の呼び出しを行うには、Azure AD にアプリケーションを登録する必要があります。 詳しくは、「[Azure AD アプリを登録して Power BI コンテンツを埋め込む](register-app.md)」をご覧ください。

[integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) をダウンロードした場合は、登録した後で取得する**クライアント ID** と**クライアント シークレット**を使います。そうすることにより、サンプルは Azure AD で認証できるようになります。 サンプルを構成するには、*cloud.config* ファイルで**クライアント ID** と**クライアント シークレット**を変更します。

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>ステップ 2 - Azure AD からアクセス トークンを取得する
アプリケーションでは、Power BI REST API の呼び出しを行う前に、まず、Azure AD から**アクセス トークン**を取得する必要があります。 詳しくは、「[ユーザーを認証し、Power BI アプリ用の Azure AD アクセス トークンを取得する](get-azuread-access-token.md)」をご覧ください。

## <a name="step-3---get-a-report"></a>ステップ 3 - レポートを取得する
**Power BI** レポートを取得するには、[レポートの取得](https://msdn.microsoft.com/library/mt634543.aspx)操作を使用して、**Power BI** レポートの一覧を取得します。 レポートの一覧から、レポート ID を取得できます。

### <a name="get-reports-using-an-access-token"></a>アクセス トークンを使ってレポートを取得する
[ステップ 2](#step-2-get-an-access-token-from-azure-ad) で取得した**アクセス トークン**を使って、[レポート取得](https://msdn.microsoft.com/library/mt634543.aspx)操作を呼び出すことができます。 [レポートを取得する](https://msdn.microsoft.com/library/mt634543.aspx)操作により、レポートの一覧が返されます。 レポートの一覧から 1 つのレポートを取得できます。 レポートを取得するための完全な C# メソッドを以下に示します。 

REST API 呼び出しを行うには、*Authorization* ヘッダーを "*ベアラー {アクセス トークン}*" の形式で含める必要があります。

#### <a name="get-reports-with-the-rest-api"></a>REST API でレポートを取得する
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>.NET SDK を使ってレポートを取得する
REST API を直接呼び出すのではなく、.NET SDK を使ってレポートの一覧を取得することもできます。

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>ステップ 4 - JavaScript を使ってレポートを読み込む
JavaScript を使って、Web ページの div 要素にレポートを読み込むことができます。

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

[integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) をダウンロードして実行する場合、サンプルは次のようになります。

![埋め込まれたレポートのサンプル](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>グループの使用 (アプリ ワークスペース)
グループ (アプリ ワークスペース) からレポートを埋め込むには、次の REST API 呼び出しを使って、グループのダッシュボードで使用可能なすべてのレポートの一覧を取得する必要があります。 この REST API 呼び出しについて詳しくは、「[レポートを取得する](https://msdn.microsoft.com/library/mt634543.aspx)」をご覧ください。 要求から結果が返るようにするには、グループでのアクセス許可が必要です。

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

上記の API は、使用可能なレポートの一覧を返します。 各レポートには EmbedUrl プロパティがあり、グループの埋め込みをサポートするように既に構成されています。

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>次の手順
GitHub でサンプル アプリケーションを入手して確認できます。 詳細については、「[integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)」をご覧ください。

JavaScript API の詳細については、「[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)」(Power BI の JavaScript API) をご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

