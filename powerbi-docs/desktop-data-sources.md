---
title: "Power BI Desktop のデータ ソース"
description: "Power BI Desktop のデータ ソース"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 04/29/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: 6014b38e0e9cabe0dc909268f87cdb284de47106
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="data-sources-in-power-bi-desktop"></a>Power BI Desktop のデータ ソース
Power BI Desktop を使用すると、多種多様なソースからデータに接続できます。 使用できるデータ ソースの完全な一覧は、このページの下部にあります。

データに接続するには、 **[ホーム]** リボンの **[データの取得]** を選択します。 下向きの矢印を選択するか、ボタン上の **[データの取得]** テキストを選択すると、次のイメージに示されているように **[最も一般的]** なデータ型が記載されたメニューが表示されます。

![](media/desktop-data-sources/data-sources_1.png)

**[その他]** を **[最も一般的]** メニューから選択すると、**[データの取得]** ウィンドウが表示されます。 **[データの取得]** ウィンドウを表示する場合 ( **[最も一般的]** メニューをバイパスします)、 **[データの取得]** **アイコン ボタン** を直接選択することもできます。

![](media/desktop-data-sources/data-sources_2.png)

> [!NOTE]
> Power BI チームは **Power BI Desktop** や **Power BI サービス**で利用できるデータ ソースを継続的に拡張しています。 そのため、*ベータ*や*プレビュー*などのマークが付いた、未完成の早期バージョンのデータ ソースが頻繁に公開されています。 データ ソースに*ベータ*や*プレビュー*などのマークが付いている場合、サポートや機能が限定されています。運用環境では利用しないでください。
> 
> 

## <a name="data-sources"></a>データ ソース
データ型は、次のカテゴリに分類されます。

* すべて
* ファイル
* データベース
* Azure
* オンライン サービス
* その他

**[すべて]** カテゴリには、すべてのカテゴリにあるすべてのデータ接続の種類が含まれます。

**[ファイル]** カテゴリには、次のデータ接続があります。

* Excel
* TEXT/CSV
* XML
* JSON
* フォルダー
* SharePoint フォルダー

次の図は、 **[ファイル]** の **[データの取得]**ウィンドウを示しています。

![](media/desktop-data-sources/data-sources_3.png)

> [!NOTE]
> Power BI Desktop の以前のバージョンでは、**CSV** と**テキスト**は別々のデータ接続の種類でした。 これらのデータ コネクタは、**CSV/テキスト**にまとめられました。
> 
> 

**[データベース]** カテゴリには、次のデータ接続があります。

* SQL Server データベース
* Access データベース
* SQL Server Analysis Services
* Oracle データベース
* IBM DB2 データベース
* IBM Informix データベース (Beta)
* IBM Netezza (ベータ)
* MySQL データベース
* PostgreSQL データベース
* Sybase データベース
* Teradata データベース
* SAP HANA データベース
* SAP Business Warehouse サーバー
* Amazon Redshift
* Impala
* Google BigQuery (ベータ版)
* Snowflake

> [!NOTE]
> 一部のデータベース コネクタの場合、有効にするためには、**[ファイル]、[オプションと設定]、[オプション]** の順に選択し、**[プレビュー機能]** を選択し、コネクタを有効にする必要があります。 前途コネクタの一部が表示されず、その中に使用したいコネクタも含まれている場合は、**[プレビュー機能]** を確認してください。 データ ソースに*ベータ*や*プレビュー*などのマークが付いている場合、サポートや機能が限定されていることにもご注意ください。運用環境では利用しないでください。
> 
> 

次の図は、 **[データベース]** の **[データの取得]**ウィンドウを示しています。

![](media/desktop-data-sources/data-sources_4.png)

**[Azure]** カテゴリには、次のデータ接続があります。

* Azure SQL Database
* Azure SQL Data Warehouse
* Azure Analysis Services データベース (ベータ版)
* Azure BLOB ストレージ
* Azure テーブル ストレージ
* Azure Cosmos DB (ベータ版)
* Azure Data Lake Store
* Azure HDInsight (HDFS)
* Azure HDInsight Spark (Beta)

次の図は、 **[Azure]** の **[データの取得]**ウィンドウを示しています。

![](media/desktop-data-sources/data-sources_5.png)

**[オンライン サービス]** カテゴリには、次のデータ接続があります。

* Power BI サービス
* SharePoint Online リスト
* Microsoft Exchange Online
* Dynamics 365 (オンライン)
* Dynamics 365 for Financials (Beta)
* Common Data Service (Beta)
* Microsoft Azure Consumption Insights (Beta)
* Visual Studio Team Services (Beta)
* Salesforce オブジェクト
* Salesforce レポート
* Google アナリティクス
* appFigures (Beta)
* comScore Digital Analytix (Beta)
* Dynamics 365 for Customer Insights (ベータ)
* Facebook
* GitHub (Beta)
* Kusto (Beta)
* MailChimp (Beta)
* Mixpanel (Beta)
* Planview Enterprise (Beta)
* Projectplace (Beta)
* QuickBooks Online (Beta)
* Smartsheet
* SparkPost (Beta)
* SQL Sentry
* Stripe (Beta)
* SweetIQ (Beta)
* Troux (Beta)
* Twilio (Beta)
* tyGraph (Beta)
* Webtrends (Beta)
* Zendesk (Beta)

次の図は、**[オンライン サービス]** の **[データの取得]** ウィンドウを示しています。

![](media/desktop-data-sources/data-sources_6b.png)

**[その他]** カテゴリには、次のデータ接続があります。

* Vertica (Beta)
* Web
* SharePoint リスト
* OData フィード
* Active Directory
* Microsoft Exchange
* Hadoop ファイル (HDFS)
* Spark (Beta)
* R スクリプト
* ODBC
* OLE DB
* 空のクエリ

次の図は、 **[その他]** の **[データの取得]**ウィンドウを示しています。

![](media/desktop-data-sources/data-sources_7a.png)

> [!NOTE]
> 現時点では、Azure Active Directory を使用して保護されているカスタム データ ソースに接続することはできません。
> 
> 

## <a name="connecting-to-a-data-source"></a>データ ソースへの接続
データ ソースに接続するには、 **[データの取得]** ウィンドウでデータ ソースを選択し、 **[接続]**を選びます。 次の図の場合、 **[その他]** データ接続カテゴリで **[Web]** が選択されています。

![](media/desktop-data-sources/data-sources_7b.png)

対象のデータ接続に固有の接続ウィンドウが表示されます。 資格情報が必要な場合には、入力を求めるプロンプトが表示されます。 次の図には、Web データ ソースに接続するために URL を入力している様子が示されています。

![](media/desktop-data-sources/datasources_fromwebbox.png)

URL またはリソースの接続情報を入力したら、 **[OK]**を選択します。 Power BI Desktop はデータ ソースに接続し、 **[ナビゲーター]**に利用可能なデータ ソースが示されます。

![](media/desktop-data-sources/datasources_fromnavigatordialog.png)

**[ナビゲーター]** ウィンドウの下部にある **[読み込み]** ボタンを選択してデータを読み込むか、 **[編集]** ボタンを選択してクエリを編集してからデータを読み込みます。

これで、Power BI Desktop でデータ ソースに接続できます。 データ ソースの一覧は拡大を続けており、ここからデータへの接続をお試しください。一覧への追加は絶えず続いているため、頻繁にご確認ください。

## <a name="next-steps"></a>次の手順
Power BI Desktop を使用すると、さまざまなことを行えます。 そのような機能について詳しくは、次のリソースをご覧ください。

* [Power BI Desktop の概要](desktop-getting-started.md)
* [Power BI Desktop でのクエリの概要](desktop-query-overview.md)
* [Power BI Desktop でのデータ型](desktop-data-types.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop での一般的なクエリ タスク](desktop-common-query-tasks.md)    

