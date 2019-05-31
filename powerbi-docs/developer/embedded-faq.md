---
title: Power BI Embedded に関してよく寄せられる質問
description: Power BI Embedded についてよく寄せられる質問とその回答の一覧です。
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 1bdc31d550573b926d45776307b8fcade95f0dc0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222168"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Power BI Embedded に関してよく寄せられる質問

* 他の質問がある場合は、[Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。
* それでも解決しない場合は、 [Power BI のサポート ページ](https://powerbi.microsoft.com/support/)をご覧ください。

## <a name="general"></a>全般

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded とは何ですか?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md)に独自のデータの視覚エフェクトと最初からコントロールを構築することがなく、アプリケーションに魅力的で完全にインタラクティブなレポートを埋め込むことができます。

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Power BI Embedded の対象者は誰ですか?

開発者やソフトウェア企業では、アプリケーションのコーディングとも呼ばれる独立系ソフトウェア ベンダー (Isv)。

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded と Power BI サービスの違いは何ですか?

Power BI は、サービスとしてのソフトウェアの分析ソリューションです。組織はその最も重要なビジネス データを 1 つのビューで見ることができます。

Microsoft は、意思決定分析、顧客を支援するためにアプリケーションにビジュアルを埋め込む必要がある isv 向けの Power BI Embedded 開発しました。 Isv が少なくて済みます自体が独自の分析ソリューションを構築する必要がなくなります。 [埋め込み分析](embedding.md)ビジネス ユーザー ビジネス データにアクセスし、アプリケーション内でのインサイトを生成することに対してクエリを実行できます。


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium と Power BI Embedded の違いは何ですか?

Power BI Premium は、容量が、組織、パートナー、顧客、およびサプライヤーの 1 つのビューを提供する包括的な BI ソリューションを望む企業向けです。 Power BI Premium は組織の意思決定に役立ちます。 Power BI Premium とは、ユーザーがモバイル アプリ、社内で開発されたアプリは、または、Power BI ポータルでコンテンツを利用できる、SaaS 製品です。

Power BI Embedded は、アプリケーションにビジュアルの埋め込みを希望する Isv 用です。 Power BI Embedded はアプリケーション開発者向けであり、そのアプリケーションを入手すれば、組織の内外を問わず、誰でも Power BI Embedded 容量に保存されているコンテンツを利用できます。Power BI Embedded は顧客の意思決定に役立ちます。 Power BI Embedded を共有することはできません 1 回のクリックによって容量コンテンツを Web に公開やワンクリック SharePoint に発行します。

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Power BI Premium と Power BI Embedded を比較して、どのような状況でどちらを購入するべきか、Microsoft は勧めていますか?

企業が、エンタープライズ グレードのセルフ サービス クラウド BI ソリューションに、Power BI Premium を購入することをお勧めします。 Isv がその埋め込み分析のクラウドを利用したコンポーネントの Power BI Embedded の購入をお勧めします。 ただし、顧客は購入する製品の制限がありません。

場合によっては、ISV (通常、大規模な)、アプリを埋め込む、に加えてが P SKU を使用して、組織内で事前にパッケージされた Power BI サービスの他の利点を取得する必要がある可能性があります。 基幹業務アプリケーションを開発し、それに分析を埋め込みたいが、事前パッケージ済み Power BI サービスは必要としない企業が Azure の A SKU の利用を決める場合もあります。

### <a name="how-many-embed-tokens-can-i-create"></a>埋め込みトークンはいくつ作成できますか?

埋め込む PRO ライセンスのトークンは開発テスト用、Power BI マスター アカウント、または[サービス プリンシパル](embed-service-principal.md)のみ限定された数のトークンを生成できます。 運用環境で埋め込むには、[容量を購入](#technical)してください。 埋め込みトークンは、容量を購入するときに生成できますが数に制限はありません。 現在の埋め込み使用パーセンテージを示す使用状況の値を確認するには、[使用可能な機能](https://docs.microsoft.com/rest/api/power-bi/availablefeatures)に関するページに移動します。

## <a name="technical"></a>技術的な質問

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Azure の A SKU と Office 365 の EM SKU の違いは何ですか?

PowerBI.com は、ソーシャル コラボレーションや電子メールのサブスクリプションの機能などの多くの機能を備えたサービス (SaaS) ソリューションとして、エンタープライズ ソフトウェアです。 PowerBI.com では、Isv、埋め込み分析ソリューションのコンテンツを管理し、テナント レベルの設定は役立ちます。

Power BI Embedded では、プラットフォームは開発者の Api のセットのサービス (PaaS) として、埋め込み分析ソリューションの作成に使用できます。

機能の相違点の一覧の一部を次に示します。

| 特性 | Power BI Embedded | Power BI Premium 容量 | Power BI Premium 容量 |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A SKU) | (EM SKU) | (P SKU) |
| Power BI アプリ ワークスペースからアーティファクトを埋め込む | Azure 容量 | Office 365 容量 | Office 365 容量 |
| 埋め込みアプリケーションで Power BI レポートを使用する | はい | はい | はい |
| SharePoint で Power BI レポートを利用する | いいえ | はい | はい |
| Dynamics で Power BI レポートを利用する | いいえ | はい | はい |
| Teams で Power BI レポートを利用する (モバイル アプリを除く) | いいえ | はい | はい |
| Powerbi.com と Power BI モバイルで無料 Power BI ライセンスでコンテンツにアクセスする | いいえ | いいえ | はい |
| MS Office アプリに埋め込まれている無料 Power BI ライセンスでコンテンツにアクセスする | いいえ | はい | はい |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI では現在、埋め込み用に 3 つの SKU を用意しています。A SKU、EM SKU、P SKU です。 私のシナリオでは、どちらを購入するべきですか?

|  |A SKU (Power BI Embedded)  |EM SKU (Power BI Premium)  |P SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|購入  |Azure Portal |Office |Office |
|ユース ケース | 独自のアプリケーションにコンテンツを埋め込む | <li> 独自のアプリケーションにコンテンツを埋め込む <br><br><br> <li> MS Office アプリケーションにコンテンツを埋め込む: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (モバイル アプリを除く)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> 独自のアプリケーションにコンテンツを埋め込む <br><br><br> <li> MS Office アプリケーションにコンテンツを埋め込む: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (モバイル アプリを除く)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br><br> <li> [Power BI サービス](https://powerbi.microsoft.com/)経由で Power BI ユーザーとコンテンツを共有する  |
|課金 |1 時間ごと |月単位 |月単位 |
|コミットメント  |コミットメントなし |年単位  |月単位/年単位 |
|差別化 |柔軟性に優れ、Azure Portal で、あるいは API 経由でリソースを拡大縮小したり、停止/再開したりできる  |SharePoint Online と Microsoft Teams の (モバイル アプリを除く) にコンテンツを埋め込むを使用することができます。 |アプリケーションの埋め込みを結合し、同じ容量で Power BI Service を使用する |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Azure で PBIE 容量を作成するための前提条件は何ですか?

* 組織のディレクトリ (Microsoft アカウントはサポートされていません) にサインインします。
* Power BI テナントを設定する必要がある、ディレクトリ内の少なくとも 1 つのユーザーが Power BI のサインアップは、します。 
* 組織のディレクトリに Azure サブスクリプションを用意する必要があります。

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Power BI Embedded の容量の消費はどのように監視できますか?

* [Power BI 管理ポータル](../service-admin-portal.md#power-bi-embedded)を使用します。

* Power BI で [metric app](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) をダウンロードします。

* [Azure 診断ログ](azure-pbie-diag-logs.md)を使用します。

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>アプリの使用量に調整することができます、容量を自動的にスケールしますか。

自動スケーリングを今すぐ行われませんが、すべての Api は、いつでも拡大縮小できます。

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>容量を作成、拡張、再開すると、容量が中断状態になります。なぜでしょうか?

容量のプロビジョニングが (scale/再開/作成) が失敗する可能性があります。 詳細の取得 API を使用すると、容量の ProvisioningState を確認してください。[Capacities - Get Details](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails) を使用します。

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>Power BI Embedded 容量は、特定のリージョンのみでしか使用できませんか?

[Multi-geo (プレビュー)](embedded-multi-geo.md) 機能では、Power BI ホーム テナントの場所とは異なるリージョンで [Power BI Embedded 容量](azure-pbie-create-capacity.md)を購入できます。

### <a name="how-can-i-find-my-pbi-tenant-region"></a>自分の PBI のテナントのリージョンを検出する方法はありますか

PBI のポータルを使用するには、PBI のテナントのリージョンが見つかりません。

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > Power BI について

![Power BI について](media/embedded-faq/about-01.png)
![テナント リージョン](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>クラウド ソリューション プロバイダー (CSP) チャネルのサポートをしますか。

* サブスクリプションの種類が CSP の場合、ご自身のテナントに対して PBIE を作成できます。
* パートナー アカウントは顧客テナントにサインインし、顧客テナントの代わりに PBIE を購入し、Power BI 容量の管理者として顧客テナント ユーザーを指定できます。

### <a name="why-do-i-get-an-unsupported-account-message"></a>アカウントがサポートされていませんというメッセージを受け取るのはなぜですか?

Power BI では、組織のアカウントでサインアップすることが求められます。 Microsoft アカウントを使用して Power BI にサインアップしようとすることはサポートされていません。

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>作成し、Azure の容量を管理する Api を使用できますか。

はいは Powershell コマンドレットと Azure Resource Manager REST Api が PBIE リソースを作成および管理を使用することができます。

* [Rest Api](https://docs.microsoft.com/rest/api/power-bi-embedded/)
* [Powershell コマンドレット](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>PBI Embedded ソリューションでは、PBI Embedded 専用容量はどのような役割を果たしますか?

[ソリューションを運用環境に昇格](embed-sample-for-customers.md#move-to-production)アプリケーションで使用する Power BI コンテンツ (アプリ ワークスペース) を Power BI Embedded (A SKU) の容量に割り当てる必要があります。

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>どのような Azure リージョンで PBI Embedded は利用できますか。

[PAM](https://ecosystemmanager.azurewebsites.net/home) (EcoManager) - Product Availability Manager を参照してください

利用できるリージョン (16 - Power BI と同じリージョン)

* 米国 (6) - 米国東部、米国東部 2、米国中北部、米国中南部、米国西部、米国西部 2
* ヨーロッパ (2) - 北ヨーロッパ、西ヨーロッパ
* アジア太平洋 (2) - 東南アジア、東アジア
* ブラジル (1) - ブラジル南部
* 日本 (1) - 東日本
* オーストラリア (1) - オーストラリア南東部
* インド (1) - インド西部
* カナダ (1) - カナダ中部
* 英国 (1) - 英国南部

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>Power BI Embedded の認証モデルとは何ですか。

マスター ユーザー (指定された Power BI Pro のライセンス ユーザー) 認証、または Azure AD を使用する Power BI Embedded は引き続き[サービス プリンシパル](embed-service-principal.md)Power BI 内でアプリケーションを認証するためです。  

 ISV は、独自の認証と承認用のアプリケーションに実装できます。

Azure AD テナントが既にある場合は、既存のディレクトリを使用できます。 作成することも、新しい埋め込みアプリケーション コンテンツ セキュリティのための Azure AD テナント。

AAD トークンを取得するには、[Azure Active Directory 認証ライブラリ](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries)のいずれかを使用できます。 複数のプラットフォームで利用可能なクライアント ライブラリがあります。

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>私はアプリケーションのユーザー認証に AAD を既に使用しています。 "ユーザーがデータを所有する" シナリオでは、Power BI に認証するとき、この ID をどのように利用できますか?

標準の OAuth の on-behalf-of フロー (<https://docs.microsoft.com/azure/active-directory/develop/web-api>)。 Power BI サービス (必要なスコープ) のアクセス許可を必要とするアプリケーションを構成する必要があります。 ユーザー アクセスを使用して、ADAL の API AcquireTokenAsync を呼び出すユーザー トークンをアプリにすると、単にし、そのリソース ID として、Power BI リソース URL を指定します。

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>オブジェクト ID は、サービス プリンシパル オブジェクト ID ですか。

*オブジェクト ID*登録済みのアプリのメイン画面からは、アプリのオブジェクト ID。

ID がで検出されたオブジェクト、*管理されているローカル ディレクトリ内のアプリケーション > プロパティ*セクションは、サービス プリンシパル オブジェクト ID を使用する必要があります。 このオブジェクト ID が操作のサービス プリンシパルを参照する、または id。 サービス プリンシパル オブジェクトを変更する など、サービス プリンシパルを管理者としてワークスペースに適用します。

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded とその他の Azure サービスの違いは何ですか?

Power BI Embedded で Azure を購入する前に、Power BI アカウントが必要です。 Power BI Embedded の展開されているお住まいの地域では、Power BI アカウントを決定します。 Azure の Power BI Embedded リソースを次の目的で管理します。

* 拡大/縮小
* 容量管理者の追加
* サービスの一時停止/再開

PowerBI.com を利用し、Power BI Embedded 容量のワークスペースの割り当て/割り当て解除を行います。

### <a name="what-are-the-supported-deploy-regions"></a>リージョンをデプロイするとは、サポートされているか。

オーストラリア南東部、ブラジル南部、カナダ中央、米国東部 2、インド西部、東日本、米国中北部、北ヨーロッパ、米国中南部、東南アジア、英国南部、西ヨーロッパ、米国西部、米国西部 2 です。

### <a name="what-content-pack-data-types-can-you-embed"></a>コンテンツ パック データ型を埋め込むことができますか。

*できません*埋め込む**ダッシュ ボード**と**タイル**コンテンツ パックのデータセットから構築します。 ただし、する*できます*埋め込む**レポート**コンテンツ パックのデータセットから構築します。

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>行レベル セキュリティ (RLS) vs の使用方法の違いとはJavaScript のフィルターの違いは何ですか?

多くの場合、混乱 1 つの方法が何を制御する方法では、JavaScript のフィルターと RLS を使用する特定のユーザーが表示できる、あり、その他のユーザーのビューを最適化する方法。

RLS の場合、ISV の開発者が、モデルの作成と埋め込みトークンの生成の一部として、データのフィルター処理を制御します。 エンド ユーザーには、ISV によって表示が許可されているもののみが表示されます。 この場合、ユーザーはフィルター処理されているものより少なく表示することはできますが、RLS の構成をバイパスして許可されているものよりも多く表示することはできません。

クライアント側フィルター処理 (JavaScript)、ISV は、最初のビューで、エンドユーザーが表示されることができますが、エンドユーザーは、ビュー自体に適用される可能性の変更を制御することはできません。 Javascript クライアント コードをユーザーには、データ バックエンドでフィルター処理をトリガーできる、のでとは見なされませんセキュリティで保護します。

詳細については、[RLS と JavaScript のフィルター](embedded-row-level-security.md#using-rls-vs-javascript-filters)に関するページをご覧ください。

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>Power BI では、どのような方法でサービス プリンシパルのアクセス許可を管理しますか?

有効にすると[サービス プリンシパル](embed-service-principal.md)で Power BI を使用するアプリケーションの AD のアクセス許可が反映されないできなくなります。 アプリケーションのアクセス許可はその後、Power BI 管理ポータルを介して管理されます。

サービス プリンシパルは、対象セキュリティ グループの Power BI テナントのすべての設定のアクセス許可を継承します。 アクセス許可を制限するサービス プリンシパルの専用のセキュリティ グループを作成し、追加、**特定のセキュリティ グループを除く**関連する、有効な Power BI の設定の一覧。

このような状況は、新しいワークスペースに**管理者**としてサービス プリンシパルを追加するときに問題となります。 このタスクは [API](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser) または Power BI サービスを使用して管理できます。

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>アプリケーション ID とサービス プリンシパル オブジェクト ID はそれぞれどのような状況で使用しますか?

**[アプリケーション ID](embed-sample-for-customers.md#application-id)** は、認証のためにアプリケーション ID を渡すときに、アクセス トークンを作成する目的で使用されます。

ワークスペースに管理者としてサービス プリンシパルを適用するなど、サービス プリンシパルを各種操作または変更のために参照するには、 **[サービス プリンシパル オブジェクト ID](embed-service-principal.md#how-to-get-the-service-principal-object-id)** を使用します。

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>サービス プリンシパルでオンプレミス データ ゲートウェイを管理できますか?

マスター アカウントの場合のようにオンプレミス データ ゲートウェイ (データ ゲートウェイ) を管理することは、[サービス プリンシパル](embed-service-principal.md)ではできません。

マスター アカウントを利用すれば、データ ゲートウェイをインストールし、そのゲートウェイにユーザーを追加したり、データ ソースに接続したり、その他の管理タスクを実行したりできます。

サービス プリンシパルを利用すれば、SQL Server Analysis Services (SSAS) オンプレミス ライブ接続データ ソースを使用し、[行レベルセキュリティ (RLS)](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal-preview) を構成できます。 サービス プリンシパルを使用して **Power BI Embedded** と統合するとき、SSAS でユーザーとデータへのユーザー アクセスをこの方法で管理できます。

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>サービス プリンシパルで Power BI サービスにサインインできますか?

いいえ - サービス プリンシパルを使用して Power BI にサインインすることはできません。

また、埋め込みトークンの生成時のみ、外部アプリケーション (SaaS 埋め込み) でユーザーとしてコンテンツを利用できません。

### <a name="what-are-the-best-practices-to-improve-performance"></a>パフォーマンスを向上するベスト プラクティスについては、次を参照してください。

[Power BI Embedded のパフォーマンス](embedded-performance-best-practices.md)

## <a name="licensing"></a>ライセンス

### <a name="how-do-i-purchase-power-bi-embedded"></a>Power BI Embedded の購入方法は?

Power BI Embedded は Azure からお買い求めいただけます。

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>Power BI Premium を既に購入したが、いくつか Power BI Embedded Azure の特典でどうなるか

お客様の現在の契約期間が終わるまで、既存の Power BI Premium の購入の支払いに続行してから、その時点では、可能性があります、Power BI Premium の購入に応じて。

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Power BI Embedded にアクセスするには Power BI Premium を購入する必要がありますか?

いいえ。Power BI Embedded には、ソリューションをデプロイし、顧客に配信するために必要な Azure ベースの容量が含まれています。

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Power BI Embedded の購入コミットメントは何ですか?

顧客は時間単位で使用方法を変更できます。 Power BI Embedded サービスの月額または年額コミットメントはありません。

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Power BI Embedded の使用状況は請求書にどのように表示されますか?

Power BI Embedded は、デプロイしたノードの種類に基づき、予測可能な時間レートで課金されます。 使用状況が存在しない場合でも、あなたのリソースは、アクティブな場合に限りは課金されます。 課金を停止するようにリソースを一時停止する必要があります。

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Power BI Embedded に Power BI Pro のライセンスを必要とするのはどのようなユーザーですか? また、その理由は?

Power BI Pro ライセンスが必要または[サービス プリンシパル](embed-service-principal.md)REST Api を使用します。 レポートを Power BI ワークスペースに追加するにアナリストが必要か、Power BI Pro ライセンスまたはサービス プリンシパルです。 Power BI テナントと容量を管理する管理者が必要な Power BI Pro ライセンスを取得します。

Power BI Embedded では Power BI ポータルの使用を管理および埋め込みコンテンツを検証するため、ために、レポートへのアクセス、正しいリポジトリで PowerBI.com 内でアプリを認証する Power BI Pro ライセンスが必要です。

ただし、自分のアプリケーション内で[埋め込みレポートを作成または編集する](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View)場合、エンド ユーザーは Power BI ユーザーである必要がないため、Pro ライセンスは必要ありません。

### <a name="can-i-get-started-for-free"></a>無料で始めることはできますか?

はい。Power BI Embedded の [Azure クレジット](https://azure.microsoft.com/free/)をご利用いただけます。

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Azure で Power BI Embedded を試してみることはできますか?

サービスを使用することは Power BI Embedded には Azure の一部であるため、 [200 ドルのクレジットを Azure にサインアップするときに受信した](https://azure.microsoft.com/free/)します。

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>Power BI Embedded は国内クラウド (米国政府、ドイツ、中国) に利用できますか?

Power BI Embedded が可能な[国内クラウド](embed-sample-for-customers-national-clouds.md)します。

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>非営利団体や教育機関は Power BI Embedded を利用できますか?

特殊な Azure の非営利団体や教育機関のエンティティの料金はありません。

## <a name="power-bi-workspace-collection"></a>Power BI ワークスペース コレクション

### <a name="what-is-power-bi-workspace-collection"></a>Power BI ワークスペース コレクションとは何ですか?

**Power BI ワークスペース コレクション**(**Power BI Embedded**バージョン 1) ソリューションに基づいて、 **Power BI ワークスペース コレクション**Azure リソースです。 このソリューションを利用すると、**Power BI ワークスペース コレクション** ソリューションの下にある Power BI コンテンツ、専用 API、および Power BI に対してアプリケーションを認証するワークスペース コレクション キーを使って、顧客向けの **Power BI Embedded** アプリケーションを作成できます。

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Power BI ワークスペース コレクションから Power BI Embedded に移行できますか?

1. 移行ツールを使って、**Power BI ワークスペース コレクション**のコンテンツを Power BI に複製できます https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration。

2. Power BI のコンテンツを使用する **Power BI Embedded** アプリケーション POC から始めます。

3. 運用する準備ができたら、**Power BI Embedded** の専用容量を購入し、その容量に Power BI のコンテンツ (ワークスペース) を割り当てます。

    > [!Note]
    > **Power BI Embedded** ソリューションを使って開発を行いながら、並行して **Power BI ワークスペース コレクション**を使い続けることができます。 準備ができたら、顧客を新しい **Power BI Embedded** ソリューションに移動し、**Power BI ワークスペース コレクション** ソリューションの使用を終了します。

詳しくは、「[Power BI Embedded に Power BI ワークスペース コレクション コンテンツを移行する方法](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)」をご覧ください。

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>Power BI ワークスペース コレクションと非推奨となるパスには

はい。 ただし、既に使用しているお客様、、 **Power BI ワークスペース コレクション**ソリューションは、非推奨となるまで使用し続けることができます。 お客様は、新しいワークスペース コレクション、および **Power BI ワークスペース コレクション** ソリューションをまだ使用する **Power BI Embedded** アプリケーションを作成することもできます。

ただし、これも意味の新機能は、いずれかに追加されていない**Power BI ワークスペース コレクション**ソリューション。 新しいへの移行を計画に活かしてまいります**Power BI Embedded**ソリューション。

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Power BI ワークスペース コレクションのサポートはいつ終了しますか?

既に **Power BI ワークスペース コレクション** ソリューションを使っているお客様は、2018年 6 月末まで、またはサポート契約が終了するまで、引き続き使用できます。

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>PBI ワークスペース コレクションはどのリージョンで作成できますか。

使用できるリージョンは、オーストラリア南東部、ブラジル南部、カナダ中部、米国東部 2、東日本、米国中北部、北ヨーロッパ、米国中南部、東南アジア、英国南部、西ヨーロッパ、インド西部、米国西部です。

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>PBI ワークスペース コレクションから Power BI Embedded に移行しなければならないのはなぜですか?

いくつか新しい**Power BI Embedded**ソリューションの機能と機能を使用して行うことはできません**Power BI ワークスペース コレクション**します。

次のような機能です。
* PBI のすべてのデータ ソースがサポートされています。 2 つだけ**Power BI ワークスペース コレクション**データ ソースがサポートされています。 
* Q&A、更新、ブックマーク、ダッシュボードとタイルの埋め込み、カスタム メニューなどの新機能は、**Power BI Embedded** ソリューションでのみサポートされます。
* 容量の課金モデル。

## <a name="embedding-setup-tool"></a>埋め込みセットアップ ツール

### <a name="what-is-the-embedding-setup-tool"></a>埋め込みのセットアップ ツールとは

[埋め込みのセットアップ ツール](https://aka.ms/embedsetup)を使うと、サンプル アプリケーションを簡単にダウンロードして Power BI で埋め込みを開始することができます。

### <a name="which-solution-should-i-choose"></a>選択するソリューション

* [顧客向けの埋め込み](embedding.md#embedding-for-your-customers)では、Power BI のアカウントがないユーザーのためにダッシュボードとレポートを埋め込むことができます。 [顧客向けの埋め込み](https://aka.ms/embedsetup/AppOwnsData)ソリューションを実行します。
* [組織向けの埋め込み](embedding.md#embedding-for-your-organization)を使って、Power BI サービスを拡張することができます。 [組織向けの埋め込み](https://aka.ms/embedsetup/UserOwnsData)ソリューションを実行します。

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>ダウンロードしたサンプル アプリのどのソリューションを選択するか

**顧客向けの埋め込み**エクスペリエンスを使用している場合、*PowerBI-Developer-Samples.zip* ファイルを保存して解凍します。 その後、*PowerBI-Developer-Samples-master\App Owns Data* フォルダーを開き、*PowerBIEmbedded_AppOwnsData.sln* ファイルを実行します。

**組織向けの埋め込み**エクスペリエンスを使用している場合、*PowerBI-Developer-Samples.zip* ファイルを保存して解凍します。 *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* フォルダーを開き、*pbi-saas-embed-report.sln* ファイルを実行します。

### <a name="how-can-i-edit-my-registered-application"></a>登録済みアプリケーションを編集する方法

AAD 登録済みアプリケーションの編集方法については、「[クイック スタート:Azure Active Directory のアプリケーションを更新する](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-update-azure-ad-app)」をご覧ください。

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Power BI ユーザー プロファイルまたはデータを編集する方法

Power BI データの編集方法は、[こちら](https://docs.microsoft.com/power-bi/service-basic-concepts)をご覧ください。

詳しくは、「[埋め込みアプリケーションのトラブルシューティング](embedded-troubleshoot.md)」をご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。
