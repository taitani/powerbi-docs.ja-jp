---
title: Power BI の DirectQuery でサポートされるデータ ソース
description: DirectQuery を使用できるデータ ソースの一覧を取得します。
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/31/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: dae93a2555101a42f072158f8536319783b3f973
ms.sourcegitcommit: aef57ff94a5d452d6b54a90598bd6a0dd1299a46
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "66809116"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Power BI の DirectQuery でサポートされるデータ ソース

**Power BI Desktop** と **Power BI サービス**には、接続してデータへのアクセスを可能にする多数のデータ ソースがあります。 この記事では、Power BI のどのデータ ソースが **DirectQuery** と呼ばれる接続方法をサポートしているかを説明します。 DirectQuery の詳細については、「[**Power BI での DirectQuery**](desktop-directquery-about.md)」を参照してください。

次のデータ ソースは、Power BI で DirectQuery をサポートしています。

* Amazon Redshift
* AtScale (ベータ)
* Azure Data Explorer
* Azure HDInsight Spark
* [Azure SQL Database](service-azure-sql-database-with-direct-connect.md)
* [Azure SQL Data Warehouse](service-azure-sql-data-warehouse-with-direct-connect.md)
* Google BigQuery
* HDInsight 対話型クエリ
* IBM DB2 データベース
* IBM Netezza
* Impala (バージョン 2.x)
* Oracle データベース (バージョン 12 以降)
* Oracle Essbase
* SAP Business Warehouse Application サーバー
* SAP Business Warehouse メッセージ サーバー
* SAP HANA
* Snowflake
* Spark (バージョン 0.9 以降)
* SQL Server
* Teradata データベース
* Vertica

名前の後に **(ベータ)** または **(プレビュー)** と書かれているデータ ソースは、変更される可能性があり、運用環境での使用はサポートされていません。 **Power BI サービス**にレポートを発行した後はサポートされない可能性もあるので、発行されたレポートを開いたり、データセットを探したりした場合にエラーが発生することがあります。

**(ベータ)** と **(プレビュー)** のデータ ソースの唯一の違いは、使用可能になる前に、 **(プレビュー)** のソースはプレビュー機能として有効にする必要があるという点です。 **(プレビュー)** データ コネクタを有効にするには、**Power BI Desktop** で **[ファイル]、[オプションと設定]、** の順に進み、 **[プレビュー機能]** を選択します。

> [!NOTE]
> SQL Server への DirectQuery クエリでは、アクセスを確立するために、現在の Windows 認証資格情報またはデータベース資格情報を使って認証を行うが必要があります。 代替資格情報はサポートされていません。
>

## <a name="on-premises-gateway-requirements"></a>オンプレミス ゲートウェイの要件
次の表では、**Power BI サービス**にレポートを発行した後に、指定したデータ ソースに接続するために、**オンプレミス データ ゲートウェイ**が必要かを示します。

| Source | ゲートウェイが必要 |
| --- | --- |
| Amazon Redshift |いいえ |
| Azure HDInsight Spark (Beta) |いいえ |
| Azure SQL Database |いいえ |
| Azure SQL Data Warehouse |いいえ |
| Google BigQuery |いいえ |
| IBM Netezza |はい |
| Impala (バージョン 2.x) |はい |
| Oracle データベース |はい |
| SAP Business Warehouse Application サーバー |はい |
| SAP Business Warehouse メッセージ サーバー |現時点では、**Power BI サービス**でサポート対象外 |
| SAP HANA |はい |
| Snowflake |はい |
| Spark (ベータ) バージョン 0.9 以降 |はい |
| SQL Server |はい |
| Teradata データベース |はい |

## <a name="single-sign-on-sso-for-directquery-sources"></a>DirectQuery ソースのシングル サインオン (SSO)

SSO オプションが有効になっている場合、データ ソースを基に作成されたレポートにユーザーがアクセスすると、Power BI によって基になるデータ ソースへのクエリで、認証済みの Azure AD 資格情報が送信されます。 これにより、Power BI はデータ ソース レベルで構成されているセキュリティ設定を適用できます。

SSO オプションは、このデータ ソースを使うすべてのデータセットで有効になります。 インポートのシナリオに使われる認証方法には影響しません。 次のデータ ソースでは、DirectQuery 経由の接続で SSO をサポートします。

- Azure SQL Database
- Azure SQL Data Warehouse
- Impala
- SAP HANA
- SAP BW
- Spark
- SQL Server
- Teradata

> [!Note]
> Azure Multi-Factor Authentication (MFA) はサポートされていません。 DirectQuery で SSO を使用する必要があるユーザーは、MFA から除外する必要があります。

## <a name="next-steps"></a>次の手順
DirectQuery の詳細については、次のリソースを参照してください。

* [Power BI の DirectQuery](desktop-directquery-about.md)
* [DirectQuery と SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery と SAP BW](desktop-directquery-sap-bw.md)
* [オンプレミス データ ゲートウェイ](service-gateway-onprem.md)

