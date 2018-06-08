---
title: Power BI レポートでのグラフの並べ替え方法の変更
description: Power BI レポートでのグラフの並べ替え方法の変更
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3c32fc3cc9dc2b16384016ca624d4dd3a773aacb
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34561795"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI レポートでのグラフの並べ替え方法の変更
Power BI レポートのほとんどの視覚エフェクトは、グラフ内のカテゴリ名のアルファベット順や、各カテゴリの数値順に、並べ替えることができます。 たとえば、このグラフは店舗名を基準に並べ替えられています。

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

カテゴリ (店舗名) から値 (平方フィートごとの売上) に、並べ替えの基準を簡単に変更できます。

1. 省略記号 ([...]) を選び、**[Sort by Sales Per Sq Ft]** (平方フィートごとの売上で並べ替え) を選びます。
2. 必要に応じて、並べ替えアイコン ![](media/power-bi-report-change-sort/sorticon.png) を選んで、**[降順]** に変更します。

   ![](media/power-bi-report-change-sort/sortby.gif)

   **注**: すべての視覚化が並べ替え可能なわけではありません。  たとえば、以下の視覚化は並べ替えできません: ツリーマップ、マップ、塗り分け地図、散布図、ゲージ、カード、複数行のカード、ウォーターフォール。

## <a name="saving-changes-you-make-to-sort-order"></a>並べ替え順序の変更を保存する
Power BI レポートでは、フィルター、スライサー、並べ替え、その他のデータ ビューに行った変更が保存されます。 そのため、レポートを終了し後で戻ったときに、変更が保存されています。  レポート作成者の設定に戻す場合、一番上のメニュー バーから **[既定値にリセット]** を選択してください。 

![永続的な並べ替え](media/power-bi-report-change-sort/power-bi-reset-to-default.png)

ただし、**[既定値にリセット]** ボタンが淡色表示になっている場合、変更を保存する (永続化する) 機能をレポート作成者が無効にしています。

<a name="other"></a>
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
