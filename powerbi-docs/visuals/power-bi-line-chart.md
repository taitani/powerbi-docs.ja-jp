---
title: Power BI の折れ線グラフ
description: Power BI の折れ線グラフ
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 0654dccf55b1e13f26d8ecaabee0349f0e56afc6
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65535792"
---
# <a name="line-charts-in-power-bi"></a>Power BI の折れ線グラフ
折れ線グラフは、一連のデータ ポイントをドットで表され、直線で接続されているのです。 折れ線グラフで、1 つまたは複数の行があります。 折れ線グラフでは、X と Y 軸があります。 

![単純な折れ線グラフ](media/power-bi-line-charts/power-bi-line.png)

## <a name="create-a-line-chart"></a>折れ線グラフを作成します。
これらの手順の使用、販売とマーケティングのサンプル アプリをカテゴリ別の今年の売上を表示する折れ線グラフを作成します。 作業を進めるには、appsource.com からサンプル アプリを取得します。

1. 空のレポート ページで開始します。 Power BI サービスを使っている場合は、[編集ビュー](../service-interact-with-a-report-in-editing-view.md)でレポートを開いていることを確認します。

2. フィールド ウィンドウで、次のように選択します。 **SalesFact** \> **ユニット数**、選択および**日付** > **月**します。  Power BI では、レポート キャンバスに縦棒グラフを作成します。

    ![[フィールド] ウィンドウから選択します](media/power-bi-line-charts/power-bi-step1.png)

4. [視覚化] ウィンドウから線グラフ テンプレートを選択して、折れ線グラフに変換します。 

    ![折れ線グラフに変換します。](media/power-bi-line-charts/power-bi-convert-to-line.png)
   

4. 2012-2014 年のデータを表示する棒グラフをフィルター処理します。 [フィルター] ウィンドウが折りたたまれている場合は、今すぐ展開します。 フィールド ウィンドウで、次のように選択します。**日付** \> **年**フィルター ペインにドラッグします。 見出しの下にドロップ**このビジュアルにフィルター**します。 
     
    ![[フィールド] ウィンドウの横にある行](media/power-bi-line-charts/power-bi-year-filter.png)

    変更**フィルターを高度な**に**基本的なフィルター**選択**2012**、 **2013**と**2014**します。

    ![年のフィルター](media/power-bi-line-charts/power-bi-filter-year.png)

6. 必要に応じて、[グラフのテキストの色とサイズを調整](power-bi-visualization-customize-title-background-and-legend.md)します。 

    ![フォント サイズを大きくと、Y axisfont の変更](media/power-bi-line-charts/power-bi-line-3years.png)

## <a name="add-additional-lines-to-the-chart"></a>グラフに行を追加します。
折れ線グラフでは、多くの異なる行を持つことができます。 また、場合によってで、行の値が、うまく連携表示しないように異なる可能性があります。 現行の追加の行がします線で表された値が非常に異なる場合、グラフの書式を設定する方法を学習し、グラフを追加することを見てみましょう。 

### <a name="add-additional-lines"></a>行を追加します。
グラフ上の単一行としてすべてのリージョンの合計ユニット数を調べる代わりリージョン別の合計ユニットを分割してみましょう。 ドラッグして行を追加する**Geo** > **リージョン**凡例有効にします。

   ![地域ごとに 1 つの行](media/power-bi-line-charts/power-bi-line-regions.png)


### <a name="use-two-y-axes"></a>2 つの Y 軸を使用します。
What-if 売上合計と合計ユニット数を同じグラフを確認しますか。 販売数が折れ線グラフで表示を使用できないため、ユニットの番号よりもはるかに高くなります。 実際には、0 を合計ユニット数の赤色の線が表示されます。

   ![値が高い分岐](media/power-bi-line-charts/power-bi-diverging.png)

高度に左右逆方向の値を 1 つのグラフに表示するには、複合グラフを使用します。 読み取りでの複合グラフのすべてについて学習できます[Power BI での複合グラフ](power-bi-visualization-combo-chart.md)します。 、次の例でおできますいっしょに表示販売と合計ユニット 1 つのグラフに 2 番目の Y 軸を追加することで。 

   ![値が高い分岐](media/power-bi-line-charts/power-bi-dual-axes.png)

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
* 1 つの折れ線グラフは、2 つの Y 軸を持つことはできません。  複合グラフを代わりに使用する必要があります。
* 上記の例で、グラフの形式にフォント サイズを大きく、フォントの色を変更、軸のタイトルを追加、グラフのタイトルと凡例を中央揃え、0、その他の両方の軸を開始します。 書式設定ウィンドウ (ペイント ローラー アイコン) には、無限に方法、グラフの外観を行うためのオプションのセットがあります。 学習する最善の方法では、書式設定ウィンドウを開き、探索します。

## <a name="next-steps"></a>次の手順

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)


