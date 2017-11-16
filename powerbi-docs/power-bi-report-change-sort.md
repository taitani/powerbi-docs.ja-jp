---
title: "Power BI レポートでのグラフの並べ替え方法の変更"
description: "Power BI レポートでのグラフの並べ替え方法の変更"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/08/2017
ms.author: mihart
ms.openlocfilehash: 37161fab1e19e6ce00eb0f02c96b6e5cbdd60f18
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI レポートでのグラフの並べ替え方法の変更
Power BI では、カテゴリ名でアルファベット順にグラフを並べ替えたり、各カテゴリの数値を基準に並べ替えたりすることができます。 たとえば、このグラフは店舗名を基準に並べ替えられています。

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

これを、1 平方フィートあたりの売上の高い順に簡単に並べ替えることができます。

1. 省略記号 ([...]) を選び、**[Sort by Sales Per Sq Ft]** (平方フィートごとの売上で並べ替え) を選びます。
2. 必要に応じて、並べ替えアイコン ![](media/power-bi-report-change-sort/sorticon.png) を選んで、**[降順]** に変更します。
   
   ![](media/power-bi-report-change-sort/sortby.gif)
   
   **注**: すべての視覚化が並べ替え可能なわけではありません。  たとえば、以下の視覚化は並べ替えできません: ツリーマップ、マップ、塗り分け地図、散布図、ゲージ、カード、複数行のカード、ウォーターフォール。

## <a name="sorting-using-other-criteria"></a>その他の条件を使用した並べ替え
別のフィールドまたはその他の条件を使用して、ビジュアルを並べ替えたい場合があります。  たとえば、月のアルファベット順ではなく数字順に並べ替えることや、数値を桁ごとにではなく数値全体で比較して (たとえば、0、1、20、9 ではなく、0、1、9、20 の順序で) 並べ替えることができます。  

場合によっては、自由にビジュアルを並べ替えることができます (月別など)。  並べ替えられない場合は、レポートの基になっているデータセットの調整が必要な可能性があります。 これには、いくつかの解決方法があります。

* Power BI Desktop では、[[Data Tools Modeling]](desktop-sort-by-column.md) (データ ツール モデリング) タブを使用して別の列で並べ替えることができます。
* Excel では、自分がデータセットを所有している場合、月の名前と番号を連結した新しい列を追加します。 その後、データセットを最新の情報に更新するか再インポートすれば、[フィールド] 領域に新しい列が表示されます。
* Excel では、数値列に "文字列" ではなく、"整数" や "10 進数" のタグを付けるようにします。

## <a name="next-steps"></a>次の手順
「[Power BI での視覚化](power-bi-report-visualizations.md)」をご覧ください。

[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

