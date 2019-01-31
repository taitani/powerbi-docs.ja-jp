---
title: ユーザーを認証し、アプリケーション用の Azure AD アクセス トークンを取得する
description: 埋め込みの Power BI コンテンツとともに使用するため、Azure Active Directory 内にアプリケーションを登録する方法を説明します。
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 08/11/2017
ms.author: maghan
ms.openlocfilehash: f585d5a48ab38124d17110049cd7dd7d5da45164
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2019
ms.locfileid: "55428764"
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>ユーザーを認証し、Power BI アプリ用の Azure AD アクセス トークンを取得する
Power BI アプリケーション内でユーザーを認証し、REST API で使うアクセス トークンを取得する方法について説明します。

Power BI REST API を呼び出す前に、Azure Active Directory (Azure AD) の**認証アクセス トークン** (アクセス トークン) を取得する必要があります。 **アクセス トークン**は、アプリが **Power BI** のダッシュボード、タイル、レポートにアクセスするのを許可するために使われます。 Azure Active Directory の**アクセス トークン** フローの詳細については、「[Azure AD 認証コード付与フロー](https://msdn.microsoft.com/library/azure/dn645542.aspx)」を参照してください。

コンテンツの埋め込み方法により、アクセス トークンの取得方法が異なります。 この記事では、2 つの異なるアプローチを使います。

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Power BI ユーザーのアクセス トークン (ユーザーがデータを所有している場合)
この例は、ユーザーが自分の組織ログインを使って Azure AD に手動でログインする場合です。 この方法は、アクセス権があるコンテンツにアクセスする Power BI ユーザー向けのコンテンツを Power BI サービス内に埋め込む場合に使われます。

### <a name="get-an-authorization-code-from-azure-ad"></a>Azure AD から認証コードを取得する
**アクセス トークン**を取得する最初の手順は、**Azure AD** から認証コードを取得することです。 この手順を行うには、次のプロパティを持つクエリ文字列を作成して、**Azure AD** にリダイレクトします。

**認証コードのクエリ文字列**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

クエリ文字列を構築した後、**Azure AD** にリダイレクトして**認証コード**を取得します。  **認証コード** クエリ文字列を構築し、**Azure AD** にリダイレクトするための完全な C# メソッドを以下に示します。 認証コードを取得した後、**認証コード**を使って**アクセス トークン**を取得します。

redirect.aspx.cs 内で、[AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) が呼び出されてトークンが生成されます。

**認証コードの取得**

```
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.microsoftonline.net/common/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>認証コードからアクセス トークンを取得する
Azure AD から認証コードを取得しました。 **Azure AD** によって**認証コード**とともに web アプリにリダイレクトされた後、**認証コード**を使用してアクセス トークンを取得します。 次に示す C# のサンプルは、リダイレクト ページ、および default.aspx ページ用の Page_Load イベントで使うことができます。

**Microsoft.IdentityModel.Clients.ActiveDirectory** 名前空間は、[Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet パッケージから取得できます。

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

**Default.aspx**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Power BI ユーザーではないユーザーのアクセス トークン (アプリがデータを所有している場合)
このアプローチは通常、アプリがデータへのアクセスを所有している ISV タイプのアプリケーションに対して使われます。 ユーザーは必ずしも Power BI ユーザーではなく、アプリケーションがエンドユーザーの認証とアクセスを制御します。

このアプローチでは、Power BI Pro ユーザーである 1 つの "*マスター*" アカウントを使います。 このアカウントの資格情報は、アプリケーションで保存されます。 アプリケーションは、これらの保存された資格情報を使って Azure AD に対する認証を行います。 次に示すコード例は、[アプリ所有データ サンプル](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)のものです

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

**await** の使い方については、「[await (C# リファレンス)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)」をご覧ください

## <a name="next-steps"></a>次の手順
アクセス トークンを入手したので、Power BI REST API を呼び出してコンテンツを埋め込むことができます。 コンテンツの埋め込み方法について詳しくは、「[Power BI ダッシュボード、レポート、およびタイルを埋め込む方法](embed-sample-for-customers.md#embed-your-content-within-your-application)」をご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。