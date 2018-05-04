---
title: Power BI Report Server での Power BI レポート データ ソース
description: Power BI レポート (.pbix) は、複数のデータ ソースに接続できます。 データの使い方に応じて、異なるデータ ソースを利用できます。
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/23/2018
ms.author: maghan
ms.openlocfilehash: a32ef2e1e85b252a2a1071cb95c80149486c2604
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="power-bi-report-pbix-data-sources-in-power-bi-report-server"></a>Power BI Report Server での Power BI レポート (.pbix) データ ソース
Power BI レポートは、複数のデータ ソースに接続できます。 データの使い方に応じて、異なるデータ ソースを利用できます。 データをインポートすること、または DirectQuery を使うか SQL Server Analysis Services へのライブ接続を使ってデータのクエリを直接行うことができます。

これらのデータ ソースは、Power BI Report Server 内で使われている Power BI レポートに固有のものです。 ページ分割されたレポート (.rdl) でサポートされるデータ ソースについては、「[Reporting Services でサポートされるデータ ソース (SSRS)](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs)」をご覧ください。

> [!IMPORTANT]
> Power BI Desktop レポートのすべてのデータ ソースが、スケジュールされた更新の構成をサポートしている必要があります。
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
| Azure HDInsight (HDFS) |はい |いいえ |いいえ |
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
| Azure Analysis Services データベース |はい |いいえ |はい |
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

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>モデル更新でサポートされている認証方法の一覧

Power BI Report Server では、モデル更新のための認証方法として、OAuth ベースの認証をサポートしていません。 Excel または Access データベースなどの一部のデータ ソースでは、ファイルまたは Web などの個別の手順を利用してデータに接続します。

| **データ ソース** | **匿名認証** | **キー認証** | **ユーザー名とパスワード** | **Windows 認証** |
| --- | --- | --- | --- | --- |
| SQL Server データベース |いいえ |いいえ |はい |はい |
| SQL Server Analysis Services |いいえ |いいえ |はい |はい |
| Web |はい |いいえ |はい |はい |
| Azure SQL Database |いいえ |いいえ |はい |いいえ |
| Azure SQL Data Warehouse |いいえ |いいえ |はい |いいえ |
| Active Directory |いいえ |いいえ |はい |はい |
| Amazon Redshift |いいえ |いいえ |いいえ |いいえ |
| Azure BLOB ストレージ |はい |はい |いいえ |いいえ |
| Azure Data Lake Store |いいえ |いいえ |いいえ |いいえ |
| Azure HDInsight (HDFS) |いいえ |いいえ |いいえ |いいえ |
| Azure HDInsight (Spark) |はい |はい |いいえ |いいえ |
| Azure テーブル ストレージ |いいえ |はい |いいえ |いいえ |
| Dynamics 365 (オンライン) |いいえ |いいえ |いいえ |いいえ |
| Facebook |いいえ |いいえ |いいえ |いいえ |
| フォルダー |いいえ |いいえ |いいえ |はい |
| Google アナリティクス |いいえ |いいえ |いいえ |いいえ |
| Hadoop ファイル (HDFS) |いいえ |いいえ |いいえ |いいえ |
| IBM DB2 データベース |いいえ |いいえ |はい |はい |
| Impala |いいえ |いいえ |いいえ |いいえ |
| Microsoft Exchange |いいえ |いいえ |いいえ |いいえ |
| Microsoft Exchange Online |いいえ |いいえ |いいえ |いいえ |
| MySQL データベース |いいえ |いいえ |はい |はい |
| OData フィード |はい |はい |はい |はい |
| ODBC |はい |いいえ |はい |はい |
| OLE DB |はい |いいえ |はい |はい |
| Oracle データベース |いいえ |いいえ |はい |はい |
| PostgreSQL データベース |いいえ |いいえ |はい |いいえ |
| Power BI サービス |いいえ |いいえ |いいえ |いいえ |
| R スクリプト |いいえ |いいえ |いいえ |いいえ |
| Salesforce オブジェクト |いいえ |いいえ |いいえ |いいえ |
| Salesforce レポート |いいえ |いいえ |いいえ |いいえ |
| SAP Business Warehouse サーバー |いいえ |いいえ |はい |いいえ |
| SAP HANA データベース |いいえ |いいえ |はい |はい |
| SharePoint フォルダー (オンプレミス) |はい |いいえ |いいえ |はい |
| SharePoint リスト (オンプレミス) |はい |いいえ |いいえ |はい |
| SharePoint Online リスト |いいえ |いいえ |いいえ |いいえ |
| Snowflake |いいえ |いいえ |いいえ |いいえ |
| Sybase データベース |いいえ |いいえ |はい |はい |
| Teradata データベース |いいえ |いいえ |はい |はい |
| appFigures (Beta) |いいえ |いいえ |いいえ |いいえ |
| Azure Analysis Services データベース (ベータ版) |いいえ |いいえ |いいえ |いいえ |
| Azure Cosmos DB (ベータ版) |いいえ |いいえ |いいえ |いいえ |
| Azure HDInsight Spark (Beta) |いいえ |いいえ |いいえ |いいえ |
| Common Data Service (Beta) |いいえ |いいえ |いいえ |いいえ |
| comScore Digital Analytix (Beta) |いいえ |いいえ |いいえ |いいえ |
| Dynamics 365 for Customer Insights (ベータ) |いいえ |いいえ |いいえ |いいえ |
| Dynamics 365 for Financials (Beta) |いいえ |いいえ |いいえ |いいえ |
| GitHub (Beta) |いいえ |いいえ |いいえ |いいえ |
| Google BigQuery (ベータ版) |いいえ |いいえ |いいえ |いいえ |
| IBM Informix データベース (Beta) |いいえ |いいえ |いいえ |いいえ |
| IBM Netezza (ベータ) |いいえ |いいえ |いいえ |いいえ |
| Kusto (Beta) |いいえ |いいえ |いいえ |いいえ |
| MailChimp (Beta) |いいえ |いいえ |いいえ |いいえ |
| Microsoft Azure Consumption Insights (Beta) |いいえ |いいえ |いいえ |いいえ |
| Mixpanel (Beta) |いいえ |いいえ |いいえ |いいえ |
| Planview Enterprise (Beta) |いいえ |いいえ |いいえ |いいえ |
| Projectplace (Beta) |いいえ |いいえ |いいえ |いいえ |
| QuickBooks Online (Beta) |いいえ |いいえ |いいえ |いいえ |
| Smartsheet |いいえ |いいえ |いいえ |いいえ |
| Spark (Beta) |いいえ |いいえ |いいえ |いいえ |
| SparkPost (Beta) |いいえ |いいえ |いいえ |いいえ |
| SQL Sentry |いいえ |いいえ |いいえ |いいえ |
| Stripe (Beta) |いいえ |いいえ |いいえ |いいえ |
| SweetIQ (Beta) |いいえ |いいえ |いいえ |いいえ |
| Troux (Beta) |いいえ |いいえ |いいえ |いいえ |
| Twilio (Beta) |いいえ |いいえ |いいえ |いいえ |
| tyGraph (Beta) |いいえ |いいえ |いいえ |いいえ |
| Vertica (Beta) |いいえ |いいえ |いいえ |いいえ |
| Visual Studio Team Services (Beta) |いいえ |いいえ |いいえ |いいえ |
| Webtrends (Beta) |いいえ |いいえ |いいえ |いいえ |
| Zendesk (Beta) |いいえ |いいえ |いいえ |いいえ |

## <a name="list-of-supported-authentication-methods-for-directquery"></a>DirectQuery でサポートされている認証方法の一覧

Power BI Report Server では、DirectQuery 用の認証方法として、OAuth ベースの認証をサポートしていません。

| **データ ソース** | **匿名認証** | **キー認証** | **ユーザー名とパスワード** | **Windows 認証** | **統合 Windows 認証** |
| --- | --- | --- | --- | --- | --- |
| SQL Server データベース |いいえ |いいえ |はい |はい |はい |
| SQL Server Analysis Services |いいえ |いいえ |はい |はい |はい |
| Azure SQL Database |いいえ |いいえ |はい |いいえ |いいえ |
| Azure SQL Data Warehouse |いいえ |いいえ |はい |いいえ |いいえ |
| Oracle データベース |いいえ |いいえ |はい |はい |はい |
| SAP Business Warehouse サーバー |いいえ |いいえ |はい |いいえ |はい |
| SAP HANA データベース |いいえ |いいえ |はい |はい |いいえ |
| Teradata データベース |いいえ |いいえ |はい |はい |はい |


## <a name="next-steps"></a>次の手順
データ ソースに接続したので、そのデータ ソースからのデータを使って [Power BI レポートを作成](quickstart-create-powerbi-report.md)します。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

