---
title: Power BI のページ分割されたレポート:よくあるご質問 (プレビュー)
description: この記事では、ページ分割されたレポートについてよく寄せられる質問に答えます。 これらのレポートは、印刷や PDF 生成用に最適化されている、高度に書式設定されたピクセル単位で完璧な出力です。
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: overview
ms.date: 11/05/2018
ms.openlocfilehash: cedf72585d7aa4f2ece39739dc0bdba33ca66e21
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "60987787"
---
# <a name="paginated-reports-in-power-bi-faq-preview"></a>Power BI のページ分割されたレポート:よくあるご質問 (プレビュー)

この記事では、ページ分割されたレポートについてよく寄せられる質問に答えます。 これらのレポートは、印刷や PDF 生成用に最適化されている、高度に書式設定されたピクセル単位で完璧な出力です。 これらは、複数のページにちょうど収まるように設定されているため "ページ分割された" と呼ばれます。 ページ分割されたレポートは、SQL Server Reporting Services の RDL レポート テクノロジに基づいています。 

この記事では、Power BI Premium でのページ分割されたレポート、およびページ分割されたレポートを作成するためのスタンドアロン ツールであるレポート ビルダーに関する多くの一般的な質問に回答します。 サービスにレポートを発行するには、Power BI Pro ライセンスが必要です。 ワークスペースが Power BI Premium 容量に存在する限り、マイ ワークスペースまたはアプリ ワークスペースにページ分割されたレポートを発行して共有できます。 

## <a name="administration"></a>管理

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>ページ分割されたレポートに必要な Premium 容量のサイズはどれくらいですか。

ページ分割されたレポート ワークロードは、パブリック プレビューでは P1 ～ P3 SKU で利用できます。  A4 ～ A6 SKU では、テスト/開発シナリオに使用することもできます。

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>容量でページ分割されたレポートに対して設定できる最大メモリしきい値はどれくらいですか。

現時点では、このワークロードに対して予約できるのはメモリの 50% のみです。 

### <a name="how-does-user-access-work-for-paginated-reports"></a>ユーザー アクセスはページ分割されたレポートに対してどのように動作しますか。

ページ分割されたレポートに対するユーザー アクセスは、Power BI サービスでの他のすべてのコンテンツに対するユーザー アクセスと同じです。 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>ページ分割されたレポート ワークロードはどのようにしてオン/オフできますか。

容量管理者は、容量管理ポータル ページでページ分割されたレポート ワークロードを有効または無効にできます。  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>テナントでのページ分割されたレポートの利用状況はどのようにして監視できますか。

Office 365 の監査では、次のイベントでこのレポートの種類の詳細な使用状況が記録されます。 

- Power BI レポートの表示
- Power BI レポートの削除
- Power BI レポートの作成
- Power BI レポートのダウンロード

Power BI レポートとページ分割されたレポートを区別するため、ReportType フィールドには "PaginatedReport" という値が設定されます。

また、監査ログでは、ページ分割されたレポートに対して次のイベントが提供されます。

- ゲートウェイに対するバインドされた Power BI データセット
- Power BI データソースの検出
- TakeOverDatasource

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>Premium 容量監視アプリを使ってこのワークロードを監視できますか。

はい。Power BI データセットと同じ関連詳細が含まれる新しいタブで監視できます。

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>ページ分割されたレポートを作成して発行するには、Pro ライセンスが必要ですか。

はい。 Pro ライセンスがないと、ワークスペースにレポートをアップロードできません。 ダウンロードして、Pro ライセンスがなくて、Power BI のレポート ビルダーを使用することをお勧めしますが、しなくても作成する改ページ調整されたレポートを発行することはできません。 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>ワークスペースにページ分割されたレポートがある状態で、ページ分割されたレポート ワークロードをオフにするとどうなりますか。

エラー メッセージが表示され、ワークロードをオンに戻すまでレポートを表示することはできません。 それでも、ワークスペースからレポートを削除することはできます。

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>ページ分割されたレポートに対してサポートされる各 Premium SKU の既定のメモリは何ですか。

ページ分割されたレポートに対する各 Premium SKU の既定のメモリは次のとおりです。

- **P1/A4**:20% (既定値)、10% (最小値)
- **P2/A5**:20% (既定値)、5% (最小値)
- **P3/A6**:20% (既定値)、2.5% (最小値)

## <a name="general"></a>全般

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>ページ分割されたレポートと Power BI レポートはそれぞれどのようなときに使用する必要がありますか。

ページ分割されたレポートは、印刷や PDF 生成用に最適化されている、高度に書式設定されたピクセル単位で完璧な出力が必要なシナリオに最適です。  損益計算書は、ページ分割されたレポートとして作成するのがおそらく望ましいレポートの種類のよい例です。  

Power BI レポートは、探索と対話性に最適化されています。  異なる営業担当者が、同じレポートのデータを特定の地域/業界/顧客でスライスして業績の変化を見る売上レポートは、Power BI レポートで提供するのが最善です。

### <a name="the-documentation-says-power-bi-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Power BI のレポート ビルダー優先 authoring tool は、ドキュメントによるとします。 Power BI 用の SQL Server Data Tools でページ分割されたれたレポートを作成できますか。

はい。ただし、Power BI サービスでは一度に 1 つの項目しかアップロードできないので、作成者が SQL Server Data Tools (SSDT) で使用する多くのシナリオは、まだサポートされていません。 [サポートされていない機能の完全な一覧](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi)は、この FAQ で後ほど示します。  

### <a name="what-versions-of-report-builder-do-you-support"></a>どのバージョンのレポート ビルダーがサポートされていますか。

最近、Power BI サービスでの改ページ調整されたレポートの主要な編集ツールとして Power BI のレポート ビルダーをリリースしました。 インストール[Power BI のレポート ビルダー、Microsoft ダウンロード センターから](https://go.microsoft.com/fwlink/?linkid=2086513)します。

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>SQL Server Reporting Services に保存してある既存のレポートを Power BI に移動するにはどうすればよいですか。

サーバーからレポートをダウンロードした後、ポータルを使用して Power BI にアップロードする必要があります。  現時点では使用可能な移行ツールはありませんが、パブリック プレビューが完了し、製品間の機能パリティが適切なレベルになった後で、ツールを作成する予定です。

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>レポートを開いて、サービスに直接発行できますか。

現時点では、いいえです。 レポートを開くおよび公開するために、サービスに直接、GA 前に、Power BI レポート ビルダーから Power BI Desktop とサポートを追加いたします。

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>SSRS でのページ分割されたレポートの機能のうち、Power BI でまだサポートされていないものは何ですか。

現在、ページ分割されたレポートでは次のものがサポートされていません。

- 共有データ ソース
- 共有データセット
- サブレポート
- クリックスルーとドリルスルー アクション
- リンク レポート
- ブックマーク
- Bing マップ レイヤー
- カスタム フォント

切り替え/並べ替え以外の Power BI サービスでサポートされていない機能を含むファイルをアップロードしようとすると、エラー メッセージが表示されます。

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>ページ分割されたレポートに対して現在サポートされているデータ ソースは何ですか。

次のデータ ソースでサポートされています 

- Power BI Premium のデータセット
- (シングル サインオン (SSO)) を使用して azure Analysis Services
- Azure SQL Database
- SQL サーバー *
- (DAX) SQL Server Analysis Services (SSAS) 表形式および多次元のモデルから (MDX) * 
- Oracle * 
- Teradata * 

* オンプレミスのゲートウェイが必要です。

ゲートウェイを介した SSAS へのアクセスが機能するには、資格情報が格納されているユーザーに管理者特権のアクセス許可が必要です。

### <a name="what-authentication-methods-do-you-support"></a>どのような認証方法がサポートされていますか。

Azure Analysis Services と Power BI Premium の両方のデータ ソースの SSO サポートされています。  その他のすべてのデータ ソースでは、現在、ポータルまたはゲートウェイでユーザー名とデータ ソースとのパスワードを格納する必要があります。  

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>ページ分割されたレポートのデータ ソースとして、Power BI データセットを使用できますか。

はい、サポートされる Power BI Premium のデータセット、改ページ調整されたレポートのデータ ソースとして。

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>ゲートウェイを介してストアド プロシージャを使用できますか。

ゲートウェイ経由でストアド プロシージャを使用できますが、ストアド プロシージャにパラメーターが指定されている場合、特定のシナリオで問題が発生することがあります。

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Power BI サービスでレポートにはどのようなエクスポート形式を使用できますか。

Microsoft Excel、Microsoft Word、Microsoft PowerPoint、PDF、.CSV、XML、MHTML にエクスポートできます。

### <a name="can-i-print-paginated-reports"></a>ページ分割されたレポートを印刷できますか。

[はい]、印刷は、新規および改良された印刷プレビュー エクスペリエンスをなど、改ページ調整されたレポートに使用できます。 

### <a name="are-e-mail-subscriptions-available-yet-for-paginated-reports"></a>メール サブスクリプションはページ分割されたレポートに対して使用できますか。

いいえ。ただし、メール サブスクリプションは近日開始する予定です。

### <a name="what-features-from-ssrs-will-you-be-supporting-in-the-power-bi-service"></a>Power BI サービスではサポート SSRS のどのような機能がサポートされていますか。

Microsoft の計画では、多くのシナリオで機能を均衡させる予定です。ただし、SSRS と Power BI の一部の項目については、既存の SSRS パターンに合わせて変更することに意味がない場合があります。  たとえば、Power BI のさまざまなアクセス許可モデルは SSRS に逆マッピングできません。  Microsoft はこの種の決定を行うために、お客様やパートナーにフィードバックをお願いしています。

### <a name="can-i-run-custom-code-in-my-report"></a>レポートでカスタム コードを実行できますか。

はい、SSRS と同様に、レポートでもコードを実行する機能がサポートされています。

### <a name="does-this-mean-ssrs-is-going-away"></a>これは SSRS がなくなることを意味しますか。

全く違います。  この新しいオファリングでは、ページ分割されたレポートのクラウド ベースのオプションがお客様に提供されます。  

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Power BI Embedded を使用して、自分がホストしているアプリにページ分割されたレポートを埋め込むことはできますか。

既存の Power BI API でこのシナリオをサポートすることは予定されていますが、このシナリオが使用可能になる時間枠はまだ決まっていません。

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Power BI レポートからページ分割されたレポートにドリルスルーできますか。

いいえ、まだできませんが、このシナリオのサポートは予定されています。

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Power BI アプリを使って、ページ分割されたレポートの内容を共有できますか。

はい、v1 と v2 の両方のワークスペースからのアプリと共に配置される改ページ調整されたレポートがサポートされています。 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>ダッシュボードへのレポート タイルのピン留めのような Power BI での他のレポート固有機能は、ページ分割されたレポートで動作しますか。

可能な限り、サービスと同じ主要シナリオをレポートでもサポートする予定です。  作成ツールは異なっても、利用者の観点からはポータルのリストの他のレポートと同じであることが理想的です。 作成された方法を気にすることなく、必要なことを実現できます。  この機能パリティのよい例は、計画されているコメントのサポートです。 機能自体の動作は各レポートの種類で若干異なる場合がありますが、どちらでもコメントを使用することができます。

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>SSRS の顧客が Power BI に既存のレポートと資産を移動できる移行ツールは計画されていますか。

Power BI にコンテンツを移動するとき、自動化を取り入れるべく、Microsoft はさまざまな選択肢を検討しています。ただし、これは GA まで利用できません。

### <a name="will-i-ever-be-able-to-create-both-paginated-reports-and-power-bi-reports-in-a-single-authoring-tool"></a>1 つの作成ツールでページ分割されたレポートと Power BI レポートの両方を作成できるようになりますか。

潜在的には可能です。  現在のところ、このシナリオを可能にする方法を模索しています。また、単一の BI スイートと共に作成ツールを配布するか、個別のダウンロード/ブランディングを用意するか検討しています。

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Power BI サービスにはページ分割されたレポート用のレポート ビューアー コントロールがありますか。

いいえ、現在は使用できるレポート ビューアー コントロールはありません。

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Power BI サービスの新しいホーム エクスペリエンスからページ分割されたレポートを検索できますか。

いいえ、現在はホームからページ分割されたレポートを検索することはできません。  ただし、新しいホーム エクスペリエンスの他の部分で表示できます。

## <a name="next-steps"></a>次の手順

- [Microsoft ダウンロード センターからの Power BI のレポート ビルダーをインストールします。](https://go.microsoft.com/fwlink/?linkid=2086513)
- [チュートリアル:ページ分割されたレポートを作成する](paginated-reports-quickstart-aw.md)
