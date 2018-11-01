---
title: Power BI 管理ポータル
description: 管理ポータルを使用して、組織内の Power BI のテナントを管理できます。 利用状況の指標、Office 365 管理センターへのアクセス、設定などの項目があります。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/30/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 02829adb386cc746715a34300a42aba616dc2d60
ms.sourcegitcommit: 862faf948468d7f6d464b83f4e0b040d5213a580
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "50252493"
---
# <a name="power-bi-admin-portal"></a>Power BI 管理ポータル

管理ポータルを使用すると、組織の Power BI "*テナント*" を管理できます。 ポータルには、利用状況の指標、Office 365 管理センターへのアクセス、設定などの項目が含まれています。

完全な管理ポータルには、Office 365 のグローバル管理者であるか、Power BI サービス管理者の役割が割り当てられているすべてのユーザーがアクセスできます。 これらの役割のいずれも割り当てられていない場合、表示できるのはポータルの **[容量の設定]** のみです。 Power BI サービス管理者の役割の詳細については、「[Power BI 管理者の役割について](service-admin-role.md)」を参照してください。

## <a name="how-to-get-to-the-admin-portal"></a>管理ポータルにアクセスする方法

Power BI の管理ポータルにアクセスするには、アカウントが Office 365 または Azure Active Directory 内で **[グローバル管理者]** とマークされているか、Power BI サービス管理者の役割が割り当てられている必要があります。 Power BI サービス管理者の役割の詳細については、「[Power BI 管理者の役割について](service-admin-role.md)」を参照してください。 Power BI 管理ポータルにアクセスするには、次のように操作します。

1. Power BI サービスの右上にある設定アイコン (歯車) を選択します。

1. **[管理ポータル]** を選択します。

    ![管理ポータルの設定](media/service-admin-portal/powerbi-admin-settings.png)

ポータルには 7 つのタブがあります。 この記事の残りの部分では、これらの各タブについて説明します。

![管理ポータルのナビゲーション](media/service-admin-portal/powerbi-admin-landing-page.png)

* [利用状況の指標](#usage-metrics)
* [ユーザー](#users)
* [監査ログ](#audit-logs)
* [テナント設定](#tenant-settings)
* [Premium の設定](#premium-settings)
* [埋め込みコード](#embed-codes)
* [組織のビジュアル](#organization-visuals)

## <a name="usage-metrics"></a>利用状況の指標

**[利用状況の指標]** を使用すると、組織の Power BI の使用状況を監視することができます。 また、組織のどのユーザーやグループが Power BI を最もアクティブに使用しているかを確認することもできます。

> [!NOTE]
> ダッシュボードに初めてアクセスした場合、またはダッシュボードを長期間表示しなかった後でもう一度アクセスした場合は、ダッシュボードを読み込んでいる間、読み込み中画面が表示される可能性があります。

ダッシュボードが読み込まれると、タイルのセクションが 2 つ表示されます。 最初のセクションには個々のユーザーの利用状況データが、2 番目のセクションには組織内のグループについての同様の情報が含まれます。

各タイルに表示される内容の詳細は次のとおりです。

* ユーザー ワークスペース内のすべてのダッシュ ボード、レポート、およびデータセットの重複しない数。
  
    ![ダッシュボード、レポート、データセットの重複しない数](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* アクセス可能ユーザー数別の最も使用されたダッシュボード。 たとえば、3 人のユーザーと共有しているダッシュ ボードがあるときに、別の 2 人のユーザーに接続されているコンテンツ パックにそのダッシュボードを追加した場合、数値は 6 になります (1 + 3 + 2)
  
    ![最も使用されたダッシュボード](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* ユーザーが最も接続しているコンテンツ。 これは、データ取得処理によってユーザーがアクセスできるコンテンツであり、SaaS コンテンツ パック、組織のコンテンツ パック、ファイル、またはデータベースになります。
  
    ![最も使用されたパッケージ](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* 所有しているダッシュボードの数 (自分で作成したダッシュボードと共有しているダッシュ ボードの両方) に基づく上位ユーザー ビュー。
  
    ![上位ユーザー - ダッシュボード](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* 所有しているレポートの数に基づく上位ユーザー ビュー。
  
    ![上位ユーザー - レポート](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

2 番目のセクションでは、同じ種類の情報が表示されますが、そのデータは (ユーザーではなく) グループに基づいています。 これにより、組織のどのグループが最もアクティブであり、どのようなコンテンツを使用しているかを確認できます。

これらの情報によって、組織全体のユーザーとグループが Power BI をどのように使用しているかについてリアルな洞察を得ることができ、組織内の非常にアクティブなユーザーとグループを認識できます。

## <a name="users"></a>ユーザー

Office 365 管理センターで Power BI のユーザー、グループ、管理者を管理します。 **[ユーザー]** タブには、テナントの管理センターへのリンクが含まれています。

![O365 管理センターに移動](media/service-admin-portal/powerbi-admin-manage-users.png)

## <a name="audit-logs"></a>監査ログ

Office 365 セキュリティ/コンプアライアンス センターで Power BI 監査ログを管理します。 **[監査ログ]** タブには、テナントのセキュリティ/コンプアライアンス センターへのリンクが含まれています。 [詳細情報](service-admin-auditing.md)

## <a name="tenant-settings"></a>テナント設定

**[テナント設定]** タブを使うと、組織で利用できる機能をきめ細かく制御できます。 機密データに関して懸念がある場合、一部の機能がお客様の組織に適していない場合や、特定の機能を特定のグループのみが使用できるようにする必要がある場合があります。

**[テナント設定]** タブの最初の 2 つのセクションを次の図に示します。

![テナント設定](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> テナントのすべてのユーザーに対して設定の変更が有効になるには、最大で 10 分かかることがあります。

次の 3 つの状態を設定できます。

* **組織全体に対して無効にする**: 組織のどのユーザーもこの機能を使用できません。

    ![すべて無効にする設定](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

* **組織全体に対して有効にする**: 組織のすべてのユーザーがこの機能を使用できます。

    ![すべて有効にする設定](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

* **組織のサブセットに対して有効にする**: 組織のユーザーまたはグループの特定のサブセットがこの機能を使用できます。

    特定のユーザーのグループを除いて、組織全体に対して機能を有効にすることができます。

    ![サブセットを有効にする設定](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

    特定のユーザーのグループのみに対して機能を有効にすることも、ユーザーのグループに対して機能を無効にすることもできます。 この方法を使用すると、特定のユーザーが許可されているグループに属している場合でも、その機能へのアクセス権を持たないようにすることができます。

    ![一部を除いて有効にする設定](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

次のいくつかのセクションでは、さまざまな種類のテナント設定の概要を示します。

## <a name="workspace-settings"></a>ワークスペースの設定

### <a name="create-workspaces-preview"></a>ワークスペース (プレビュー) を作成する

組織内のユーザーはアプリ ワークスペースを作成し、ダッシュボード、レポート、およびその他のコンテンツで共同作業を行うことができます。 [詳細情報](service-create-the-new-workspaces.md)

## <a name="export-and-sharing-settings"></a>エクスポートと共有の設定

### <a name="share-content-to-external-users"></a>外部ユーザーとコンテンツを共有する

組織内のユーザーは組織外のユーザーとダッシュボードを共有できます。

![外部ユーザーの設定](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

外部ユーザーと共有すると、次の図のようなメッセージが表示されます。

![外部ユーザーと共有する](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Web に公開

組織内のユーザーは、Web にレポートを公開することができます。 [詳細情報](service-publish-to-web.md)

**[Web に公開]** 設定を有効にした場合のレポートの **[ファイル]** メニューを次の図に示します。

![Web に公開設定](media/service-admin-portal/powerbi-admin-publish-to-web.png)

**[Web に公開]** の設定に基づき、UI にさまざまなオプションが表示されます。

|おすすめ |組織全体に対して有効にする |組織全体に対して無効にする |特定のセキュリティ グループ   |
|---------|---------|---------|---------|
|**[ファイル]** メニューの下の **[Web に公開]**。|すべてのユーザーに対して有効|すべてのユーザーに対して非表示|承認されたユーザーまたはグループに対してのみ表示されます。|
|**[設定]** の下の **[埋め込みコードの管理]**|すべてのユーザーに対して有効|すべてのユーザーに対して有効|すべてのユーザーに対して有効<br><br>* **[削除]** オプションは、承認されたユーザーまたはグループの場合にのみ使用可能です。<br>* **[コードを取得]** は、すべてのユーザーに対して有効になります。|
|管理ポータル内の **[埋め込みコード]**|状態には次のいずれかが反映されます。<br>* アクティブ<br>* サポートされていません<br>* ブロック|状態は **[無効]** と表示|状態には次のいずれかが反映されます。<br>* アクティブ<br>* サポートされていません<br>* ブロック<br><br>ユーザーがテナント設定に基づいて承認されていない場合、状態は **[侵害]** となります。|
|既存の公開済みレポート|すべて有効|すべて無効|すべてのユーザーに対して、レポートの表示が続行されます。|

### <a name="export-data"></a>データのエクスポート

組織内のユーザーは、タイルや視覚エフェクトからデータをエクスポートできます。 [詳細情報](visuals/power-bi-visualization-export-data.md)

タイルからデータをエクスポートするためのオプションを次の図に示します。

![タイルからデータをエクスポートする](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> また、**[データのエクスポート]** を無効にして、ユーザーが **[Excel で分析]** 機能と、Power BI サービスのライブ接続を使用できないように設定することもできます。

### <a name="export-reports-as-powerpoint-presentations"></a>PowerPoint プレゼンテーションとしてレポートをエクスポート

組織内のユーザーは、Power BI レポートを PowerPoint ファイルとしてエクスポートできます。 [詳細情報](consumer/end-user-powerpoint.md)

**[PowerPoint プレゼンテーションとしてレポートをエクスポート]** 設定を有効にした場合のレポートの **[ファイル]** メニューを次の図に示します。

![PowerPoint プレゼンテーションとしてレポートをエクスポート](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>ダッシュボードとレポートの印刷

組織内のユーザーは、ダッシュボードとレポートを印刷できます。 [詳細情報](consumer/end-user-print.md)

![](media/service-admin-portal/powerbi-admin-print-dashboard.png)

![](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-settings"></a>コンテンツ パックの設定

### <a name="publish-content-packs-to-the-entire-organization"></a>コンテンツ パックを組織全体に公開する

組織内のユーザーは、コンテンツ パックを組織全体に公開することができます。

![](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs"></a>テンプレートの組織のコンテンツ パックを作成する

組織内のユーザーは、Power BI Desktop 内の 1 つのデータ ソース上に構築されたデータセットを使用する、テンプレート コンテンツ パックを作成できます。

### <a name="push-apps-to-end-users"></a>アプリをエンド ユーザーにプッシュする

テナント管理者が **[テナント設定]** でアプリをプッシュする機能を有効にします。

   ![アプリのプッシュを有効にする](media/service-create-distribute-apps/power-bi-apps-pushapps01.png)

設定を **[有効]** に切り替えた後、この機能を利用できるユーザーを指定できます (組織全体または特定のセキュリティ グループ)。

> [!NOTE]
> テナント設定の変更が有効になるまで時間がかかることに注意してください。

アプリのプッシュの詳細については、[こちら](service-create-distribute-apps.md)をご覧ください。

## <a name="integration-settings"></a>統合の設定

### <a name="ask-questions-about-data-using-cortana"></a>Cortana を使ってデータに関する質問をする

組織内のユーザーは、データについて Cortana を使って質問することができます。

> [!NOTE]
> この設定は、組織全体に適用され、特定のグループに限定することはできません。

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>オンプレミスのデータセットで [Excel で分析] を使用する

組織内のユーザーは、Excel を使用して、オンプレミスの Power BI データセットの表示および操作を行うことができます。 [詳細情報](service-analyze-in-excel.md)

> [!NOTE]
> また、**[データのエクスポート]** を無効にして、ユーザーが **[Excel で分析]** 機能を使用することを防ぐこともできます。

### <a name="use-arcgis-maps-for-power-bi"></a>ArcGIS Maps for Power BI を使用する

組織内のユーザーは、Esri が提供する ArcGIS Maps for Power BI の視覚エフェクトを使用できます。 [詳細情報](power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Power BI でグローバル検索を使用する (プレビュー)

組織のユーザーには、Azure Search に依存する外部の検索機能を使用できます。 たとえば、Cortana を使用し、Power BI のダッシュボードとレポートから重要な情報を直接取得できます。 [詳細情報](service-cortana-intro.md)

## <a name="custom-visuals-settings"></a>カスタム ビジュアルの設定

### <a name="enable-custom-visuals-for-the-entire-organization"></a>組織全体のカスタム ビジュアルを有効にする

組織内のユーザーは、カスタム ビジュアルを操作して共有することができます。 [詳細情報](power-bi-custom-visuals.md)

> [!NOTE]
> この設定は、組織全体に適用され、特定のグループに限定することはできません。

## <a name="r-visuals-settings"></a>R ビジュアルの設定

### <a name="interact-with-and-share-r-visuals"></a>R ビジュアルとの対話と共有

組織内のユーザーは、R スクリプトで作成したビジュアルと対話して共有することができます。 [詳細情報](visuals/service-r-visuals.md)

> [!NOTE]
> この設定は、組織全体に適用され、特定のグループに限定することはできません。

## <a name="audit-and-usage-settings"></a>監査と使用状況の設定

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>内部アクティビティの監査とコンプライアンスのための監査ログの作成

組織内のユーザーは監査を使用して、組織内の他のユーザーによって実行された Power BI のアクションを監視することができます。 [詳細情報](service-admin-auditing.md)

監査ログのエントリを記録するには、この設定を有効にする必要があります。 監査を有効にしてから監査データを表示できるようになるまで、最大で 48 時間の遅延が発生する場合があります。 データがすぐに表示されない場合は、後で、監査ログを確認してください。 監査ログの表示アクセス許可を取得してからログにアクセスできるようになるまでにも、同様の遅延が発生する場合があります。

> [!NOTE]
> この設定は、組織全体に適用され、特定のグループに限定することはできません。

### <a name="usage-metrics-for-content-creators"></a>コンテンツ作成者用の使用状況メトリック
組織内のユーザーは、自分が作成したダッシュボードとレポートの使用状況メトリックを確認できます。 [詳細情報](service-usage-metrics.md)

設定を **[有効]** に切り替えた後、使用状況メトリックを表示できるユーザーを指定できます (組織全体または特定のセキュリティ グループ)。

> [!NOTE]
> テナント設定の変更が有効になるまで時間がかかることに注意してください。

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>コンテンツ作成者用の使用状況メトリックにおけるユーザーごとのデータ
コンテンツ作成者用の使用状況メトリックには、コンテンツにアクセスしているユーザーの表示名とメール アドレスが示されます。 [詳細情報](service-usage-metrics.md)

設定を **[有効]** に切り替えた後、使用状況メトリックで表示名とメール アドレスを表示できるユーザーを指定できます (組織全体または特定のセキュリティ グループ)。

ユーザーごとのデータは利用状況メトリックに対して既定で有効になり、コンテンツ作成者のアカウント情報はメトリック レポートに含まれます。 一部またはすべてのユーザーに対してこの情報を含めない場合は、指定したセキュリティ グループまたは組織全体に対してこの機能を無効にします。 アカウント情報は、*[名前なし]* としてレポートに表示されます。

> [!NOTE]
> テナント設定の変更が有効になるまで時間がかかることに注意してください。


## <a name="dashboard-settings"></a>ダッシュボードの設定

### <a name="data-classification-for-dashboards"></a>ダッシュボードのデータ分類

組織内のユーザーは、ダッシュボードのセキュリティ レベルを示す分類を使って、ダッシュボードにタグを付けることができます。 [詳細情報](service-data-classification.md)

> [!NOTE]
> この設定は、組織全体に適用され、特定のグループに限定することはできません。

## <a name="developer-settings"></a>開発者の設定

### <a name="embed-content-in-apps"></a>アプリにコンテンツを埋め込む

組織内のユーザーが、Power BI のダッシュボードとレポートを、サービスとしてのソフトウェア (SaaS) アプリケーションに埋め込むことができます。 この設定を無効にすると、ユーザーが REST API を使用して、Power BI コンテンツをアプリケーションに埋め込むことができなくなります。

## <a name="capacity-settings"></a>容量の設定

### <a name="premium-settings"></a>Premium の設定

[Premium の設定] タブでは、組織用に購入されたすべての Power BI Premium (Em または P SKU) 容量を管理できます。 組織内のすべてのユーザーに [Premium の設定] タブが表示されますが、そのタブにコンテンツが表示されるのは、ユーザーが、**容量管理者**、または割り当てのアクセス許可を持つユーザーとして割り当てられている場合のみです。 アクセス許可が何も割り当てられていないユーザーには、次のメッセージが表示されます。

![Power BI Premium 管理の設定](media/service-admin-portal/premium-settings-no-access.png "Premium の設定にアクセスできません")

Premium の設定の管理方法について詳しくは、「[Power BI Premium の管理](service-admin-premium-manage.md)」をご覧ください。

### <a name="power-bi-embedded-settings"></a>Power BI Embedded の設定

Power BI Embedded の設定タブを使用すると、顧客用に購入した Power BI Embedded (A SKU) の容量を表示できます。 Azure からは A SKU の購入のみ可能であるため、**Azure Portal** から [Azure の埋め込み容量を管理](developer/azure-pbie-create-capacity.md)できます。

![Power BI Embedded 管理の設定](media/service-admin-portal/manage-pbie-capacities-01.png)

![Power BI Embedded 管理の設定の詳細](media/service-admin-portal/manage-pbie-capacities-02.png)

Power BI Embedded (A SKU) の設定を管理する方法について詳しくは、「[Azure の Power BI Embedded とは何か](developer/azure-pbie-what-is-power-bi-embedded.md)」をご覧ください。

## <a name="embed-codes"></a>埋め込みコード

![Power BI 管理ポータル内の埋め込みコード](media/service-admin-portal/embed-codes.png)

管理者は、テナントに対して生成されている埋め込みコードを表示することができます。 レポートを表示したり、埋め込みコードを削除して取り消したりすることができます。

## <a name="organization-visuals"></a>組織のビジュアル

[組織のビジュアル] タブでは、組織内にカスタム ビジュアルを展開し、管理できます。つまり、独自のビジュアルを組織に簡単に展開できます。レポートを作成するとき、カスタム ビジュアルを簡単に見つけ、Power BI Desktop からレポートに直接インポートできます。

このページには、組織のリポジトリに現在展開されているすべてのカスタム ビジュアルが表示されます。

![組織の管理のビジュアル](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>新しいカスタム ビジュアルの追加

新しいカスタム ビジュアルを一覧に追加するには、**[カスタム ビジュアルの追加]** を選択します。

![](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

> [!WARNING]
> カスタム ビジュアルには、セキュリティやプライバシー上のリスクを伴うコードが含まれている可能性があります。組織のリポジトリに展開する前に、カスタム ビジュアルの作成者とソースが信頼できることを確認してください。

次のフィールドに入力します。

* .pbiviz ファイルを選択する (必須): アップロードするカスタム ビジュアル ファイルを選択します。 バージョン管理されている API カスタム ビジュアルのみをサポートしています (詳細はここをお読みください)。

カスタム ビジュアルをアップロードする前に、そのビジュアルのセキュリティとプライバシーを調べ、組織の基準に適合することを確認してください。 カスタム ビジュアル セキュリティの詳細情報

* カスタム ビジュアルに名前を付ける (必須): Power BI Desktop ユーザーにとってわかりやすくなるように、ビジュアルに短いタイトルを付けます。

* アイコン (必須): Power BI Desktop UI に表示されるアイコン ファイルです。

* 説明: ユーザーにとってわかりやすくなるようにビジュアルに簡単な説明を与えます。

"適用" を選択し、アップロード要求を開始します。 成功すると、一覧に新しい項目が表示されます。 失敗すると、エラー メッセージが表示されます。

### <a name="delete-a-custom-visual-from-the-list"></a>一覧からカスタム ビジュアルを削除する

リポジトリからビジュアルを完全削除するごみ箱アイコンを選択します。
重要: 削除は元に戻すことができません。 削除の直後から、既存のレポートでそのビジュアルのレンダリングが停止します。 同じビジュアルを再度アップロードしても、削除された以前のビジュアルに代わることにはなりません。新しいビジュアルを再度インポートし、レポートにあるインスタンスを置換できます。

### <a name="disable-a-custom-visual-in-the-list"></a>一覧でカスタム ビジュアルを無効にする

組織のストアからビジュアルを無効にするには、歯車アイコンを選択します。 **[アクセス]** セクションで、カスタム ビジュアルを無効にします。

無効にしたビジュアルは既存のレポートに表示されず、次のエラー メッセージが表示されます。

*This custom visual is no longer available.Please contact your administrator for details. (このカスタム ビジュアルは使用できなくなりました。詳細については管理者に問い合わせてください。)*

ただし、ブックマークが設定されたビジュアルは引き続き機能します。

更新または管理者による変更の後、Power BI Desktop ユーザーはアプリケーションを再起動するか、Power BI サービスでブラウザーを最新の情報に更新して、更新の内容を確認する必要があります。

### <a name="how-to-update-a-visual"></a>ビジュアルを更新する方法

新しいバージョンのビジュアル (バグ修正、新機能など) があるため、リポジトリ内のビジュアルを更新する場合は、**更新**アイコンを選択し、新しいファイルをアップロードします。 ビジュアル ID が変わらないことを確認します。 新しいファイルで、組織全体のすべてのレポートの以前のファイルが置き換えられます。 ただし、ビジュアルの新しいバージョンのためにビジュアルの以前のバージョンを使用できなくなったり、データ構造が破損されたりする可能性がある場合は、以前のバージョンを置き換えないでください。 代わりに、新しいバージョンのビジュアル用に新しく登録することをお勧めします。 たとえば、新しいバージョン番号 (バージョン X.X) を新しく登録されたビジュアルのタイトルに追加します。 こうすると、バージョン番号が更新されているだけで同じビジュアルであることがわかるので、既存のレポートの機能は中断されません。 この場合も、ビジュアル ID が変わらないことを確認します。 次回ユーザーが Power BI Desktop から組織のリポジトリに入ると、新しいバージョンをインポートできます。レポートに入っている現在のバージョンを置換するように求められます。

## <a name="next-steps"></a>次の手順

[Power BI 管理者の役割について](service-admin-role.md)  
[組織内の Power BI を監査する](service-admin-auditing.md)  
[Manage Power BI Premium](service-admin-premium-manage.md) (Power BI Premium の管理)  
[組織内の Power BI を管理する](service-admin-administering-power-bi-in-your-organization.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。
