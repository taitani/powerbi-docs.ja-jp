---
title: Power BI のリボン グラフを使用する
description: Power BI サービスと Power BI Desktop でリボン グラフを作成し、使用する
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3400071c6b8cee472bb61475e6d3482189680563
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840107"
---
# <a name="use-ribbon-charts-in-power-bi"></a>Power BI のリボン グラフを使用する
リボン グラフを利用してデータを視覚化し、ランクが最も高い (最大値の) データ カテゴリをすばやく判断できます。 リボン グラフでは、ランクの変化を効果的に確認できます。各期間を対象に、最高位の範囲 (値) が常に一番上に表示されます。 

![リボン グラフ](media/desktop-ribbon-charts/ribbon-charts_01.png)

## <a name="create-a-ribbon-chart"></a>リボン グラフを作成する
作業を進めるために、[小売りの分析のサンプル レポート](../sample-retail-analysis.md)を開きます。 

1. リボン グラフを作成するには、 **[視覚化]** ウィンドウで **[リボン グラフ]** を選択します。

    ![視覚エフェクトのテンプレート](media/desktop-ribbon-charts/power-bi-template.png)

    リボン グラフでは、リボンによりデータのカテゴリがつながり、その連続する時間が視覚化されます。グラフの X 軸 (通常、時系列) 期間全体での特定のカテゴリのランク変化を確認できます。

2. **[軸]** 、 **[凡例]** 、 **[値]** のフィールドを選択します。  この例では、次のように選択しています:**Date**、**Category**、**This year sales**。  

    ![選択されたフィールド](media/desktop-ribbon-charts/power-bi-ribbon-values.png)

    データセットには 1 年間のデータしか格納されていないため、 **[軸]** ウェルから **Year** フィールドを削除しました。 

3. リボン グラフには、1 か月おきのランクが表示されます。 ランクが時間の経過と共にどのように変化するかに注意してください。  たとえば、Home カテゴリは 3 位から 4 位に移動した後、再び 3 位に戻っています。 Juniors カテゴリは、7 月に 3 位から 5 位に移動しています。 

    ![リボン グラフ](media/desktop-ribbon-charts/power-bi-ribbon.png)

## <a name="format-a-ribbon-chart"></a>リボン グラフを書式設定する
リボン グラフを作成するとき、 **[視覚化]** ウィンドウの **[書式]** セクションの書式設定オプションを利用できます。 リボン グラフの書式設定オプションは、積み上げ縦棒グラフのそれと似ています。リボンに固有の追加書式設定オプションがあります。

![[視覚化] ウィンドウのリボン テンプレート](media/desktop-ribbon-charts/power-bi-format-ribbon.png)

リボン グラフのこの書式設定オプションでは、次の項目を調整できます。

* **[間隔]** では、リボン間の間隔を調整できます。 この数値は、列の最大の高さの割合になります。
* **[系列の色を一致させる]** では、リボンの色を系列の色に合わせることができます。 **オフ**に設定した場合、リボンは灰色になります。
* **[透過性]** では、リボンの透明度が指定されます。初期設定は 30 です。
* **[罫線]** では、リボンの上下に濃い色の罫線を引くことができます。 既定では、罫線はオフになっています。

リボン グラフには Y 軸のラベルがないため、データ ラベルを追加したい場合があります。 [書式] ウィンドウで、 **[データ ラベル]** を選択します。 

![データ ラベルの書式オプション](media/desktop-ribbon-charts/power-bi-labels.png)

データ ラベルの書式オプションを設定します。  この例では、テキストの色を白に、小数点以下の桁数を 0 に、表示単位を千に設定しています。 

![[視覚化] ウィンドウのリボン テンプレート](media/desktop-ribbon-charts/power-bi-data-labels.png)

## <a name="next-steps"></a>次の手順

[Power BI の散布図とバブル チャート](power-bi-visualization-scatter.md)

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)