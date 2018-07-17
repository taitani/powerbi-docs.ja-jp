---
title: Power BI ダッシュボード、レポート、およびタイルを埋め込む方法
description: ここでは、アプリケーション内に Power BI コンテンツを埋め込むために必要な手順について説明します。
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 8a912791777c631208ee40d37c5eaad56806ccf9
ms.sourcegitcommit: 001ea0ef95fdd4382602bfdae74c686de7dc3bd8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38924715"
---
# <a name="embed-your-power-bi-dashboards-reports-and-tiles"></a>Power BI ダッシュボード、レポート、およびタイルを埋め込む

ここでは、アプリケーション内に Power BI コンテンツを埋め込むために必要な手順について説明します。

Microsoft は [Power BI Premium を発表](https://powerbi.microsoft.com/blog/microsoft-accelerates-modern-bi-adoption-with-power-bi-premium/)しました。この新しい容量ベースのライセンス モデルは、ユーザーによるコンテンツのアクセス、共有および配布方法の柔軟性を高めます。 また、Power BI サービスのスケーラビリティとパフォーマンスが向上します。 Microsoft Azure 内に容量を作成することができる Power BI Embedded も発表されました。 Power BI Embedded はアプリケーションと顧客を対象としたものです。 

この記事では、組織向けと顧客向け両方の Power BI コンテンツの埋め込みについて説明します。 2 つのシナリオの手順は似ています。 手順が顧客向けの埋め込みに固有である場合は、その旨が記されています。

これを可能にするためにアプリケーションで実行する必要がある手順がいくつかあります。 アプリケーション内で埋め込みコンテンツを作成し、使用できるようにするために、必要な手順を順に説明します。

> [!NOTE]
> Power BI API では引き続き、アプリ ワークスペースをグループと呼びます。 したがって、グループと記述されている場合はすべて、アプリ ワークスペースを使用していることを意味します。

## <a name="step-1-setup-your-embedded-analytics-development-environment"></a>手順 1: 埋め込み分析開発環境をセットアップする

アプリケーションへのダッシュボードとレポートの埋め込みを開始する前に、埋め込めるように環境がセットアップされていることを確認する必要があります。 セットアップの一環として、以下を行う必要があります。

* [Azure Active Directory テナントがあることを確認する](embedding-content.md#azureadtenant)
* [Power BI Pro アカウントを作成する](embedding-content.md#proaccount)
* [アプリの登録とアクセス許可](embedding-content.md#appreg)
* [アプリ ワークスペースを作成する](embedding-content.md#appws)
* [レポートを作成してアップロードする](embedding-content.md#createreports)

[オンボード エクスペリエンス ツール](https://aka.ms/embedsetup)に移動し、すばやく開始してサンプル アプリケーションをダウンロードすることができます。

適切なソリューションを選択します。
* [顧客向けの埋め込み](embedding.md#embedding-for-your-customers)では、Power BI のアカウントがないユーザーのためにダッシュボードとレポートを埋め込むことができます。 [顧客向けの埋め込み](https://aka.ms/embedsetup/AppOwnsData)ソリューションを実行します。
* [組織向けの埋め込み](embedding.md#embedding-for-your-organization)を使って、Power BI サービスを拡張することができます。 [組織向けの埋め込み](https://aka.ms/embedsetup/UserOwnsData)ソリューションを実行します。

ただし、手動で環境をセットアップする場合は、以下を続行できます。 

> [!NOTE]
> アプリケーションの開発には、専用容量は必要ありません。 アプリケーションの開発者には、Power BI Pro ライセンスが必要です。

### <a name="azureadtenant"></a>Azure Active Directory テナント

Power BI からアイテムを埋め込むには、Azure Active Directory (Azure AD) テナントが必要です。 このテナントには少なくとも 1 人の Power BI Pro ユーザーが必要です。 また、テナント内で Azure AD アプリを定義する必要もあります。 既存の Azure AD テナントを利用することも、埋め込み専用に新しいものを作成することもできます。

顧客向けに埋め込む場合は、使用するテナント セットアップを決める必要があります。

* 既存の企業の Power BI テナントを使用しますか。
* アプリケーションで個別のテナントを使用しますか。
* 顧客ごとに個別のテナントを使用しますか。

既存のテナントを使用しない場合や、アプリケーション、または顧客ごとに新しいテナントを作成するよう選択できる場合は、「[Azure Active Directory テナントを作成する](create-an-azure-active-directory-tenant.md)」または「[Azure Active Directory テナントを取得する方法](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant)」を参照してください。

### <a name="proaccount"></a>Power BI Pro ユーザー アカウントを作成する

コンテンツを埋め込む場合、1 つの Power BI Pro アカウントのみが必要となります。 ただし、アイテムに固有のアクセス権を持ついくつかの異なるユーザーが必要になる場合があります。 ここでは、テナント内で考慮する必要がある可能性があるユーザーを示します。

次のアカウントはテナント内に存在し、Power BI Pro ライセンスを割り当てる必要があります。 Power BI 内でアプリ ワークスペースを使用する場合は、Power BI Pro ライセンスが必要です。

#### <a name="an-organizationtenant-admin-user"></a>組織/テナント管理者ユーザー

顧客向けの埋め込みでは、アプリケーションが使用するアカウントとして、組織/テナントのグローバル管理者ユーザーを使用しないことをお勧めします。 そうすれば、テナント内でのアプリケーション アカウントによるアクセスが最小限に抑えられます。 管理者ユーザーは、埋め込むために作成されたすべてのアプリ ワークスペースの管理者である必要があります。

#### <a name="accounts-for-analysts-that-create-content"></a>コンテンツを作成するアナリストのアカウント

複数のユーザーが Power BI のコンテンツを作成する可能性があります。 コンテンツを作成し、Power BI に配置するアナリストごとに Power BI Pro アカウントが必要です。

#### <a name="an-application-master-user-account-for-embedding-for-your-customers"></a>顧客向けの埋め込みのためのアプリケーション "*マスター*" ユーザー アカウント

マスター アカウントは、顧客向けのコンテンツ埋め込み時にアプリケーションが使用するアカウントです。 通常、このシナリオは ISV アプリケーション向けです。 組織内で必要なアカウントは、マスター アカウントだけです。 管理者およびアナリスト アカウントとしても使用できますが、お勧めできません。 アプリケーションのバックエンドには、このアカウントの資格情報が格納され、Power BI API で使用する Azure AD 認証トークンを取得するために使用されます。 このアカウントは、アプリケーションを顧客用に使用するための埋め込みトークンを生成します。

マスター アカウントは、アプリケーションで使用する Power BI Pro ライセンスを持っている通常のユーザーに過ぎません。 このアカウントは、埋め込みに使用されるアプリ ワークスペースの管理者である必要があります。

### <a name="appreg"></a> アプリの登録とアクセス許可

REST API の呼び出しを行うには、Azure AD にアプリケーションを登録する必要があります。 詳しくは、「[Azure AD アプリを登録して Power BI コンテンツを埋め込む](register-app.md)」をご覧ください。

### <a name="appws"></a>アプリ ワークスペースを作成する

顧客向けにダッシュボードとレポートを埋め込む場合は、そのダッシュボードとレポートをアプリ ワークスペース内に配置する必要があります。 前述の*マスター* アカウントは、アプリ ワークスペースの管理者である必要があります。

[!INCLUDE [powerbi-service-create-app-workspace](../includes/powerbi-service-create-app-workspace.md)]

> [!NOTE]
> 管理者以外のユーザーの場合、作成できるアプリ ワークスペースは 250 個までです。 アプリ ワークスペースをさらに作成するには、テナント管理者アカウントを使用する必要があります。
>

### <a name="createreports"></a>レポートを作成してアップロードする

Power BI Desktop を使用してレポートとデータセットを作成し、アプリ ワークスペースにこれらのレポートを発行できます。 レポートを発行するエンド ユーザーには、アプリ ワークスペースに発行するための Power BI Pro ライセンスが必要です。

## <a name="step-2-embed-your-content"></a>手順 2: コンテンツを埋め込む

アプリケーション内では、Power BI で認証する必要があります。 顧客向けのコンテンツを埋め込む場合は、アプリケーション内に*マスター* アカウントの資格情報を格納します。

> [!NOTE]
> 顧客向けの埋め込みの間にユーザーを認証する方法の詳細については、「[ユーザーを認証し、Power BI アプリ用の Azure AD アクセス トークンを取得する](get-azuread-access-token.md)」を参照してください。
>

認証を行った後、アプリケーション内で、Power BI REST API と JavaScript API を使用して、ダッシュボードとレポートをアプリケーションに埋め込みます。 

**組織向けの埋め込み**については、以下のチュートリアルをご覧ください。

* [ダッシュボードをアプリに統合する](integrate-dashboard.md)
* [タイルをアプリに統合する](integrate-tile.md)
* [レポートをアプリに統合する](integrate-report.md)

通常は ISV を対象とした**顧客向けの埋め込み**については、以下をご覧ください。

* [ダッシュボード、タイル、レポートをアプリケーションに統合する](embed-sample-for-customers.md)

顧客向けに埋め込む場合は、埋め込みトークンが必要です。 詳細については、「[Embed Token](https://docs.microsoft.com/rest/api/power-bi/embedtoken)」 (埋め込みトークン) を参照してください。

## <a name="step-3-promote-your-solution-to-production"></a>手順 3: ソリューションを運用に昇格する

運用環境に移行には、追加手順がいくつか必要です。

### <a name="embedding-for-your-organization"></a>組織向けの埋め込み

組織向けの埋め込みの場合は、アプリケーションへのアクセス方法を知らせるだけです。 

アプリ ワークスペース (グループ) が専用容量にバックアップされている場合、割り当てられているライセンスに関係なく、すべてのユーザーがそのワークスペースから埋め込まれたコンテンツを利用できます。 つまり、Power BI Pro ライセンスを所有しないすべてのユーザーにアプリ ワークスペースを明示的に追加する必要があります。そうしないと、401 の権限なしエラーが表示されます。 次の表は、Office 365 で利用可能な Power BI Premium SKU の一覧です。

| 容量ノード | 合計コア<br/>*(バックエンド + フロントエンド)* | バックエンド コア | フロントエンド コア | DirectQuery/ライブ接続の制限 | ピーク時の最大のページ レンダリング数 |
| --- | --- | --- | --- | --- | --- |
| EM3 |4 v コア |2 コア、10 GB の RAM |2 コア | |601-1,200 |
| P1 |8 v コア |4 コア、25 GB の RAM |4 コア |1 秒あたり 30 |1,201-2,400 |
| P2 |16 v コア |8 コア、50 GB の RAM |8 コア |1 秒あたり 60 |2,401-4,800 |
| P3 |32 v コア |16 コア、100 GB の RAM |16 コア |1 秒あたり 120 |4,801-9600 |

> [!NOTE]
> グローバルまたは課金管理者は、Power BI Premium を購入するには、テナント内に存在する必要があります。 Power BI Premium の購入方法については、「[Power BI Premium の購入方法](../service-admin-premium-purchase.md)」を参照してください。

>[!Note]
>[組織向けに埋め込み分析環境をセットアップします。](#step-1-setup-your-embedded-analytics-development-environment)
>

### <a name="embedding-for-your-customers"></a>顧客向けの埋め込み

顧客向けに埋め込む場合は、次のようにします。

* 開発用に個別のテナントを使う場合は、アプリ ワークスペース、ダッシュボード、およびレポートが運用環境で利用可能であることを確認する必要があります。 また、運用テナントの Azure AD でアプリケーションを作成し、手順 1 のとおり、適切なアプリにアクセス許可を割り当てたことを確認します。
* ニーズに合う容量を購入します。 以下の表を使って、必要になる可能性がある Power BI Embedded 容量の SKU を把握できます。 詳細については、「[Embedded analytics capacity planning whitepaper](https://aka.ms/pbiewhitepaper)」 (埋め込み分析の容量計画に関するホワイト ペーパー) を参照してください。 準備ができたら、[Microsoft Azure Portal](https://portal.azure.com) で購入できます。 Power BI Embedded 容量の作成方法の詳細については、「[Create Power BI Embedded capacity in the Azure portal](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity)」(Azure Portal で Power BI Embedded 容量を作成する) をご覧ください。

> [!IMPORTANT]
> 埋め込みトークンは開発テストのためのものです。そのため、Power BI マスター アカウントで生成できる埋め込みトークンの数には限りがあります。 運用環境で埋め込む場合、[容量を購入する](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical)必要があります。 専用容量が購入されている場合、埋め込みトークンの生成数には上限がありません。 「[Available Features](https://docs.microsoft.com/rest/api/power-bi/availablefeatures)」 (使用可能な機能) に移動して、使用されている無料埋め込みトークンの数を確認してください。

| 容量ノード | 合計コア<br/>*(バックエンド + フロントエンド)* | バックエンド コア | フロントエンド コア | DirectQuery/ライブ接続の制限 | ピーク時の最大のページ レンダリング数 |
| --- | --- | --- | --- | --- | --- |
| A1 |1 v コア |0.5 コア、3 GB の RAM |0.5 コア | 1 秒あたり 5 |1-300 |
| A2 |2 v コア |1 コア、5 GB の RAM |1 コア | 1 秒あたり 10 |301-600 |
| A3 |4 v コア |2 コア、10 GB の RAM |2 コア | 1 秒あたり 15 |601-1,200 |
| A4 |8 v コア |4 コア、25 GB の RAM |4 コア |1 秒あたり 30 |1,201-2,400 |
| A5 |16 v コア |8 コア、50 GB の RAM |8 コア |1 秒あたり 60 |2,401-4,800 |
| A6 |32 v コア |16 コア、100 GB の RAM |16 コア |1 秒あたり 120 |4,801-9600 |

* アプリ ワークスペースを編集し、[詳細] で専用容量にそれを割り当てます。

    ![容量にアプリ ワークスペースを割り当てる](media/embedding-content/powerbi-embedded-premium-capacity.png)

* 更新されたアプリケーションを運用環境にデプロイし、Power BI ダッシュボードとレポートの埋め込みを始めます。

>[!Note]
>[顧客向けに埋め込み分析環境をセットアップします。](#step-1-setup-your-embedded-analytics-development-environment) 
>

## <a name="admin-settings"></a>管理の設定

グローバル管理者または Power BI サービス管理者は、テナントに対し REST API を使う機能を有効または無効にできます。 Power BI 管理者は、組織全体または個々のセキュリティ グループに対してこれを設定できます。 既定では組織全体に対して有効になります。 これは [Power BI 管理ポータル](../service-admin-portal.md)から行います。

## <a name="next-steps"></a>次の手順

[Power BI で埋め込み](embedding.md)  
[Power BI に Power BI Embedded ワークスペース コレクション コンテンツを移行する方法](migrate-from-powerbi-embedded.md)  
[Power BI Premium とは](../service-premium.md)  
[Power BI Premium の購入方法](../service-admin-premium-purchase.md)  
[JavaScript API Git リポジトリ](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git リポジトリ](https://github.com/Microsoft/PowerBI-CSharp)  
[JavaScript 埋め込みサンプル](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[埋め込み分析の容量計画に関するホワイト ペーパー](https://aka.ms/pbiewhitepaper)  
[Power BI Premium ホワイト ペーパー](https://aka.ms/pbipremiumwhitepaper)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。