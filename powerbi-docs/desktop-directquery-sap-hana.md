---
title: "Power BI での SAP HANA 用 DirectQuery"
description: "SAP HANA で DirectQuery を使用する場合の考慮事項"
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
ms.openlocfilehash: d6f863df59d7374c792f1e1ac16db3a04ad99d87
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="directquery-and-sap-hana"></a>DirectQuery と SAP HANA
**SAP HANA** データ ソースへは、**DirectQuery** を使用して直接接続することが可能です。

**SAP HANA** を使用する場合、これへの接続の処理方法のいくつかの側面を理解することが、次のために重要です。

* SAP HANA ビューに、非加算的な方法 (たとえば、単純な合計ではなく、個別のカウントまたは平均) が含まれている場合、結果は想定したものになります。
* 結果のクエリが効率的です。

**[データの取得]** または **[クエリ エディター]** で定義したクエリで集計を実行する場合、**SQL Server** などのリレーショナル ソースの動作を明確にするのに、少し時間を取ると便利です。 次の例では、**[クエリ エディター]** で定義したクエリは、**ProductID** での平均価格を返しています。

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

データが (DirectQuery ではなく) Power BI にインポートされる場合、次の結果になります。

* データは、**[クエリ エディター]** で作成したクエリで定義した集計レベルでインポートされます。 たとえば、製品ごとの平均価格です。 これでは、ビジュアルで使用できる *ProductID* と *AveragePrice* の 2 つの列を持つテーブルが作成されます。
* ビジュアルでは、それ以降のすべての (*Sum*、*Average*、 *Min* などの) 集約は、そのインポートされたデータに対して実行されます。  たとえば、ビジュアルに *AveragePrice* を含めると、既定で *Sum* 集計が使用され、各 *ProductID* の *AveragePrice* の合計 (ここでは 13.67) が返されます。 これは、ビジュアルで使用される (*Min*、*Average* などの) すべての代替の集計関数にも当てはまります。 たとえば、*AveragePrice* の *Average* では、6.66、4、および 3 の平均である 4.56 が返されます。元の表の 6 つのレコードの *Price* の平均 (5.17) では*ありません*。

インポートの代わりに **DirectQuery** を使用した場合、同じセマンティクスが当てはまり、結果はまったく同じになります。

* 同じクエリの場合、データが実際にインポートされない場合でも、論理的に正確に同じデータがレポート層に表示されます。
* ビジュアルでは、それ以降の (*Sum*、*Average*、*Min* などの) すべての集約がクエリの論理テーブルに対して再度実行されます。 ここでも、*AveragePrice* の *Average* を含むビジュアルでは、同様に 4.56 が返されます。

では、**SAP HANA** を考えてみましょう。 Power BI は SAP HANA の、メジャーを含むことができる*分析ビュー*と*計算ビュー*の両方で使用することができます。 しかし、SAP HANA のアプローチは、現在でも前述の同じ原則どおりです。つまり、**[データの取得]** または **[クエリ エディター]** に定義したクエリによって使用可能なデータが決定され、ビジュアル内のそれ以降のすべての集計はそのデータに対して行われます。これは、インポートと DirectQuery の両方に対しても同様です。

ただし、HANA の性質を考えた場合、最初の **[データの取得]** ダイアログまたは **[クエリ エディター]** で定義したクエリは常に集計クエリであり、実際に使用される集計は HANA ビューによって定義されるメジャーを通常含みます。

上の SQL Server と同等な例として、**ID**、**ProductID**、**DepotID** を含む HANA ビューと、ビューで、**Average of Price** として定義されている **AveragePrice** を含むメジャーがあります。

![](media/desktop-directquery-sap-hana/directquery-sap-hana_02.png)

**[データの取得]** エクスペリエンスで **ProductID** と **AveragePrice** メジャー用の選択が行われた場合、それではその集計データを要求するビューに対するクエリが定義されています (上記の例では、簡単にするために HANA SQL の構文と完全に一致しない疑似 SQL を使用しています)。 すると、ビジュアルで定義されている以降の集計は、このようなクエリの結果がさらに集計されます。 **SQL Server** の場合で説明したように、これはインポートおよび DirectQuery の両方の場合に当てはまります。 なお、DirectQuery の場合、**[データの取得]** または **[クエリ エディター]** からのクエリは HANA に送信される 1 つのクエリのサブセレクト内で使用されます。したがって、これでは、さらなる集計の前に、すべてのデータは読み込まれません。

これにより、HANA ではなく DirectQuery を使用した場合、次の重要事項を考慮する必要が生じます。

* HANA のメジャーが非加算的である場合 (たとえば、単純な *Sum**Min* または *Max* ではない場合)、ビジュアルで実行される以降のすべての集計では注意が必要です。
* **[データの取得]** または **[クエリ エディター]** では、必要なデータを取得するのに、必要な列のみを含める必要があります。それは、結果がクエリになるという事実が反映された、HANA に送信可能な妥当なクエリである必要があります。 たとえば、以降のビジュアルで必要になる可能性があるという考えから、列を数十選択した場合、DirectQuery の単純なビジュアルのサブセレクトで使用されている集計クエリにも、それらの数十の行が含まれることを意味します。これは、通常パフォーマンスを非常に低下させます。

例を見てみましょう。 次の例では、**[データの取得]** ダイアログ ボックスで 5 つ列 (CalendarQuarter、Color、LastName、ProductLine、SalesOrderNumber) をメジャー OrderQuantity と共に選択した場合、後で作成する Min OrderQuantity を含む単純なビジュアルには、次の HANA への SQL クエリが含まれることを意味します。 灰色の部分は、**[データの取得]** / **[クエリ エディター]** からのクエリを含むサブセレクトです。 このサブセレクトにより結果の基数が非常に多くなる場合、結果の HANA のパフォーマンスが低下する可能性があります。

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

このため、**[データの取得]** または **[クエリ エディター]** で選択するアイテムは、それが結果として HANA で妥当なクエリとなる、必要なもののみに制限する必要があります。

### <a name="next-steps"></a>次の手順
DirectQuery の詳細については、次のリソースを参照してください。

* [Power BI の DirectQuery](desktop-directquery-about.md)
* [DirectQuery でサポートされるデータ ソース](desktop-directquery-data-sources.md)
* [DirectQuery と SAP BW](desktop-directquery-sap-bw.md)
* [オンプレミス データ ゲートウェイ](service-gateway-onprem.md)

