---
title: "Power BI Desktop で変数を視覚化する What-if パラメーターを使用する"
description: "独自の What-if 変数を作成し、Power BI レポートの変数を想定して視覚化します"
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 5222b6ba99c9e61d1070f66115b90aa29099fd8d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>Power BI Desktop で変数を視覚化する What-if パラメーターを作成して使用する
2017 年 8 月リリースの **Power BI Desktop** 以降では、レポート用の **What-if** 変数を作成し、スライサーで変数を操作して、レポート内の異なるキー値を視覚化および定量化できます。

![](media/desktop-what-if/what-if_01.png)

**What-if** パラメーターは、**Power BI Desktop** の **[モデリング]** タブにあります。 ダイアログが表示されてパラメーターを構成できます。

## <a name="creating-a-what-if-parameter"></a>What-if パラメーターの作成
**What-if** パラメーターを作成するには、**Power BI Desktop** の **[モデリング]** タブで **[What-If]** ボタンを選びます。 次の図では、*Discount percentage* という名前のパラメーターを作成し、データ型を "*10 進数*" に設定しています。 "*最小値*" は 0、"*最大値*" は 0.50 (50%) です。 また、"*増分*" を 0.05 (5%) に設定してあります。 これはレポートで操作したときのパラメーターの調整量です。

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> 10 進数の場合、".50" だけではなく "0.50" のように先頭のゼロが必要です。 このようにしないと、値が妥当と見なされず、**[OK]** ボタンを選択できません。
> 
> 

使いやすいように、**[このページにスライサーを追加する]** チェック ボックスをオンにすると現在のレポート ページの **What-if** パラメーターにスライサーが自動的に追加されます。

![](media/desktop-what-if/what-if_03.png)

**What-if** パラメーターを作成すると、パラメーターだけでなくメジャーも作成されて、**What-if** パラメーターの現在値を視覚化するために使うことができます。

![](media/desktop-what-if/what-if_04.png)

**What-if** パラメーターを作成すると、パラメーターとメジャーの両方がモデルの一部になるということは重要であり、覚えておくと役に立ちます。 したがって、パラメーターとメジャーをレポート全体および他のレポート ページで使うことができます。 また、モデルに含まれるので、レポート ページから削除したスライサーを元に戻したい場合は、**What-if** パラメーターを **[フィールド]** リストからキャンバスにドラッグしてビジュアルをスライサーに変更するだけで、**What-if** パラメーターをレポートに簡単に戻すことができます。

## <a name="using-a-what-if-parameter"></a>What-if パラメーターの使用
**What-if** パラメーターを使う簡単な例を作成します。 前のセクションでは **What-if** パラメーターを作成しました。ここでは、スライダーで値を調整する新しいメジャーを作成することにより What-if パラメーターを使います。 そのためには、新しいメジャーを作成します。

![](media/desktop-what-if/what-if_05.png)

新しいメジャーは、割引率を適用した合計売上金額を表示するだけの簡単なものです。 もちろん、複雑な興味深いメジャーを作成して、レポートの使用者が **What-if** パラメーターの変数を視覚化できるようにすることができます。 たとえば、販売員が販売目標や割合を達成したときの報酬を表示したり、より大きい割引への売上増加の影響を表示したりするレポートを作成できます。

数式バーにメジャーの式を入力し、**Sales after Discount** という名前にして、結果を表示します。

![](media/desktop-what-if/what-if_06.png)

その後、*OrderDate* を軸にし、*SalesAmount* と作成した *Sales after Discount* メジャーを値にして、縦棒グラフ ビジュアルを作成します。

![](media/desktop-what-if/what-if_07.png)

スライダーを動かすと、*Sales after Discount* の縦棒に割引後の売り上げ高が反映されるのがわかります。

![](media/desktop-what-if/what-if_08.png)

これで完了です。 あらゆる種類の状況で **What-if** パラメーターを使って、レポートのユーザーがレポートのさまざまなシナリオと対話できるようにすることができます。

