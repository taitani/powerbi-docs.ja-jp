---
title: "iFrame を使用してレポートを埋め込む"
description: "Power BI レポート サーバー自体のインストールはすぐに終わります。 ダウンロードし、インストールして構成し、実行できるようになるまで、数分で終わります。"
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
ms.date: 11/09/2017
ms.author: asaxton
ms.openlocfilehash: df22a7ed0772979d164a9afae18f4931310ec4a1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>クイック スタート: iFrame と URL パラメーターを使用して Power BI レポートを埋め込む

アプリケーションで iFrame を使用してレポートを埋め込むことができます。 

## <a name="url-parameter"></a>URL パラメーター

レポートの URL の場合、`?rs:Embed=true` のクエリ文字列パラメーターを追加できます。

例:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Power BI Report Server 内のすべてのレポートの種類で使用できます。

## <a name="iframe"></a>iFrame

URL を用意したら、レポートをホストする iFrame を Web ページ内に作成できます。

例:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>URL フィルター

URL にクエリ文字列パラメーターを追加して、レポートに返されたデータをフィルター処理することができます。

構文は簡単です。レポートの URL に疑問符を追加し、その後にこのフィルター構文を追加します。

URL?filter=***<テーブル>***/***<フィールド>*** eq '***<値>***'

次の考慮事項に注意してください。

- **テーブル**と**フィールド**の名前では大文字と小文字が区別されますが、**値**では区別されません。
- レポート ビューに表示されないフィールドを含むレポートをフィルター処理することができます。
- **値**は一重引用符で囲む必要があります。
- フィールドの型は文字列である必要があります。
- テーブルとフィールドの名前にスペースを含めることはできません。

###  <a name="example-filter-on-a-field"></a>例: フィールドをフィルター処理する

[小売の分析のサンプル](../sample-datasets.md)を例として使用します。 次に示すのは、"power-bi" という名前のフォルダーにあるレポート サーバー上のレポートに対する URL であるとします。

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

ノースカロライナや他の州の店舗を示している、小売りの分析のサンプルにマップの視覚エフェクトが表示されます。

![小売りの分析のサンプルにおけるマップの視覚エフェクト](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC* は、**Store** テーブルの **Territory** フィールドに格納されているノースカロライナの値です。 ノースカロライナの店舗のデータだけが表示されるようにレポートをフィルター処理するには、URL に以下を追加します。

?filter=Store/Territory eq 'NC'

これで、レポートはノースカロライナでフィルター処理されます。レポート ページのすべての視覚化には、ノースカロライナのデータだけが表示されます。

![小売りの分析のサンプルにおけるフィルター処理された視覚エフェクト](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>DAX 式を作成して複数の値をフィルター処理する

複数のフィールドにフィルターを適用するもう 1 つの方法は、2 つのフィールドを 1 つの値に連結する Power BI Desktop で計算列を作成することです。 その後は、その値に対してフィルターを適用できます。

たとえば、小売りの分析のサンプルには、2 つのフィールド、Territory と Chain があります。 Power BI Desktop で、TerritoryChain という名前の[計算列 (フィールド) を作成](../desktop-tutorial-create-calculated-columns.md)できます。 **フィールド**名にスペースが含まれてはならないことに注意してください。 その列に DAX 式は次のようになります。

TerritoryChain = [Territory] & "-" & [Chain]

レポートを Power BI Report Server に公開した後、URL クエリ文字列を使って、NC の Lindseys 店のデータだけを表示するようにフィルター処理します。

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>次の手順

[クイックスタート: Power BI レポート サーバーの Power BI レポートの作成](quickstart-create-powerbi-report.md)  
[クイックスタート: Power BI Report Server のページ分割されたレポートの作成](quickstart-create-paginated-report.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。