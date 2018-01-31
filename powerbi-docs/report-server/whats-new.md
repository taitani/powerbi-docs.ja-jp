---
title: "Power BI レポート サーバーの新機能"
description: "Power BI レポート サーバーの新機能について説明します。 これは主要な機能領域を網羅しており、新しいアイテムがリリースされるたびに更新されます。"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/31/2017
ms.author: maghan
ms.openlocfilehash: 2ac4efa4e1eff5099fa3732b0fa753b04941979e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2018
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI レポート サーバーの新機能
Power BI レポート サーバーの新機能について説明します。 これは主要な機能領域を網羅しており、新しいアイテムがリリースされるたびに更新されます。

Power BI Report Server および Power BI Report Server 向けに最適化された Power BI Desktop をダウンロードするには、「[Power BI Report Server によるオンプレミスでのレポート作成](https://powerbi.microsoft.com/report-server/)」を参照してください。

![ヒント](media/whats-new/fyi-tip.png "ヒント") 最新のリリース ノートについては、「[Power BI Report Server - Release notes](release-notes.md)」 (Power BI レポート サーバー - リリース ノート) をご覧ください。

関連する最新情報については、次の資料を参照してください。

* [Power BI サービスの新機能](../service-whats-new.md)
* [Power BI Desktop の新機能](../desktop-latest-update.md)
* [Power BI 用モバイル アプリの新機能](../mobile-whats-new-in-the-mobile-apps.md)
* [Power BI チーム ブログ](https://powerbi.microsoft.com/blog/)

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
[Power BI レポート サーバーのリリース ノート](release-notes.md)  
[ユーザー向けハンドブック](user-handbook-overview.md)  
[管理者向けハンドブック](admin-handbook-overview.md)  
[クイックスタート: Power BI レポート サーバーをインストールする](quickstart-install-report-server.md)  
[レポート ビルダーをインストールする](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) のダウンロード](http://go.microsoft.com/fwlink/?LinkID=616714)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

