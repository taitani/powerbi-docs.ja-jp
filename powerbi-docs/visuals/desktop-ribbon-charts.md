---
title: Power BI のリボン グラフを使用する
description: Power BI サービスと Power BI Desktop でリボン グラフを作成し、使用する
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/11/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 9241c46c368eba094c075efe42d4989c03979125
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296430"
---
# <a name="use-ribbon-charts-in-power-bi"></a>Power BI のリボン グラフを使用する
リボン グラフを利用してデータを視覚化し、ランクが最も高い (最大値の) データ カテゴリをすばやく判断できます。 リボン グラフでは、ランクの変化を効果的に確認できます。各期間を対象に、最高位の範囲 (値) が常に一番上に表示されます。 

![リボン グラフ](media/desktop-ribbon-charts/ribbon-charts_01.png)

## <a name="create-a-ribbon-chart"></a>リボン グラフを作成する
リボン グラフを作成するには、**[視覚化]** ウィンドウで **[リボン グラフ]** を選択します。

![](media/desktop-ribbon-charts/ribbon-charts_02.png)

リボン グラフでは、リボンによりデータのカテゴリがつながり、その連続する時間が視覚化されます。グラフの X 軸 (通常、時系列) 期間全体での特定のカテゴリのランク変化を確認できます。

## <a name="format-a-ribbon-chart"></a>リボン グラフを書式設定する
リボン グラフを作成するとき、**[視覚化]** ウィンドウの **[書式]** セクションの書式設定オプションを利用できます。 リボン グラフの書式設定オプションは、積み上げ縦棒グラフのそれと似ています。リボンに固有の追加書式設定オプションがあります。

![[視覚化] ウィンドウのリボン テンプレート](media/desktop-ribbon-charts/ribbon-charts_03.png)

リボン グラフのこの書式設定オプションでは、次の項目を調整できます。

* **[間隔]** では、リボン間の間隔を調整できます。 この数値は、列の最大の高さの割合になります。
* **[系列の色を一致させる]** では、リボンの色を系列の色に合わせることができます。 **オフ**に設定した場合、リボンは灰色になります。
* **[透過性]** では、リボンの透明度が指定されます。初期設定は 30 です。
* **[罫線]** では、リボンの上下に濃い色の罫線を引くことができます。 既定では、罫線はオフになっています。

## <a name="next-steps"></a>次の手順

[Power BI の散布図とバブル チャート](power-bi-visualization-scatter.md)

[Power BI での視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)