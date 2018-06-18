---
title: 埋め込みアプリケーションのトラブルシューティング
description: この記事では、Power BI からコンテンツを埋め込むときに発生する一般的な問題について説明します。
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: maghan
ms.openlocfilehash: ad23161985cc2721562cfdfd9128e326db887ece
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813160"
---
# <a name="troubleshooting-your-embedded-application"></a>埋め込みアプリケーションのトラブルシューティング

この記事では、Power BI からコンテンツを埋め込むときに発生する一般的な問題について説明します。

## <a name="tools-for-troubleshooting"></a>トラブルシューティングするためのツール

### <a name="fiddler-trace"></a>Fiddler のトレース

[Fiddler](http://www.telerik.com/fiddler) は、HTTP トラフィックを監視する Telerik 提供の無償ツールです。  クライアント コンピューターから Power BI API によるやり取りを確認できます。 これにより、エラーとその他の関連する情報が表示される場合があります。

![Fiddler のトレース](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>フロント エンド デバッグにはブラウザーで F12

F12 を押すと、ブラウザー内で開発者ウィンドウが起動します。 これでネットワーク トラフィックやその他の情報を見ることができます。

![F12 ブラウザー デバッグ](media/embedded-troubleshoot/browser-f12.png)

### <a name="extracting-error-details-from-power-bi-response"></a>Power BI 応答からエラーの詳細を抽出する

このコード スニペットは、HTTP 例外からエラーの詳細を抽出する方法を示しています。

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
要求 ID (およびエラーの詳細をトラブルシューティングのために) をログに記録することをお勧めします。
Microsoft サポートに連絡する際に、要求 ID を指定してください。

## <a name="app-registration"></a>アプリの登録

**アプリ登録エラー**

Azure Portal または Power BI アプリ登録ページ内のエラー メッセージは、特権が不十分であることを伝えます。 アプリケーションを登録するには、Azure AD テナントの管理者になる必要があります。または、非管理者ユーザーのアプリケーション登録を有効にする必要があります。

**新しいアプリを登録したとき、Power BI サービスが Azure Portal に表示されない**

少なくとも 1 名のユーザーを Power BI に登録する必要があります。 API 一覧に **Power BI サービス**が表示されない場合、Power BI にユーザーが登録されていません。

## <a name="rest-api"></a>REST API

**API の呼び出しで 401 が返される**

さらに調査するには、Fiddler キャプチャが必要になる場合があります。 Azure AD 内の登録済みアプリケーションに対して、必要なアクセス許可スコープがない可能性があります。 Azure Portal 内で Azure AD のアプリ登録内に必要なスコープがあることを確認します。

**API の呼び出しで 403 が返される**

さらに調査するには、Fiddler キャプチャが必要になる場合があります。 403 エラーにはいくつかの理由が考えられます。

* ユーザーが共有容量で生成できる埋め込みトークンの量を超えました。 埋め込みトークンを生成するための Azure 容量を購入し、ワークスペースをその容量に割り当てる必要があります。 「[Azure Portal での Power BI Embedded 容量の作成](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity)」をご覧ください。
* Azure AD 認証トークンの有効期限が切れています。
* 認証されたユーザーがグループ (アプリ ワークスペース) に属していません。
* 認証されたユーザーがグループ (アプリ ワークスペース) の管理者ではありません。
* Authorization ヘッダーが正しく記載されていない可能性があります。 入力ミスがないことを確認してください。

場合によっては、GenerateToken を呼び出す前にアプリケーションのバックエンドで認証トークンを更新する必要があります。

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

**有効な ID が与えられた GenerateToken が失敗する**

いくつかの理由から、有効な ID が与えられた GenerateToken が失敗することがあります。

* データセットが有効な ID に対応していない
* ユーザー名が指定されていない
* ロールが指定されていない
* DatasetId が指定されていない
* ユーザーに正しいアクセス許可が与えられていない

どれが原因か検証するには、次を試します。

* [get dataset](https://docs.microsoft.com/rest/api/power-bi/datasets) を実行します。 プロパティ IsEffectiveIdentityRequired は true ですか?
* ユーザー名はあらゆる EffectiveIdentity で必須です。
* IsEffectiveIdentityRolesRequired が true であれば、ロールが必要です。
* DatasetId はあらゆる EffectiveIdentity で必須です。
* Analysis Services の場合、マスター ユーザーをゲートウェイ管理者にする必要があります。

## <a name="data-sources"></a>データ ソース

**ISV が同じデータ ソースに対して複数の資格情報を求める**

データ ソースには、1 つのマスター ユーザーに対して 1 つの資格情報セットを与えることができます。 異なる資格情報を使用する必要がある場合、追加のマスター ユーザーを作成します。 次に、マスター ユーザーごとに異なる資格情報を割り当て、そのユーザーの Azure AD トークンを利用して埋め込みます。

## <a name="content-rendering"></a>コンテンツ レンダリング

**埋め込みコンテンツをレンダリングできない、使用できない、またはタイムアウトになる**

埋め込みトークンの有効期限が切れていないことを確認します。 埋め込みトークンの有効期限を確認し、更新してください。 詳細については、「[Refresh token using JavaScript SDK](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example)」 (JavaScript SDK を利用してトークンを更新する) を参照してください。

**レポートまたはダッシュボードが読み込まれない**

ユーザーがレポートまたはダッシュボードを表示できない場合、それが powerbi.com 内で正しく読み込まれることを確認してください。 powerbi.com 内で読み込まれない場合、レポートまたはダッシュボードがアプリケーション内で機能することはありません。

**レポートまたはダッシュボードの動きが遅い**

Power BI Desktop から、あるいは powerbi.com 内でファイルを開き、パフォーマンスがアプリケーションまたは埋め込み API の問題として除外できる範囲であることを確認します。

## <a name="onboarding-experience-tool-for-embedding"></a>埋め込み用のオンボード エクスペリエンス ツール

[オンボード エクスペリエンス ツール](https://aka.ms/embedsetup)を使って、サンプル アプリケーションをすばやくダウンロードできます。 その後、アプリケーションとサンプルを比較できます。

### <a name="prerequisites"></a>前提条件

オンボード エクスペリエンス ツールを使う前に、適切な前提条件がすべてあることを確認します。 **Power BI Pro** アカウントと **Microsoft Azure** サブスクリプションが必要です。

* **Power BI Pro** にサインアップしていない場合は、[無料の試用版にサインアップ](https://powerbi.microsoft.com/en-us/pricing/)してください。
* Azure サブスクリプションをお持ちでない場合は、始める前に[無料アカウントを作成](https://azure.microsoft.com/free/?WT.mc_id=A261C142F)してください。
* 独自の [Azure Active Directory テナント](create-an-azure-active-directory-tenant.md)のセットアップが必要です。
* [Visual Studio](https://www.visualstudio.com/) がインストールされている必要があります (バージョン 2013 以降)。

### <a name="common-issues"></a>一般的な問題

オンボード エクスペリエンス ツールを使ってテストするときに発生する可能性がある一般的な問題は次のとおりです。

#### <a name="using-the-embed-for-your-customers-sample-application"></a>顧客サンプル アプリケーションへの埋め込みの使用

**顧客向けの埋め込み**エクスペリエンスを使用している場合、*PowerBI-Developer-Samples.zip* ファイルを保存して解凍します。 その後、*PowerBI-Developer-Samples-master\App Owns Data* フォルダーを開き、*PowerBIEmbedded_AppOwnsData.sln* ファイルを実行します。

**[アクセス許可の付与]** を選ぶと ([アクセス許可の付与] ステップ)、次のエラーが発生します。

    AADSTS70001: Application with identifier <client ID> was not found in the directory <directory ID>

解決するには、ポップアップを閉じ、数秒待ってから、もう一度やり直してください。 この操作を数回繰り返す必要があるかもしれません。 アプリケーション登録プロセス完了から外部 API で使用可能になるまでの時間間隔が問題の原因です。

サンプル アプリを実行すると、次のエラー メッセージが表示されます。

    Password is empty. Please fill password of Power BI username in web.config.

このエラーは、サンプル アプリケーションに挿入されていない唯一の値がユーザー パスワードであるために発生します。 ソリューションの Web.config ファイルを開き、pbiPassword フィールドにユーザーのパスワードを入力します。

#### <a name="using-the-embed-for-your-organization-sample-application"></a>組織サンプル アプリケーションへの埋め込みの使用

**組織向けの埋め込み**エクスペリエンスを使用している場合、*PowerBI-Developer-Samples.zip* ファイルを保存して解凍します。 *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* フォルダーを開き、*pbi-saas-embed-report.sln* ファイルを実行します。

**組織向けの埋め込み**サンプル アプリを実行すると、次のエラーが発生します。

    AADSTS50011: The reply URL specified in the request does not match the reply URLs configured for the application: <client ID>

これは、Web サーバー アプリケーションに対して指定されているリダイレクト URL が、サンプルの URL と異なるためです。 サンプル アプリケーションを登録する場合は、リダイレクト URL として *http://localhost:13526/* を使います。

登録済みのアプリケーションを編集する場合は、[AAD 登録済みアプリケーション](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application)の編集方法を確認し、アプリケーションが Web API へのアクセスを提供できるようにします。

Power BI ユーザー プロファイルまたはデータを編集する場合は、[Power BI データ](https://docs.microsoft.com/en-us/power-bi/service-basic-concepts)の編集方法をご覧ください。

詳しくは、「[Power BI Embedded に関してよく寄せられる質問](embedded-faq.md)」をご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。