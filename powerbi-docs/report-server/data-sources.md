---
title: "Power BI Report Server での Power BI レポート データ ソース"
description: "Power BI レポートは、さまざまなデータ ソースに接続できます。 データの使い方に応じて、異なるデータ ソースを利用できます。"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: f800f79fd49854e0f26a19de1fc9475dad0e1045
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Power BI Report Server での Power BI レポート データ ソース
Power BI レポートは、さまざまなデータ ソースに接続できます。 データの使い方に応じて、異なるデータ ソースを利用できます。 データをインポートすること、または DirectQuery を使うか SQL Server Analysis Services へのライブ接続を使ってデータのクエリを直接行うことができます。

これらのデータ ソースは、Power BI Report Server 内で使われている Power BI レポートに固有のものです。 ページ分割されたレポートでサポートされるデータ ソースについては、「[Reporting Services でサポートされるデータ ソース (SSRS)](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs)」をご覧ください。

> [!IMPORTANT]
> スケジュールされた更新を構成するには、Power BI Desktop レポートのすべてのデータ ソースがサポートされている必要があります。
> 
> 

## <a name="list-of-supported-data-sources"></a>サポートされているデータ ソースの一覧
サポート対象の一覧に記載されていない他のデータ ソースであっても、動作する可能性があります。

| **データ ソース** | **キャッシュされたデータ** | **スケジュールされた更新** | **Live/DirectQuery** |
| --- | --- | --- | --- |
| SQL Server データベース |はい |はい |はい |
| SQL Server Analysis Services |はい |はい |はい |
| Azure SQL Database |はい |はい |はい |
| Azure SQL Data Warehouse |はい |はい |はい |
| Excel |はい |はい |いいえ |
| Access データベース |はい |はい |いいえ |
| Active Directory |はい |はい |いいえ |
| Amazon Redshift |はい |いいえ |いいえ |
| Azure BLOB ストレージ |はい |はい |いいえ |
| Azure Data Lake Store |はい |いいえ |いいえ |
| Azure HDInsight (HDFS) |はい |はい |いいえ |
| Azure HDInsight (Spark) |はい |はい |いいえ |
| Azure テーブル ストレージ |はい |はい |いいえ |
| Dynamics 365 (オンライン) |はい |いいえ |いいえ |
| Facebook |はい |いいえ |いいえ |
| フォルダー |はい |はい |いいえ |
| Google アナリティクス |はい |いいえ |いいえ |
| Hadoop ファイル (HDFS) |はい |いいえ |いいえ |
| IBM DB2 データベース |はい |はい |いいえ |
| Impala |はい |いいえ |いいえ |
| JSON |はい |はい |いいえ |
| Microsoft Exchange |はい |いいえ |いいえ |
| Microsoft Exchange Online |はい |いいえ |いいえ |
| MySQL データベース |はい |はい |いいえ |
| OData フィード |はい |はい |いいえ |
| ODBC |はい |はい |いいえ |
| OLE DB |はい |はい |いいえ |
| Oracle データベース |はい |はい |はい |
| PostgreSQL データベース |はい |はい |いいえ |
| Power BI サービス |いいえ |いいえ |いいえ |
| R スクリプト |はい |いいえ |いいえ |
| Salesforce オブジェクト |はい |いいえ |いいえ |
| Salesforce レポート |はい |いいえ |いいえ |
| SAP Business Warehouse サーバー |はい |はい |はい |
| SAP HANA データベース |はい |はい |はい |
| SharePoint フォルダー (オンプレミス) |はい |はい |いいえ |
| SharePoint リスト (オンプレミス) |はい |はい |いいえ |
| SharePoint Online リスト |はい |いいえ |いいえ |
| Snowflake |はい |いいえ |いいえ |
| Sybase データベース |はい |はい |いいえ |
| Teradata データベース |はい |はい |はい |
| TEXT/CSV |はい |はい |いいえ |
| Web |はい |はい |いいえ |
| XML |はい |はい |いいえ |
| appFigures (Beta) |はい |いいえ |いいえ |
| Azure Analysis Services データベース (ベータ版) |はい |いいえ |いいえ |
| Azure Cosmos DB (ベータ版) |はい |いいえ |いいえ |
| Azure HDInsight Spark (Beta) |はい |いいえ |いいえ |
| Common Data Service (Beta) |はい |いいえ |いいえ |
| comScore Digital Analytix (Beta) |はい |いいえ |いいえ |
| Dynamics 365 for Customer Insights (ベータ) |はい |いいえ |いいえ |
| Dynamics 365 for Financials (Beta) |はい |いいえ |いいえ |
| GitHub (Beta) |はい |いいえ |いいえ |
| Google BigQuery (ベータ版) |はい |いいえ |いいえ |
| IBM Informix データベース (Beta) |はい |いいえ |いいえ |
| IBM Netezza (ベータ) |はい |いいえ |いいえ |
| Kusto (Beta) |はい |いいえ |いいえ |
| MailChimp (Beta) |はい |いいえ |いいえ |
| Microsoft Azure Consumption Insights (Beta) |はい |いいえ |いいえ |
| Mixpanel (Beta) |はい |いいえ |いいえ |
| Planview Enterprise (Beta) |はい |いいえ |いいえ |
| Projectplace (Beta) |はい |いいえ |いいえ |
| QuickBooks Online (Beta) |はい |いいえ |いいえ |
| Smartsheet |はい |いいえ |いいえ |
| Spark (Beta) |はい |いいえ |いいえ |
| SparkPost (Beta) |はい |いいえ |いいえ |
| SQL Sentry |はい |いいえ |いいえ |
| Stripe (Beta) |はい |いいえ |いいえ |
| SweetIQ (Beta) |はい |いいえ |いいえ |
| Troux (Beta) |はい |いいえ |いいえ |
| Twilio (Beta) |はい |いいえ |いいえ |
| tyGraph (Beta) |はい |いいえ |いいえ |
| Vertica (Beta) |はい |いいえ |いいえ |
| Visual Studio Team Services (Beta) |はい |いいえ |いいえ |
| Webtrends (Beta) |はい |いいえ |いいえ |
| Zendesk (Beta) |はい |いいえ |いいえ |

> [!IMPORTANT]
> 環境内で Kerberos が正しく構成されている場合は、データ ソースで構成されている行レベルのセキュリティが、特定の DirectQuery (SQL Server、Azure SQL Database、Oracle、Teradata) およびライブ接続に対して機能します。
> 
> 

## <a name="next-steps"></a>次の手順
データ ソースを選んだ後は、そのデータ ソースからのデータを使って[レポートを作成](quickstart-create-powerbi-report.md)します。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

