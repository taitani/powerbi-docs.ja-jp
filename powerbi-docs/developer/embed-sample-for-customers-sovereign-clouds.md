---
title: ソブリン クラウド顧客向けのアプリケーションに Power BI コンテンツを埋め込む
description: Power BI API を使って、Web アプリに顧客向けのダッシュボード、タイル、またはレポートを統合する (埋め込む) 方法を説明します。
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: tutorial
ms.date: 07/26/2018
ms.openlocfilehash: 2d722428ce2029ef4689e6b4bf5dfcdd208baff8
ms.sourcegitcommit: 7fb0b68203877ff01f29724f0d1761d023075445
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39255873"
---
# <a name="tutorial-embed-a-power-bi-dashboard-tile-or-report-into-your-application-for-sovereign-clouds"></a>チュートリアル: Power BI のダッシュボード、タイル、レポートをソブリン クラウド向けアプリケーションに埋め込む
顧客向けのダッシュボード、タイル、またはレポートを、Power BI .NET SDK と Power BI JavaScript API を使って Web アプリに統合する (埋め込む) 方法を説明します。 通常、これは ISV のシナリオです。

Power BI はソブリン (プライベート) クラウドもサポートしています。

次のようなソブリン クラウドがあります。

* 米国Government Community Cloud (GCC)

* U. S. Military Contractors (DoDCON)

* U. S. Military (DoD)

* Germany Cloud 向け Power BI

* China Cloud 向け Power BI

![埋め込まれたダッシュボード](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

このチュートリアルを開始するには、**Power BI** アカウントが必要です。 アカウントを設定していない場合は、ソブリン クラウドの種類に応じて、[U. S. Government Power BI アカウント](../service-govus-signup.md)、[Germany Cloud 向け Power BI アカウント](https://powerbi.microsoft.com/power-bi-germany/?ru=https%3A%2F%2Fapp.powerbi.de%2F%3FnoSignUpCheck%3D1)、または [China Cloud 向け Power BI アカウント](http://www.21vbluecloud.com/powerbi/)にサインアップすることができます。

> [!NOTE]
> 代わりに組織向けのダッシュボードを埋め込む場合は、 「[ダッシュボードを組織のアプリに統合する](integrate-dashboard.md)」をご覧ください。
>

ダッシュボードを Web アプリに統合するには、**Power BI** API、および Azure Active Directory (AD) 承認**アクセス トークン**を使って、ダッシュボードを取得します。 次に、埋め込んだトークンを使ってダッシュボードを読み込みます。 **Power BI** API では、特定の **Power BI** リソースへのプログラムによるアクセスが提供されます。 詳細については、[Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)、[Power BI .NET SDK](https://github.com/Microsoft/PowerBI-CSharp)、[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) に関するページをご覧ください。

## <a name="download-the-sample"></a>サンプルをダウンロードする
この記事では、GitHub の[顧客向けの埋め込みのサンプル](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data/PowerBIEmbedded_AppOwnsData)で使われているコードを示します。 このチュートリアルの手順を試してみるには、サンプルをダウンロードできます。

* Government Community Cloud (GCC):
    1. Cloud.config ファイルを GCCCloud.config コンテンツで上書きします。
    2. web.config ファイルの clientid (ネイティブ アプリ クライアント ID)、groupid、user (マスター ユーザー)、password を更新します。
    3. 次のように、web.config ファイルに GCC パラメーターを追加します。

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://analysis.usgovcloudapi.net/powerbi/api" />
<add key="apiUrl" value="https://api.powerbigov.us/" />
<add key="embedUrlBase" value="https://app.powerbigov.us" />
```

* Military Contractors (DoDCON):
    1. Cloud.config ファイルを TBCloud.config コンテンツで上書きします。
    2. web.config ファイルの clientid (ネイティブ アプリ クライアント ID)、groupid、user (マスター ユーザー)、password を更新します。
    3. 次のように、web.config ファイルに DoDCON パラメーターを追加します。

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://high.analysis.usgovcloudapi.net/powerbi/api" />
<add key="apiUrl" value="https://api.high.powerbigov.us/" />
<add key="embedUrlBase" value="https://app.high.powerbigov.us" />
```

* Military (DoD):
    1. Cloud.config ファイルを PFCloud.config コンテンツで上書きします。
    2. web.config ファイルの clientid (ネイティブ アプリ クライアント ID)、groupid、user (マスター ユーザー)、password を更新します。
    3. 次のように、web.config ファイルに DoDCON パラメーターを追加します。

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://mil.analysis.usgovcloudapi.net/powerbi/api" />
<add key="apiUrl" value="https://api.mil.powerbigov.us/" />
<add key="embedUrlBase" value="https://app.mil.powerbigov.us" />
```

* Germany Cloud 向け Power BI のパラメーター
    1. Cloud.config ファイルを Germany Cloud 向け Power BI コンテンツで上書きします。
    2. web.config ファイルの clientid (ネイティブ アプリ クライアント ID)、groupid、user (マスター ユーザー)、password を更新します。
    3. 次のように、web.config ファイルに Germany Cloud 向け Power BI のパラメーターを追加します。

```xml
<add key="authorityUrl" value=https://login.microsoftonline.de/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://analysis.cloudapi.de/powerbi/api" />
<add key="apiUrl" value="https://api.powerbi.de/" />
<add key="embedUrlBase" value="https://app.powerbi.de" />
```

* China Cloud 向け Power BI のパラメーター
    1. Cloud.config ファイルを [China Cloud 向け Power BI](https://github.com/Microsoft/PowerBI-Developer-Samples/blob/master/App%20Owns%20Data/PowerBIEmbedded_AppOwnsData/CloudConfigs/Power%20BI%20operated%20by%2021Vianet%20in%20China/Cloud.config) コンテンツで上書きします。
    2. web.config ファイルの clientid (ネイティブ アプリ クライアント ID)、groupid、user (マスター ユーザー)、password を更新します。
    3. web.config ファイルに China Cloud 向け Power BI のパラメーターを次のように追加します。

```xml
<add key="authorityUrl" value=https://login.chinacloudapi.cn/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://analysis.chinacloudapi.cn/powerbi/api" />
<add key="apiUrl" value="https://api.powerbi.cn/" />
<add key="embedUrlBase" value="https://app.powerbi.cn" />
```

## <a name="step-1---register-an-app-in-azure-ad"></a>ステップ 1 - Azure AD にアプリを登録する
REST API を呼び出すには、アプリケーションを Azure AD に登録する必要があります。 詳しくは、「[Azure AD アプリを登録して Power BI コンテンツを埋め込む](register-app.md)」をご覧ください。 ソブリン クラウドにはさまざまな所属があり、アプリケーションを登録するための別個の URL があります。

* Government Community Cloud (GCC) - https://app.powerbigov.us/apps 

* Military Contractors (DoDCON) - https://app.high.powerbigov.us/apps 

* Military (DoD) - https://app.mil.powerbigov.us/apps

* Germany Cloud 向け Power BI - https://app.powerbi.de/apps

* China Cloud 向け Power BI - https://app.powerbi.cn/apps

[顧客向けの埋め込みのサンプル](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)をダウンロードした場合、サンプルが Azure AD に対して認証を実行できるように、登録した後で取得する**クライアント ID** を使います。 サンプルを構成するには、*web.config* ファイルの **clientId** を変更します。


## <a name="step-2---get-an-access-token-from-azure-ad"></a>ステップ 2 - Azure AD からアクセス トークンを取得する
アプリケーション内では、Power BI REST API の呼び出しを行う前に、Azure AD から**アクセス トークン**を取得する必要があります。 詳しくは、「[ユーザーを認証し、Power BI アプリ用の Azure AD アクセス トークンを取得する](get-azuread-access-token.md)」をご覧ください。 さまざまなソブリン クラウドの所属があるので、アプリケーションのアクセス トークンを取得するための個別の URL があります。

* Government Community Cloud (GCC) - https://login.microsoftonline.com

* Military Contractors (DoDCON) - http://login.microsoftonline.us

* Military (DoD) - https://login.microsoftonline.us

* Germany Cloud 向け Power BI - https://login.microsoftonline.de

* China Cloud 向け Power BI - https://login.microsoftonline.cn

**Controllers\HomeController.cs** 内の各コンテンツ アイテム タスクで、これの例を見ることができます。

## <a name="step-3---get-a-content-item"></a>ステップ 3 - コンテンツ アイテムを取得する
Power BI コンテンツを正しく埋め込むには、いくつかの作業が必要です。 すべての手順は REST API で直接行うことができますが、サンプル アプリケーションとここの例は .NET SDK で行われています。

### <a name="create-the-power-bi-client-with-your-access-token"></a>アクセス トークンを使って Power BI クライアントを作成する
Power BI API と対話できる Power BI クライアント オブジェクトをアクセス トークンで作成します。 そのためには、AccessToken を *Microsoft.Rest.TokenCredentials* オブジェクトでラップします。

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. This is used to call the Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>埋め込むコンテンツ アイテムを取得する
Power BI クライアント オブジェクトを使って、埋め込むアイテムへの参照を取得します。 ダッシュボード、タイル、またはレポートを埋め込むことができます。 指定したワークスペースから最初のダッシュボード、タイル、またはレポートを取得する方法の例を次に示します。

このサンプルは、「[App Owns Data sample](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)」(アプリ所有データ サンプル) の **Controllers\HomeController.cs** にあります。

**ダッシュボード**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**タイル**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**レポート**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>埋め込みトークンを作成する
JavaScript API から使うことができる埋め込みトークンを生成する必要があります。 埋め込みトークンは、埋め込むアイテムに固有のものです。 つまり、Power BI コンテンツを埋め込むときは常に、そのための埋め込みトークンを新しく作成する必要があります。 使用する **accessLevel** など、詳しくは「[Embed Token](https://docs.microsoft.com/rest/api/power-bi/embedtoken)」 (埋め込みトークン) をご覧ください。

> [!IMPORTANT]
> 埋め込みトークンは開発テストのためのものです。そのため、Power BI マスター アカウントで生成できる埋め込みトークンの数には限りがあります。 運用環境で埋め込む場合、[容量を購入する](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical)必要があります。 容量を購入する場合、埋め込みトークンの生成数には上限がありません。

このサンプルは、[組織向けの埋め込みのサンプル](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)の **Controllers\HomeController.cs** にあります。

ここでは **EmbedConfig** および **TileEmbedConfig** のクラスを作成するものとします。 これらのサンプルは、**Models\EmbedConfig.cs** および **Models\TileEmbedConfig.cs** にあります。

**ダッシュボード**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**タイル**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**レポート**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```
## <a name="step-4---load-an-item-using-javascript"></a>ステップ 4 - JavaScript を使ってアイテムを読み込む
JavaScript を使用して、Web ページの div 要素にダッシュ ボードを読み込むことができます。 このサンプルでは、EmbedConfig/TileEmbedConfig モデルと、ダッシュボード、タイル、またはレポートのビューを使います。 JavaScript API の使用に関する完全なサンプルについては、「[Microsoft Power BI Embedded Sample](https://microsoft.github.io/PowerBI-JavaScript/demo)」(Microsoft Power BI Embedded のサンプル) をご覧ください。

このアプリケーションのサンプルは、[組織向けの埋め込みのサンプル](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)にあります。

**Views\Home\EmbedDashboard.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>次の手順

* GitHub でサンプル アプリケーションを入手して確認できます。 上の例はそのサンプルに基づいています。 詳細については、[組織向けの埋め込みのサンプル](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)をご覧ください。
* JavaScript API の詳細については、[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) のページを参照してください。
* Germany Cloud 向け Power BI の詳細については、「[ドイツ クラウド顧客向け Power BI のよく寄せられる質問](https://docs.microsoft.com/power-bi/service-govde-faq)」を参照してください。
* [Power BI に Power BI ワークスペース コレクション コンテンツを移行する方法](migrate-from-powerbi-embedded.md)

制限事項と考慮事項
* 現在、GCC アカウントは P および EM 容量のみをサポートします

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。
