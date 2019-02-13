---
title: 認証アクセス トークンを取得する
description: データをプッシュするチュートリアル - 認証アクセス トークンを取得する
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 0840d01a53a8d1f2c19ef1d5d263bf9a3d2d8f81
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56216564"
---
# <a name="step-2-get-an-authentication-access-token"></a>手順 2:認証アクセス トークンを取得する

この記事は、チュートリアル「[データセットにデータをプッシュする](walkthrough-push-data.md)」の一部です。

チュートリアル「データセットにデータをプッシュする」の**手順 1**「[アプリを Azure AD に登録する](walkthrough-push-data-register-app-with-azure-ad.md)」では、クライアント アプリを Azure AD に登録しました。 この手順では、認証アクセス トークンを取得します。 Power BI アプリは **Azure AD** と統合されており、それによってセキュリティで保護されたサインインと承認をアプリで行うことができます。 トークンを使って **Azure AD** に対して認証を行い、Power BI リソースにアクセスします。

ここでは、認証アクセス トークンを取得する方法を説明します。

## <a name="get-an-authentication-access-token"></a>認証アクセス トークンを取得する

> **注**:作業を開始する前に、チュートリアル「[データセットにデータをプッシュする](walkthrough-push-data.md)」の前の手順を完了してください。
> 
> 

1. Visual Studio 2015 で、 **コンソール アプリケーション** プロジェクトを作成します。
2. [Azure AD Authentication Library for .NET NuGet パッケージ](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)をインストールします。 .NET アプリで認証セキュリティ トークンを取得するには、このパッケージを使います。 パッケージをインストールする方法を次に示します。

     a. Visual Studio 2015 で、**[ツール]** > **[NuGet パッケージ マネージャー]** > **[パッケージ マネージャー コンソール]** を選びます。

     b. **[パッケージ マネージャー コンソール]** で、「Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612」と入力します。
3. Program {...} クラスに、以下のコードを追加します。
4. "{ClientID}" を、アプリを登録したときに取得した **クライアント ID** で置き換えます。 「[アプリを Azure AD に登録する](walkthrough-push-data-register-app-with-azure-ad.md)」をご覧ください。
5. Microsoft.IdentityModel.Clients.ActiveDirectory パッケージをインストールした後、Program.cs に「 **using Microsoft.IdentityModel.Clients.ActiveDirectory;** 」を追加します。
6. コンソール アプリを実行し、Power BI アカウントにログインします。 コンソール ウィンドウにトークン文字列が表示されます。

**認証セキュリティ トークンを取得するサンプル コード**

このコードを Program {...} に追加します。

* 操作を呼び出すためのトークン変数。
  
  ```csharp
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* static void Main(string[] args) では、以下のように入力します。
  
  ```csharp
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* GetToken() メソッドを追加します。

```csharp
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.microsoftonline.net/common/";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

認証トークンを取得すると、任意の Power BI 操作を呼び出せます。 次の手順では、[PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) 操作を呼び出して、ダッシュボードにデータをプッシュするデータセットを作成する方法を説明します。

次の手順では、[Power BI でデータセットを作成する](walkthrough-push-data-create-dataset.md)方法について説明します。

以下は、[完全なコード リスト](#code)です。

<a name="code"/>

## <a name="complete-code-listing"></a>完全なコード リスト

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

        }

        #region Get an authentication access token
        private static string GetToken()
        {
            // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
            // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

            //The client id that Azure AD created when you registered your client app.
            string clientID = "{Client_ID}";

            //RedirectUri you used when you register your app.
            //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
            // You can use this redirect uri for your client app
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            //OAuth2 authority Uri
            string authorityUri = "https://login.microsoftonline.net/common/";

            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            // AcquireToken will acquire an Azure access token
            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            Console.WriteLine(token);
            Console.ReadLine();

            return token;
        }

        #endregion

    }
}
```

[次の手順 >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>次の手順

[Power BI でデータセットを作成する](walkthrough-push-data-create-dataset.md)  
[アプリを Azure AD に登録する](walkthrough-push-data-register-app-with-azure-ad.md)  
[Azure AD Authentication Library for .NET NuGet パッケージ](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Power BI データセットにデータをプッシュする](walkthrough-push-data.md)  
[Power BI REST API の概要](overview-of-power-bi-rest-api.md)  
[Power BI REST API リファレンス](https://docs.microsoft.com/rest/api/power-bi/)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。