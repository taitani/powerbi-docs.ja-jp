---
title: "Power BI Desktop でジェネリック インターフェイスを使用してデータに接続する"
description: "Power BI Desktop でジェネリック インターフェイスを使用して異なるデータ ソースに接続する方法を説明します"
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: 2083343e8642470b8eb21bf13ba75fe784351b1c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-data-using-generic-interfaces-in-power-bi-desktop"></a>Power BI Desktop でジェネリック インターフェイスを使用してデータに接続する
**Power BI Desktop** では、**[データの取得]** ウィンドウに表示されるように、**Access データベース**から **Zendesk** まで広範にカバーする組み込みデータ接続を使用して、さまざまな異なるデータ ソースに接続できます。 また、**Power BI Desktop** に組み込まれているジェネリック インターフェイス (**ODBC** や **REST API** など) を使うことで、*その他*のあらゆる種類のデータ ソースに接続でき、接続オプションの範囲が大きく広がります。

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_1.png)

## <a name="power-bi-desktop-data-interfaces"></a>Power BI Desktop のデータ インターフェイス
**Power BI Desktop** に含まれる、特定のデータ ソースに接続するために作成されたデータ コネクタのコレクションは増え続けています。 たとえば、**SharePoint リスト**のデータ コネクタは、**SharePoint リスト**向けに設計された接続シーケンスの間に特定のフィールドとサポート情報を提供します。**[データの取得] > [その他]** を選択すると表示されるウィンドウの他のデータ ソースについても同様です (上図を参照)。

さらに、**Power BI Desktop** では、以下のジェネリック データ インターフェイスのいずれかを使うことで、**[データの取得]** の一覧には具体的に示されていないデータ ソースにも接続できます。

* **ODBC**
* **OLE DB**
* **OData**
* **REST API**
* **R スクリプト**

これらのジェネリック インターフェイスで提供される接続ウィンドウの適切なパラメーターにより、**Power BI Desktop** でアクセスして使用できるデータ ソースの範囲が大きく広がります。

以下のセクションでは、これらのジェネリック インターフェイスでアクセスできるデータ ソースの一覧を示します。

**Power BI Desktop** で使いたいデータ ソースが見つからない場合は、 [ご連絡](https://ideas.powerbi.com/)をいただければ、アイデアとご要望の一覧に追加します。

## <a name="data-sources-accessible-through-odbc"></a>ODBC でアクセスできるデータ ソース
**Power BI Desktop** の **ODBC** コネクタを使うと、**データ ソース名 (DSN)** または*接続文字列*を指定するだけで、任意のサードパーティ製 ODBC ドライバーから簡単にデータをインポートできます。 必要であれば、ODBC ドライバーに対して SQL ステートメントを実行することもできます。

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_2.png)

次の一覧では、ジェネリック **ODBC** インターフェイスを使って **Power BI Desktop** が接続できるいくつかのデータ ソースの詳細な例を示します。

| Power BI Desktop のジェネリック コネクタ | 外部データ ソース | 詳細情報のリンク |
| --- | --- | --- |
| ODBC |Cassandra |[Cassandra ODBC ドライバー](http://www.simba.com/drivers/cassandra-odbc-jdbc/) |
| ODBC |Couchbase DB |[Couchbase と Power BI](https://powerbi.microsoft.com/en-us/blog/visualizing-data-from-couchbase-server-v4-using-power-bi/) |
| ODBC |DynamoDB |[DynamoDB ODBC ドライバー](http://www.simba.com/drivers/dynamodb-odbc-jdbc/) |
| ODBC |Google BigQuery |[BigQuery ODBC ドライバー](http://www.simba.com/drivers/bigquery-odbc-jdbc/) |
| ODBC |Hbase |[Hbase ODBC ドライバー](http://www.simba.com/drivers/hbase-odbc-jdbc/) |
| ODBC |Hive |[Hive ODBC ドライバー](http://www.simba.com/drivers/hive-odbc-jdbc/) |
| ODBC |IBM Netezza |[IBM Netezza の情報](https://www.ibm.com/support/knowledgecenter/SSULQD_7.2.1/com.ibm.nz.datacon.doc/c_datacon_plg_overview.html) |
| ODBC |Presto |[Presto ODBC ドライバー](http://www.simba.com/drivers/presto-odbc-jdbc/) |
| ODBC |Project Online |[Project Online の記事](desktop-project-online-connect-to-data.md) |
| ODBC |Progress OpenEdge |[Progress OpenEdge ODBC ドライバーのブログ投稿](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.progress.com%2Fblogs%2Fconnect-microsoft-power-bi-to-openedge-via-odbc-driver&data=02%7C01%7CMatt.Masson%40microsoft.com%7C5e63742e6c454308b58a08d4034b5923%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636137069555329811&sdata=gSu2Rq3vZ0uBVOgjaXxd8Y3uBf%2B8DidX6PG33jwAduY%3D&reserved=0) |

## <a name="data-sources-accessible-through-ole-db"></a>OLE DB でアクセスできるデータ ソース
**Power BI Desktop** の **OLE DB** コネクタを使うと、*接続文字列*を指定するだけで、任意のサードパーティ製 OLE DB ドライバーから簡単にデータをインポートできます。 必要であれば、OLE DB ドライバーに対して SQL ステートメントを実行することもできます。

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_3.png)

次の一覧では、ジェネリック **OLE DB** インターフェイスを使って **Power BI Desktop** が接続できるいくつかのデータ ソースの詳細な例を示します。

| Power BI Desktop のジェネリック コネクタ | 外部データ ソース | 詳細情報のリンク |
| --- | --- | --- |
| OLE DB |SAS OLE DB |[SAS Provider for OLE DB](https://support.sas.com/downloads/package.htm?pid=648) |
| OLE DB |Sybase OLE DB |[Sybase Provider for OLE DB](http://infocenter.sybase.com/help/index.jsp?topic=/com.sybase.infocenter.dc35888.1550/doc/html/jon1256941734395.html) |

## <a name="data-sources-accessible-through-odata"></a>OData でアクセスできるデータ ソース
**Power BI Desktop** の **OData** コネクタを使うと、**OData** の URL を入力するか貼り付けるだけで、任意の **OData** URL からデータをインポートできます。 **[OData フィード]** ウィンドウのテキスト ボックスにリンクを入力するか貼り付けることにより、URL の複数の部分を追加できます。

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_4.png)

次の一覧では、ジェネリック **OData** インターフェイスを使って **Power BI Desktop** が接続できるいくつかのデータ ソースの詳細な例を示します。

| Power BI Desktop のジェネリック コネクタ | 外部データ ソース | 詳細情報のリンク |
| --- | --- | --- |
| OData |近日公開予定 |後で確認してください |

## <a name="data-sources-accessible-through-rest-apis"></a>REST API でアクセスできるデータ ソース
**REST API** を使ってデータ ソースに接続し、**REST** をサポートするあらゆる種類のデータ ソースのデータを使用できます。

![](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_5.png)

次の一覧では、ジェネリック **REST API** インターフェイスを使って **Power BI Desktop** が接続できるいくつかのデータ ソースの詳細な例を示します。

| Power BI Desktop のジェネリック コネクタ | 外部データ ソース | 詳細情報のリンク |
| --- | --- | --- |
| REST API |Couchbase DB |[Couchbase REST API の情報](https://powerbi.microsoft.com/en-us/blog/visualizing-data-from-couchbase-server-v4-using-power-bi/) |

## <a name="data-sources-accessible-through-r-script"></a>R スクリプトでアクセスできるデータ ソース
**R スクリプト**を使ってデータ ソースにアクセスし、**Power BI Desktop** でそのデータを使うことができます。

![](media/desktop-connect-using-generic-interfaces/r-scripts-2.png)

次の一覧では、ジェネリック **R スクリプト** インターフェイスを使って **Power BI Desktop** が接続できるいくつかのデータ ソースの詳細な例を示します。

| Power BI Desktop のジェネリック コネクタ | 外部データ ソース | 詳細情報のリンク |
| --- | --- | --- |
| R スクリプト |SAS ファイル |[CRAN からの R スクリプトのガイダンス](https://cran.r-project.org/doc/manuals/R-data.html) |
| R スクリプト |SPSS ファイル |[CRAN からの R スクリプトのガイダンス](https://cran.r-project.org/doc/manuals/R-data.html) |
| R スクリプト |R 統計ファイル |[CRAN からの R スクリプトのガイダンス](https://cran.r-project.org/doc/manuals/R-data.html) |

## <a name="next-steps"></a>次の手順
Power BI Desktop を使用して接続できるデータ ソースの種類は他にもあります。 データ ソースの詳細については、次のリソースを参照してください。

* [Power BI Desktop の概要](desktop-getting-started.md)
* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop で Excel ブックに接続する](desktop-connect-excel.md)   
* [Power BI Desktop にデータを直接入力する](desktop-enter-data-directly-into-desktop.md)   

