---
title: "Power BI の DirectQuery でサポートされるデータ ソース"
description: "DirectQuery を使用できるデータ ソースの一覧を取得します。"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 3630d876f3e32cbe981d7fb5bcc38d9da1a257f2
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Power BI の DirectQuery でサポートされるデータ ソース
**Power BI Desktop** と **Power BI サービス**には、接続してデータへのアクセスを可能にする多数のデータ ソースがあります。 この記事では、Power BI のどのデータ ソースが **DirectQuery** と呼ばれる接続方法をサポートしているかを説明します。 DirectQuery の詳細については、「[**Power BI での DirectQuery**](desktop-directquery-about.md)」を参照してください。

次のデータ ソースは、Power BI で DirectQuery をサポートしています。

* Amazon Redshift
* Azure HDInsight Spark (Beta)
* Azure SQL Database
* Azure SQL Data Warehouse
* Google BigQuery (ベータ版)
* IBM Netezza (ベータ)
* Impala (バージョン 2.x)
* Oracle データベース (バージョン 12 以降)
* SAP Business Warehouse (ベータ)
* SAP HANA
* Snowflake
* Spark (ベータ) (バージョン 0.9 以降)
* SQL Server
* Teradata データベース
* Vertica (Beta)

名前の後に **(ベータ)** または **(プレビュー)** と書かれているデータ ソースには、変更される可能性があり、運用での使用はサポートされていません。 **Power BI サービス**にレポートを発行した後はサポートされない可能性もあるので、発行されたレポートを開いたり、データセットを探したりした場合にエラーが発生することがあります。

**(ベータ)** と **(プレビュー)** のデータ ソースの唯一の違いは、使用可能になる前に、**(プレビュー)** のソースはプレビュー機能として有効にする必要があるという点です。 **(プレビュー)** データ コネクタを有効にするには、**Power BI Desktop** で **[ファイル]、[オプションと設定]、****[設定]、[オプション]、[プレビュー機能]** に進みます。

## <a name="on-premises-gateway-requirements"></a>オンプレミス ゲートウェイの要件
次の表では、**Power BI サービス**にレポートを発行した後に、指定したデータ ソースに接続するために、**オンプレミス データ ゲートウェイ**が必要かを示します。

| ソース | ゲートウェイが必要 |
| --- | --- |
| SQL Server |はい |
| Azure SQL Database |いいえ |
| Azure SQL Data Warehouse |いいえ |
| SAP HANA |はい |
| Oracle データベース |はい |
| Teradata データベース |はい |
| Amazon Redshift |いいえ |
| Impala (バージョン 2.x) |はい |
| Snowflake (プレビュー) |現時点では、**Power BI サービス**でサポート対象外 |
| Spark (ベータ) バージョン 0.9 以降 |現時点では、**Power BI サービス**でサポート対象外 |
| Azure HDInsight Spark (Beta) |現時点では、**Power BI サービス**でサポート対象外 |
| IBM Netezza (ベータ) |現時点では、**Power BI サービス**でサポート対象外 |
| SAP Business Warehouse (ベータ) |現時点では、**Power BI サービス**でサポート対象外 |

## <a name="next-steps"></a>次の手順
DirectQuery の詳細については、次のリソースを参照してください。

* [Power BI の DirectQuery](desktop-directquery-about.md)
* [DirectQuery と SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery と SAP BW](desktop-directquery-sap-bw.md)
* [オンプレミス データ ゲートウェイ](service-gateway-onprem.md)

