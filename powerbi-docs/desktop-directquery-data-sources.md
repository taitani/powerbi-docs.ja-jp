---
title: Power BI の DirectQuery でサポートされるデータ ソース
description: DirectQuery を使用できるデータ ソースの一覧を取得します。
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 55d6259c3ae044d395bd0b077577856dd88ff43c
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "34720767"
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
* SAP Business Warehouse Application サーバー
* SAP Business Warehouse メッセージ サーバー (Beta)
* SAP HANA
* Snowflake
* Spark (ベータ) (バージョン 0.9 以降)
* SQL Server
* Teradata データベース
* Vertica (Beta)

名前の後に **(ベータ)** または **(プレビュー)** と書かれているデータ ソースには、変更される可能性があり、運用での使用はサポートされていません。 **Power BI サービス**にレポートを発行した後はサポートされない可能性もあるので、発行されたレポートを開いたり、データセットを探したりした場合にエラーが発生することがあります。

**(ベータ)** と **(プレビュー)** のデータ ソースの唯一の違いは、使用可能になる前に、**(プレビュー)** のソースはプレビュー機能として有効にする必要があるという点です。 **(プレビュー)** データ コネクタを有効にするには、**Power BI Desktop** で **[ファイル]、[オプションと設定]、** の順に進み、**[プレビュー機能]** を選択します。

> [!NOTE]
> SQL Server への DirectQuery クエリでは、アクセスを確立するために、現在の Windows 認証資格情報またはデータベース資格情報を使って認証を行うが必要があります。 代替資格情報はサポートされていません。
>

## <a name="on-premises-gateway-requirements"></a>オンプレミス ゲートウェイの要件
次の表では、**Power BI サービス**にレポートを発行した後に、指定したデータ ソースに接続するために、**オンプレミス データ ゲートウェイ**が必要かを示します。

| Source | ゲートウェイが必要 |
| --- | --- |
| SQL Server |はい |
| Azure SQL Database |いいえ |
| Azure SQL Data Warehouse |いいえ |
| SAP HANA |はい |
| Oracle データベース |はい |
| Teradata データベース |はい |
| Amazon Redshift |いいえ |
| Impala (バージョン 2.x) |はい |
| Snowflake |はい |
| Spark (ベータ) バージョン 0.9 以降 |現時点では、**Power BI サービス**でサポート対象外 |
| Azure HDInsight Spark (Beta) |いいえ |
| IBM Netezza |はい |
| SAP Business Warehouse Application サーバー |はい |
| SAP Business Warehouse メッセージ サーバー |現時点では、**Power BI サービス**でサポート対象外 |
| Google BigQuery |いいえ |


## <a name="next-steps"></a>次の手順
DirectQuery の詳細については、次のリソースを参照してください。

* [Power BI の DirectQuery](desktop-directquery-about.md)
* [DirectQuery と SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery と SAP BW](desktop-directquery-sap-bw.md)
* [オンプレミス データ ゲートウェイ](service-gateway-onprem.md)

