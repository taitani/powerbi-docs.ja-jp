---
title: 'Power BI のページ分割されたレポート: FAQ (プレビュー)'
description: この記事では、ページ分割されたレポートについてよく寄せられる質問に答えます。 これらのレポートは、印刷や PDF 生成用に最適化されている、高度に書式設定されたピクセル単位で完璧な出力です。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: overview
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: 0ddf95563c52af135ac7ae4fe71aeddcd2ce7313
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51268081"
---
# <a name="paginated-reports-in-power-bi-faq-preview"></a>Power BI のページ分割されたレポート: FAQ (プレビュー)

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

まだできません。 パブリック プレビューでは、既存レポートの新しいタブで、Power BI データセットと同じ関連する詳細を監視できます。

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>ページ分割されたレポートを作成して発行するには、Pro ライセンスが必要ですか。

はい。 Pro ライセンスがないと、ワークスペースにレポートをアップロードできません。 Pro ライセンスがなくてもレポート ビルダーをダウンロードして試すことはできますが、作成したページ分割されたレポートを公開することはできません。 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>ワークスペースにページ分割されたレポートがある状態で、ページ分割されたレポート ワークロードをオフにするとどうなりますか。

エラー メッセージが表示され、ワークロードをオンに戻すまでレポートを表示することはできません。 それでも、ワークスペースからレポートを削除することはできます。

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>ページ分割されたレポートに対してサポートされる各 Premium SKU の既定のメモリは何ですか。

ページ分割されたレポートに対する各 Premium SKU の既定のメモリは次のとおりです。

- **P1/A4**: 20% (既定値)、10% (最小値)
- **P2/A5**: 10% (既定値)、5% (最小値)
- **P3/A6**: 5% (既定値)、2.5% (最小値)

## <a name="general"></a>全般

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>ページ分割されたレポートと Power BI レポートはそれぞれどのようなときに使用する必要がありますか。

ページ分割されたレポートは、印刷や PDF 生成用に最適化されている、高度に書式設定されたピクセル単位で完璧な出力が必要なシナリオに最適です。  損益計算書は、ページ分割されたレポートとして作成するのがおそらく望ましいレポートの種類のよい例です。  

Power BI レポートは、探索と対話性に最適化されています。  異なる営業担当者が、同じレポートのデータを特定の地域/業界/顧客でスライスして業績の変化を見る売上レポートは、Power BI レポートで提供するのが最善です。

### <a name="the-documentation-says-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>ドキュメントでは、レポート ビルダーが推奨される作成ツールになっています。 Power BI 用の SQL Server Data Tools でページ分割されたれたレポートを作成できますか。

はい。ただし、Power BI サービスでは一度に 1 つの項目しかアップロードできないので、作成者が SQL Server Data Tools (SSDT) で使用する多くのシナリオは、まだサポートされていません。 [サポートされていない機能の完全な一覧](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi)は、この FAQ で後ほど示します。  

### <a name="what-versions-of-report-builder-do-you-support"></a>どのバージョンのレポート ビルダーがサポートされていますか。

レポートを作成して Power BI サービスに発行するには、最新バージョンの SQL Server 2016 レポート ビルダーを使用してください。 [レポート ビルダーは、Microsoft ダウンロード センターから](https://www.microsoft.com/download/details.aspx?id=53613)インストールします。

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>SQL Server Reporting Services に保存してある既存のレポートを Power BI に移動するにはどうすればよいですか。

サーバーからレポートをダウンロードした後、ポータルを使用して Power BI にアップロードする必要があります。  現時点では使用可能な移行ツールはありませんが、パブリック プレビューが完了し、製品間の機能パリティが適切なレベルになった後で、ツールを作成する予定です。

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>レポートを開いて、サービスに直接発行できますか。

現時点では、いいえです。 Power BI Desktop で可能なように、レポート ビルダーでレポートを開いてサービスに直接公開する機能を、いつかは追加する予定です。

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
- 非表示パラメーター

切り替えと対話式の並べ替えは、まだ運用段階ではありませんが、間もなく提供される予定です。    

切り替え/並べ替え以外の Power BI サービスでサポートされていない機能を含むファイルをアップロードしようとすると、エラー メッセージが表示されます。

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>ページ分割されたレポートに対して現在サポートされているデータ ソースは何ですか。

Azure SQL Database、SQL Server、およびオンプレミス ゲートウェイを使用する SQL Server Analysis Services (SSAS) の表形式モデルが、サポートされています。 SSAS 多次元 (MDX) モデルは現在サポートされていません。

ゲートウェイを介した SSAS へのアクセスが機能するには、資格情報が格納されているユーザーに管理者特権のアクセス許可が必要です。

### <a name="what-authentication-methods-do-you-support"></a>どのような認証方法がサポートされていますか。

現在は、ポータルまたはゲートウェイでデータ ソースと共にユーザー名とパスワードを格納する必要があります。  行レベルのセキュリティなどの他の認証方法のサポートは、今後プレビューになります。

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>ページ分割されたレポートのデータ ソースとして、Power BI データセットを使用できますか。

まだできませんが、まもなくサポートされる予定です。

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>ゲートウェイを介してストアド プロシージャを使用できますか。

ゲートウェイを介してストアド プロシージャを使用することはできますが、ストアド プロシージャにパラメーターがある場合はできません。

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Power BI サービスでレポートにはどのようなエクスポート形式を使用できますか。

Microsoft Excel、Microsoft Word、Microsoft PowerPoint、PDF、.CSV、XML、MHTML にエクスポートできます。

### <a name="can-i-print-paginated-reports"></a>ページ分割されたレポートを印刷できますか。

現在は、PDF にエクスポートして、ファイルを印刷できます。 ページ分割されたレポートからの直接印刷は、近日中に使用できるようになります。 

### <a name="are-e-mail-subscriptions-available-yet-for-paginated-reports"></a>メール サブスクリプションはページ分割されたレポートに対して使用できますか。

いいえ、メール サブスクリプションは今後提供されます。

### <a name="what-features-from-ssrs-will-you-be-supporting-in-the-power-bi-service"></a>Power BI サービスではサポート SSRS のどのような機能がサポートされていますか。

2 つの製品間のパリティが可能な限り近くなるように提供することを計画しています。  Power BI での異なるアクセス許可モデルなど、SSRS と Power BI に関する特定の事柄は、既存の SSRS パターンに合わせるため変更しようとしても意味がありませんが、この種の決定についてはお客様やパートナーからのフィードバックをお待ちしています。

### <a name="can-i-run-custom-code-in-my-report"></a>レポートでカスタム コードを実行できますか。

はい、SSRS と同様に、レポートでもコードを実行する機能がサポートされています。

### <a name="does-this-mean-ssrs-is-going-away"></a>これは SSRS がなくなることを意味しますか。

全く違います。  この新しいオファリングでは、ページ分割されたレポートのクラウド ベースのオプションがお客様に提供されます。  

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Power BI Embedded を使用して、自分がホストしているアプリにページ分割されたレポートを埋め込むことはできますか。

既存の Power BI API でこのシナリオをサポートすることは予定されていますが、このシナリオが使用可能になる時間枠はまだ決まっていません。

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Power BI レポートからページ分割されたレポートにドリルスルーできますか。

いいえ、まだできませんが、このシナリオのサポートは予定されています。

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Power BI アプリを使って、ページ分割されたレポートの内容を共有できますか。

現在は、ポータルでの共有アクションを使用して、他のユーザーと個々のページ分割されたレポートを共有できます。 アプリでの共有はまだサポートされていませんが、間もなくサポートされる予定です。 ツール バーにも共有ボタンを設けます。

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>ダッシュボードへのレポート タイルのピン留めのような Power BI での他のレポート固有機能は、ページ分割されたレポートで動作しますか。

可能な限り、サービスと同じ主要シナリオをレポートでもサポートする予定です。  作成ツールは異なっても、利用者の観点からはポータルのリストの他のレポートと同じであることが理想的です。 作成された方法を気にすることなく、必要なことを実現できます。  この機能パリティのよい例は、計画されているコメントのサポートです。 機能自体の動作は各レポートの種類で若干異なる場合がありますが、どちらでもコメントを使用することができます。

### <a name="are-you-planning-to-create-a-new-authoring-tool-for-paginated-reports-in-the-power-bi-service--we-cant-do-everything-we-need-to-with-report-builder-today"></a>Power BI サービスでページ分割されたレポート用に新しい作成ツールを作成する予定はありますか。  レポート ビルダーで必要なすべてのことを今すぐ行うことはできません。

最適なツールにするためのさまざまなオプションをまだ模索していますが、ALM やカスタム拡張機能など、SSRS 用作成ツールのいずれかにのみ含まれる可能性のある機能はサポートするので安心してください。 

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>SSRS の顧客が Power BI に既存のレポートと資産を移動できる移行ツールは計画されていますか。

はい、Power BI サービスでサポートされる一連のコア機能が完了するまでは提供されません。

### <a name="will-i-ever-be-able-to-create-both-paginated-reports-and-power-bi-reports-in-a-single-authoring-tool"></a>1 つの作成ツールでページ分割されたレポートと Power BI レポートの両方を作成できるようになりますか。

現在は単一の作成ツールは計画されていませんが、作成ツールも一緒に単一の BI スイートとして配布するか、または個別のダウンロード/分ランドにする可能性を検討しています。

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Power BI サービスにはページ分割されたレポート用のレポート ビューアー コントロールがありますか。

いいえ、現在は使用できるレポート ビューアー コントロールはありません。

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Power BI サービスの新しいホーム エクスペリエンスからページ分割されたレポートを検索できますか。

いいえ、現在はホームからページ分割されたレポートを検索することはできません。  ただし、新しいホーム エクスペリエンスの他の部分で表示できます。

## <a name="next-steps"></a>次の手順

- [Microsoft ダウンロード センターからレポート ビルダーをインストールする](https://www.microsoft.com/download/details.aspx?id=53613)
- [チュートリアル: ページ分割されたレポートを作成する](paginated-reports-quickstart-aw.md)