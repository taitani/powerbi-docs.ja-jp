---
title: Power BI における色の書式設定に関するヒントとコツ
description: Power BI における色の書式設定に関するヒントとコツ
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/09/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 71ed70344281dec3353b73c8698594d62ef32eae
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285601"
---
# <a name="tips-and-tricks-for-color-formatting-in-power-bi"></a>Power BI における色の書式設定に関するヒントとコツ
Power BI は、ダッシュボードとレポートをカスタマイズするためのさまざまな方法を提供しています。 この記事では、Power BI の視覚化を、説得力のある興味をひくものにして、お客様のニーズに合わせてカスタマイズできる各種ヒントについて詳しく説明しています。

ヒントには次のものがあります。 優れた別のヒントをお持ちですか。 それは素晴らしいことです。 そのヒントを是非マイクロソフトまでお送りください。この一覧への追加を検討させていただきます。

* 1 つのデータ ポイントの色を変更する
* グラフの色を 1 つの数値に基づいて決める
* データ ポイントの色を 1 つのフィールドの値に基づいて決める
* カラー スケールで使用する色をカスタマイズする
* 左右逆方向のカラー スケールを使用する
* Power BI で元に戻す方法

変更を行うには、レポートを編集している必要があります。 レポートを開き、次の図のように上部のメニュー領域で **[レポートの編集]** を選択します。

![](media/service-tips-and-tricks-for-color-formatting/power-bi-edit.png)

**[視覚化]** ウィンドウが **[レポート]** キャンバスの右側に表示されたら、カスタマイズを開始できます。 ウィンドウが表示されない場合は、右上隅の矢印を選択して開きます。

![](media/service-tips-and-tricks-for-color-formatting/power-bi-formatting-pane.png)

## <a name="change-the-color-of-a-single-data-point"></a>1 つのデータ ポイントの色を変更する
特定の 1 つのデータ ポイントを強調表示したい場合があります。 このようなデータ ポイントには、発売した新製品の売上高や、新しい計画が開始した後に向上した品質のスコアなどがあります。 Power BI を使用すれば、特定のデータ ポイントの色を変更することで、それを強調表示できます。

次の視覚エフェクトでは、製品区分別に販売されたユニット数がランク付けされています。 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-grey.png)

ここで、**Convenience** 区分を取り出して、この新しい区分のパフォーマンスを色を使用して示すものとします。 この手順を以下に示します。

**[データの色]** セクションを展開し、**[すべて表示]** のスライダーをオンにします。 これにより、視覚化内の各データ要素の色が表示されます。 データ ポイントにポインターを合わせるとスクロールが有効になり、任意のデータ ポイントを変更できるようになります。

![](media/service-tips-and-tricks-for-color-formatting/power-bi-show-all.png)

**Convenience** をオレンジ色に設定します。 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-orange.png)

選択すると、**Convenience** のデータ ポイントがオレンジの網掛けになり、確実に目立ちます。

視覚化の種類を変更してから処理を終了した場合でも、Power BI では選んだ内容が記憶され、 **Convenience** をオレンジのままに保ちます。

視覚エフェクトの 1 つ、複数、またはすべてのデータ要素について、データ ポイントの色を変更できます。 おそらく、企業の色に似たビジュアルにしたいのではないですか。 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-corporate.png)

色を使用すると、さまざまなことを行えます。 次のセクションでは、グラデーションを確認してみましょう。

## <a name="base-the-colors-of-a-chart-on-a-numeric-value"></a>グラフの色を 1 つの数値に基づいて決める
あるフィールドの数値に基づいてグラフの色を動的に設定すると役立つ場合がよくあります。 このように色を設定すると、1 つの横棒のサイズに使用された値とは異なる値を示して、1 つのグラフに 2 つの値を表示できます。 また、このような設定を使用して、特定の値の上 (または下) のデータ ポイントを強調表示することもできます (低い収益性の領域を強調表示するような場合)。

次のセクションでは、ある数値に基づいて色を決めるためのさまざまな方法を示します。

## <a name="base-the-color-of-data-points-on-a-value"></a>データ ポイントの色を 1 つの値に基づいて決める
1 つの値に基づいて色を変更するには、色の基準となるフィールドを、**[フィールド]** ウィンドウの **[色の彩度]** 領域にドラッグします。 次の図では、**%Market Share SPLY YTD** が **[色の彩度]** にドラッグされています。 

![](media/service-tips-and-tricks-for-color-formatting/power-bi-color-saturation.png)

また、[書式] ウィンドウの **[データの色]** で、縦棒グラフでの **%Market Share SPLY YTD** の値による色と網掛けの変更方法を決定します。 この例では、%Market Share の値が小さいほど明るい青、大きいほど濃い青になります。


![](media/service-tips-and-tricks-for-color-formatting/power-bi-data-colors2.png)


見ると分かるように、販売されたユニット数では **Productivity** と **Extreme** の方が多くなっていますが (棒が高い)、**%Market Share SPLY YTD** では **Moderation** の方が多くなっています (色が濃い)。

![](media/service-tips-and-tricks-for-color-formatting/power-bi-saturation.png)

## <a name="customize-the-colors-used-in-the-color-scale"></a>カラー スケールで使用する色をカスタマイズする
カラー スケールで使用する色もカスタマイズすることができます。 既定では、データ内の最小値が最も低い彩度の色にマップされ、最大値が最も彩度の高い色にマップされます。 上の図では、青のグラデーションを使用しました。 

**[データの色]** を展開すると、データの視覚化に使用する色のグラデーションが表示されます。 色の範囲は、 **[最小]** と **[最大]** の色の値の間にスペクトルが表示されるグラデーション バーに示され、 **最小** 値の色が左側、 **最大** 値の色が右側になります。

![](media/service-tips-and-tricks-for-color-formatting/power-bi-data-colors2.png)


異なる範囲の色を使用するためにスケールを変更するには、 **[最小]** または **[最大]** の横にある色のドロップダウンを選んでから、色を選びます。 次の図では、黒に変更された **[最大]** の色が示され、グラデーション バーには、**[最小]** と **[最大]** の間に新しい色のスペクトルが示されています。

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_11.png)

また、値をこれらの色にマップする方法を変更することもできます。 次の図では、 **[最小]** と **[最大]** の色がオレンジ色と緑に、それぞれ設定されています。

この最初の図で、横棒に示されたグラデーションがどのようにグラフの縦棒に反映されているかにご注目ください。つまり、最大値が緑、最小値がオレンジ色で、それらの間の各縦棒は、緑とオレンジ色の間のスペクトルの網掛けで色が設定されています。

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_12.png)

ここで、**[最小]** と **[最大]** の各値ボックスに数値を指定した場合にどうなるか見てみましょう。これらのボックスは、**[最小]** と **[最大]** の各色セレクターの下にあります (次の図を参照)。 **[最小]** を 20,000,000 に設定し、**[最大]** を 20,000,001 に設定してみましょう。

これらの値を設定すると、**[最小]** よりも低いか、または **[最大]** よりも高いグラフの値には、グラデーションが適用されなくなります。つまり、**[最大]** 値よりも高い値を持つすべての縦棒には緑、**[最小]** 値よりも低い値を持つすべての縦棒には赤が設定されます。

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_13.png)

## <a name="use-diverging-color-scales"></a>左右逆方向のカラー スケールを使用する
データに、もともと左右逆方向の尺度がある場合があります。 たとえば、温度の範囲には氷点に中央があり、収益性スコアには中間点 (ゼロ) があります。

左右逆方向のカラー スケールを使用するには、 **[左右逆方向]** スライダーを **[オン]** にスライドさせます。 **[左右逆方向]** がオンの場合、追加のカラー セレクターと値ボックス (ともに **[中央]** という) が次の図のように表示されます。

![](media/service-tips-and-tricks-for-color-formatting/tipstrickscolor_14.png)

**[左右逆方向]** スライダーがオンの場合、 **[最小]**、 **[最大]** 、および **[中央]** の色を別々に設定することができます。 次の図では、 **[中央]** が 1 に設定されているため、1 を超える値を持つ縦棒は緑のグラデーションの網かけ、1 を下回縦棒は赤の網かけになります。

## <a name="how-to-undo-in-power-bi"></a>Power BI で元に戻す方法
他の多くの Microsoft のサービスやソフトウェアと同様に、Power BI には、最後のコマンドを元に戻すための簡単な方法が備わっています。 たとえば、データ ポイントの色または一連のデータ ポイントを変更した場合に、それらが視覚化に表示されるときの色が好みでない場合があります。 そして、前にどの色だったか正確には思い出せないけれども、その色に戻したいことがあります。

直前の操作または最近のいくつか操作を **元に戻す** には、次の操作を行うだけです。

- CTRL + Z を入力します

## <a name="feedback"></a>フィードバック
共有したいヒントがありますか? そのヒントを是非マイクロソフトまでお送りください。このページに記載することを検討させていただきます。

>[!NOTE]
>上記の色、軸、関連するカスタマイズは、**[書式]** アイコンが選ばれている場合に使用できます。また、Power BI Desktop でも使用できます。

## <a name="next-steps"></a>次の手順
[色の書式設定と軸のプロパティの概要](service-getting-started-with-color-formatting-and-axis-properties.md)

