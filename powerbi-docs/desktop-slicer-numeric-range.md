---
title: "Power BI Desktop で数値範囲スライサーを使用する"
description: "Power BI Desktop で数値範囲を制約するためのスライサーを使用する方法について説明します。"
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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f6e0433e8862e2acb6f0e7a72a1293e37f2185eb
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Power BI Desktop で数値範囲スライサーを使用する
**数値範囲スライサー**を使用して、データ モデルの数値列にあらゆるフィルターを適用することができます。 フィルターの種類は、数値の**範囲**、数値**以下**、数値**以上**から選択できます。 これは単純なようですが、データをフィルターするには非常に強力な方法です。

![](media/desktop-slicer-numeric-range/slicer-numeric-range_2.png)

## <a name="using-the-numeric-range-slicer"></a>数値範囲スライサーの使用
他のスライサーと同じように数値範囲スライサーを使用できます。 レポートの**スライサー** ビジュアルを作成し、**[フィールド]** 値の数値を選択するだけです。 次の図では、*UnitPrice* フィールドが選択されています。

![](media/desktop-slicer-numeric-range/slicer-numeric-range_3.png)

**数値範囲スライサー**の右上隅にあるカラットを選択すると、メニューが表示されます。

![](media/desktop-slicer-numeric-range/slicer-numeric-range_4.png)

数値範囲として、次の 3 つから選択できます。

* 次の値の間
* 次の値以下
* 次の値以上

メニューから **[次の値の間]** を選択すると、スライダーが表示され、対象の数値の間にある数値をフィルターできます。 スライダー バーを使用する以外にも、いずれかのボックス内でクリックし、値を入力することができます。 この方法は、特定の数値全体でスライスする際に、スライサー バーをほんの少しだけ動かして対象の数値に正確に合わせるのが難しい場合に便利です。

次の図のレポート ページでは、500 から 1500 までの範囲の *UnitPrice* 値がフィルターされています。

![](media/desktop-slicer-numeric-range/slicer-numeric-range_5.png)

**[次の値以下]** を選択すると、スライダー バーの左側 (下限) のハンドルが消え、調整できるのはスライダー バーの上限のみとなります。 次の図では、スライダー バーが 497.17 に設定されています。

![](media/desktop-slicer-numeric-range/slicer-numeric-range_6.png)

最後に **[次の値以上]** を選択します。その場合、次の図のように、右側 (上限) のスライダー バーが消え、調整できるのは下限のみとなります。 これで、レポート ページのビジュアルには、*UnitPrice* が 750.56 以上のアイテムのみが表示されます。

![](media/desktop-slicer-numeric-range/slicer-numeric-range_7.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer-preview"></a>数値範囲のスライサーを整数にスナップする (プレビュー)

**Power BI Desktop** の 2018 年 2 月リリースより、数値範囲のスライサーが整数にスナップするようになります。 スライサーで整数がきれいに整列させることができます。 整数へのスナップは小数フィルターには適用されません。


## <a name="limitations-and-considerations"></a>制限事項と考慮事項
現在、**数値範囲スライサー**には次の制限事項と考慮事項が適用されています。

* 現在、**数値範囲スライサー**では、集計値ではなく、データの基になるすべての行がフィルターされます。 たとえば、*Sales Amount* フィールドが使用されている場合、ビジュアルのデータ ポイントごとの *Sales Amount* の合計ではなく、*Sales Amount* に基づく各トランザクションがフィルターされます。
* 現在、メジャーでは動作しません。
* 現在、**Power BI Desktop** で使用できるのは**数値範囲スライサー**のみです。 **数値範囲スライサー**を使用するレポートが **Power BI サービス**に発行された場合でも、フィルターは適用されますが、リスト スライサーとして表示されます。

