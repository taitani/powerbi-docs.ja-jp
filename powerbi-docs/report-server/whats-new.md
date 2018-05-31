---
title: Power BI レポート サーバーの新機能
description: Power BI レポート サーバーの新機能について説明します。 これは主要な機能領域を網羅しており、新しいアイテムがリリースされるたびに更新されます。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 04/19/2018
ms.author: maggies
ms.openlocfilehash: 391edc8a2187f9a4af43b93f0713d40e41f6e943
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34295424"
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI レポート サーバーの新機能
Power BI レポート サーバーの新機能について説明します。 これは主要な機能領域を網羅しており、新しいアイテムがリリースされるたびに更新されます。

Power BI Report Server および Power BI Report Server 向けに最適化された Power BI Desktop をダウンロードするには、「[Power BI Report Server によるオンプレミスでのレポート作成](https://powerbi.microsoft.com/report-server/)」を参照してください。

また、次のソースをチェックして、Power BI Report Server の新機能に関する最新情報を常に把握してください。

* [Microsoft Power BI ブログ](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services チームのブログ](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Guy in a Cube の YouTube チャネル](https://aka.ms/guyinacube)

関連するPower BI の最新情報については、以下を参照してください。

* [Power BI サービスの新機能](../service-whats-new.md)
* [Power BI Desktop の新機能](../desktop-latest-update.md)
* [Power BI 用モバイル アプリの新機能](../mobile-whats-new-in-the-mobile-apps.md)

## <a name="march-2018-release"></a>2018 年 3 月リリース

2018 年 3 月に、Power BI Report Server 向けに最適化された Power BI Desktop のバージョンに数多くの新しい機能が追加されます。 それらは次の領域に分類されます。 
- [ビジュアル](#visuals-updates)
- [レポート](#reporting)
- [分析](#analytics)
- [パフォーマンス](#performance)
- [レポート サーバー](#report-server)
- [その他](#other-improvements)

### <a name="highlights-of-this-release"></a>このリリースの重要なポイント

ここでは、新しい全機能の長いリストの中で特に興味深いものを紹介します。

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[テーブルとマトリックス用のルール ベースの条件付き書式](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)
 
テーブルまたはマトリックスの特定のビジネス ロジックに基づいて、列の背景またはフォントの色を条件付きで色付けするルールを作成します。

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[ページの表示と非表示](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

閲覧者がレポートにアクセスできるようにしたいが、一部のページが完全に完成していない場合があります。 そのページの準備ができるまで非表示にできるようになりました。 通常のナビゲーションからページを非表示にすることもできます。その場合、閲覧者はブックマークやドリルスルーを使用してページにアクセスできます。

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[ブックマーク](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

ブックマークと言えば、レポートのデータでストーリーを伝えるブックマークを作成します。

- [ブックマークのクロス強調表示](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): ブックマークには、ブックマークを作成した時点のレポート ページのクロス強調表示状態が維持され、表示されます。
- [ブックマークの柔軟性の向上](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): ブックマークはレポートで設定したプロパティを反映し、選択したビジュアルのみに影響します。

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[複数のグラフにまたがってデータ ポイントを複数選択する](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

複数のグラフの複数のデータ ポイントを選択し、クロスフィルター処理をページ全体に適用します。

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[レポートの複数のページにまたがってスライサーを同期する](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

スライサーは、レポート内の 1 ページ、2 ページ、またはそれ以上のページに適用できます。

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[クイック メジャー](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

テーブル内の既存のメジャーと数値列に基づいて新しいメジャーを作成します。

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[他のビジュアルに詳細なフィルターを適用する](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

1 つのビジュアルの特定のカテゴリをドリルダウンする場合、同じカテゴリでページのすべてのビジュアルをフィルター処理することができます。

### <a name="visuals-updates"></a>ビジュアルの更新

- [テーブルとマトリックスのセルの配置](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [テーブルとマトリックスの列の表示単位と精度のコントロール](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [横棒グラフと縦棒グラフのオーバーフロー データ ラベル](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [デカルトのデータ ラベルの背景色を制御し、ビジュアルをマッピングする](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [棒/列の余白を調整する](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [グラフの軸ラベルに使用される領域を増やす](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [X 軸と Y 軸のグループ化からの散布ビジュアル](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [緯度と経度に基づくマップの高密度サンプリング](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [レスポンシブ スライサー](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [相対日付スライサーのアンカー日付を追加する](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>レポート

- [レポートの読み取りモードでビジュアル ヘッダーをオフにする](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [低速なデータ ソース向けのレポート オプション](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [強化された既定のビジュアル配置](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [選択ウィンドウで視覚順を制御する](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [レポートでオブジェクトをロックする](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [書式設定および分析ウィンドウで検索する](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [フィールドのプロパティ ウィンドウとフィールドの説明](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Analytics

- [UTCNOW() と UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [カスタム日付テーブルのマーキング](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [他のビジュアルの詳細フィルター](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [複数の行カードに対する多次元 AS モデルのセル レベルの書式設定](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)
 
### <a name="performance"></a>Performance

- [フィルター処理のパフォーマンスの向上](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [DirectQuery のパフォーマンスの向上](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [開く動作と保存のパフォーマンス向上](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [[データのない項目を表示する] の改善](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)
 
### <a name="report-server"></a>レポート サーバー 

#### <a name="export-to-accessible-pdf"></a>アクセス可能な PDF へのエクスポート

ページ分割された (RDL) レポートを PDF にエクスポートする際に、アクセス可能な/タグ付けされた PDF ファイルを取得できるようになりました。 サイズは大きくなりますが、スクリーン リーダーやその他の支援技術による読み取りや移動が容易になります。 アクセス可能な PDF を有効にするには、**AccessiblePDF** デバイス情報の設定を **True** に指定します。 「[PDF デバイス情報の設定](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings)」と「[デバイス情報設定の変更](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings)」を参照してください。


### <a name="other-improvements"></a>その他の改良

- [[例から列を追加する] の改善](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [[コンサルティング サービス] クイック リンク](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [エラー レポートの改善](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [以前に発生したエラーの表示](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

 
## <a name="october-2017-release"></a>2017 年 10 月リリース
### <a name="power-bi-report-data-sources"></a>Power BI レポート データ ソース
Power BI Report Server の Power BI レポートは、さまざまなデータ ソースに接続できます。 データをインポートしてデータ更新スケジュールを設定したり、DirectQuery または SQL Server Analysis Services へのライブ接続を使って直接クエリを実行したりできます。 スケジュールされた更新および DirectQuery をサポートするデータ ソースの一覧については、「Power BI Report Server での Power BI レポート データ ソース」をご覧ください。

### <a name="scheduled-data-refresh-for-imported-data"></a>インポートしたデータのスケジュールされたデータ更新
Power BI Report Server では、スケジュールされたデータ更新をセットアップして、ライブ接続または DirectQuery ではなく埋め込みモデルで、Power BI レポートのデータを最新の状態に保つことができます。 埋め込みモデルではデータをインポートするので、元のデータ ソースからは切断されています。 データを最新の状態に保つにはデータを更新する必要があり、スケジュールされた更新はそのための方法です。 Power BI Report Server での Power BI レポートのスケジュールされた更新に関する記事をご覧ください。

### <a name="editing-power-bi-reports-from-the-server"></a>サーバーからの Power BI レポートの編集
サーバーから Power BI レポート (.pbix) ファイルを開いて編集できますが、取得されるのはアップロードした元のファイルです。  つまり、**サーバーによってデータが更新された場合、ファイルを初めて開いたときには、データは更新されません**。 変更を反映するには、手動でローカルにファイルを更新する必要があります。

### <a name="large-file-uploaddownload"></a>大きいファイルのアップロード/ダウンロード
アップロードできるファイルの最大サイズは 2 GB ですが、SQL Server Management Studio (SSMS) のレポート サーバーの設定では、既定で 1 GB に制限されています。  これらのファイルは SharePoint 用の場合と同様にデータベースに格納され、SQL Server カタログ用の特別な構成は必要ありません。  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>OData フィードとしての共有データセットへのアクセス
OData フィードを使って Power BI Desktop から共有データセットにアクセスできます。 詳細については、「[Power BI Report Server で OData フィードとして共有データセットにアクセスする](access-dataset-odata.md)」をご覧ください。

### <a name="scale-out"></a>スケールアウト
このリリースでは、スケールアウトがサポートされています。ロード バランサーを使って、最良のエクスペリエンスになるようにサーバーのアフィニティを設定します。 シナリオはまだスケールアウト対応に最適化されていないため、モデルが複数のノードにレプリケートされる可能性があることに注意してください。 シナリオは、ネットワーク ロード バランサーと固定セッションがなくても機能します。 ただし、モデルが N 回読み込まれるのでノード間でメモリの過剰使用が発生するだけでなく、要求の間に新しいノードに達するとモデルがストリーミングされるため、接続の間でパフォーマンスが低下します。  

### <a name="administrator-settings"></a>管理者の設定
管理者は、サーバー ファームの SSMS 詳細プロパティで、次のプロパティを設定できます。

* EnableCustomVisuals: True/False
* EnablePowerBIReportEmbeddedModels: True/False
* EnablePowerBIReportExportData: True/False
* MaxFileSizeMb: 既定値が 1000 になりました
* ModelCleanupCycleMinutes: メモリからのモデルの削除をチェックする頻度
* ModelExpirationMinutes: 最終使用時刻に基づく、モデルの有効期限が切れて削除されるまでの時間
* ScheduleRefreshTimeoutMinutes: モデルのデータ更新にかけられる時間。 既定では 2 時間です。  ハード上限はありません。

**構成ファイル rsreportserver.config**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>開発者 API
SSRS 2017 に導入された開発者 API (REST API) が、Power BI Report Server で Excel ファイルと .pbix ファイルの両方を使うことができるように拡張されました。 プログラムでサーバーからファイルをダウンロードし、更新してから再発行するといったユース ケースが考えられます。 たとえば、これは PowerPivot モデルを含む Excel ブックを更新する唯一の方法です。

大きいファイル用に別の新しい API があることに注意してください。これは、Swagger の Power BI Report Server バージョンで更新されます。 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) と Power BI Report Server のメモリ使用量
Power BI Report Server は、SQL Server Analysis Services (SSAS) を内部的にホストするようになりました。 これは、スケジュールされた更新に限ったことではありません。 SSAS をホストすることで、レポート サーバーのメモリ使用量を大幅に拡張できます。 サーバー ノードでは AS.ini 構成ファイルを使うことができるので、SSAS に慣れている場合は、最大メモリ制限やディスク キャッシュなどの設定を更新できます。詳細については、「[Server properties in Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services)」(Analysis Services でのサーバー プロパティ) をご覧ください。

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Excel ブックの表示と操作
Excel と Power BI には、業界で他に類を見ないツール ポートフォリオが含まれています。 併用することで、企業のアナリストはデータをより簡単に収集し、整理し、分析し、視覚的に調査できます。 Web ポータルで Power BI レポートを表示することに加え、Power BI Report Server では、ビジネス ユーザーは Excel ブックで同じことができるようになりました。セルフサービスの Microsoft BI コンテンツを 1 か所で公開し、表示します。

[Power BI Report Server のプレビュー環境に Office Online Server (OOS) を追加する方法を紹介したチュートリアル](excel-oos.md)を公開しています。 ボリューム ライセンス アカウントのお客様は Volume License Servicing Center から閲覧専用機能を持つ OOS を無料でダウンロードできます。 構成後、次のような Excel ブックを表示し、操作できます。

* 外部データ ソースとの依存関係がない
* 外部 SQL Server Analysis Services データ ソースにライブ接続している
* PowerPivot データ モデルがある

### <a name="support-for-new-table-and-matrix-visuals"></a>新しいテーブルとマトリックス ビジュアルのサポート
Power BI Report Server は、Power BI の新しいテーブル ビジュアルとマトリックス ビジュアルをサポートするようになりました。 これらのビジュアルでレポートを作成するには、2017 年 10 月リリース向けに更新された Power BI Desktop リリースが必要です。 Power BI Desktop (2017 年 6 月) リリースと並列インストールすることはできません。 Power BI Desktop の最新バージョンについては、[Power BI Report Server のダウンロード ページ](https://powerbi.microsoft.com/report-server/)で、**[ダウンロードの詳細オプション]** を選んでください。

## <a name="june-2017"></a>2017 年 6 月
* Power BI Report Server が一般公開 (GA) されました。

## <a name="may-2017"></a>2017 年 5 月
* Power BI レポート サーバー プレビューが利用可能
* Power BI レポートをオンプレミスで公開する機能
  * カスタム ビジュアルのサポート
  * サポートされるのは Analysis Services のライブ接続のみ。今後、さらに多くのデータ ソースがサポートされる予定
  * Power BI レポート サーバーでホストされている Power BI レポートを表示するように Power BI モバイル アプリを更新
* レポートにコメントを含めてコラボレーションを強化

## <a name="next-steps"></a>次の手順
[ユーザー向けハンドブック](user-handbook-overview.md)  
[管理者向けハンドブック](admin-handbook-overview.md)  
[Power BI レポート サーバーのインストール](install-report-server.md)  
[レポート ビルダーをインストールする](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) のダウンロード](http://go.microsoft.com/fwlink/?LinkID=616714)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

