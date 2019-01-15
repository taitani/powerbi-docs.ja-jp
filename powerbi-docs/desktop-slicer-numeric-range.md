---
title: Power BI Desktop で数値範囲スライサーを使用する
description: Power BI Desktop で数値範囲を制約するためのスライサーを使用する方法について説明します。
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 68467894850248d6acb841dc2ed651f595f19b95
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54287050"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Power BI Desktop で数値範囲スライサーを使用する
**数値範囲スライサー**を使用して、データ モデルの数値列にあらゆるフィルターを適用することができます。 フィルターの種類は、数値の**範囲**、数値**以下**、数値**以上**から選択できます。 これは単純なようですが、データをフィルターするには非常に強力な方法です。

![数値範囲スライサーがあるビジュアル](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="using-the-numeric-range-slicer"></a>数値範囲スライサーの使用
他のスライサーと同じように数値範囲スライサーを使用できます。 レポートの**スライサー** ビジュアルを作成し、**[フィールド]** 値の数値を選択するだけです。 次の図では、*LineTotal* フィールドが選択されています。

![数値範囲スライサーの作成](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

**数値範囲スライサー**の右上隅にある下向き矢印のリンクを選択すると、メニューが表示されます。

![数値範囲スライサー メニュー](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

数値範囲として、次の 3 つから選択できます。

* 次の値の間
* 次の値以下
* 次の値以上

メニューから **[次の値の間]** を選択すると、スライダーが表示され、対象の数値の間にある数値をフィルターできます。 スライダー バーを使用する以外にも、いずれかのボックス内でクリックし、値を入力することができます。 この方法は、特定の数値でスライスする際に、スライサー バーをほんの少しだけ動かして対象の数値に正確に合わせるのが難しい場合に便利です。

次の図のレポート ページでは、2500.00 から 6000.00 までの範囲の *LineTotal* 値がフィルターされています。

![[次の値の間] を使用した数値範囲スライサー](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

**[次の値以下]** を選択すると、スライダー バーの左側 (下限) のハンドルが消え、調整できるのはスライダー バーの上限のみとなります。 次の図では、スライダー バーが最大の 5928.19 に設定されています。

![[次の値以下] を使用した数値範囲スライサー](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

最後に **[次の値以上]** を選択します。その場合、次の図のように、右側 (上限) のスライダー バーが消え、調整できるのは下限のみとなります。 これで、レポート ページのビジュアルには、*LineTotal* が 4902.99 以上のアイテムのみが表示されます。

![[次の値以上] を使用した数値範囲スライサー](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>数値範囲スライサーを整数にスナップする

基礎とするフィールドのデータ型が**整数**の場合、数値範囲スライサーは整数にスナップします。 スライサーで整数がきれいに整列させることができます。 **10 進数**型のフィールドでは、ある数の分数を入力または選択できます。 数値をさらに正確に入力または選択できますが、テキスト ボックスに適用される書式設定は、フィールドに設定されている書式設定に一致します。

## <a name="display-formatting-with-the-date-range-slicer"></a>日付範囲スライサーによる表示書式設定

スライサーを使用して日付範囲を表示または設定すると、日付の形式は常に、ユーザーのブラウザーやオペレーティング システム ロケールに基づき、**[短い日付]** 形式を利用して表示されます。 基になるデータやモデルのデータ型設定に関係なく、これが表示形式になります。 

たとえば、基礎になるデータ型の日付形式が "長い日付" の場合 ("*dddd, MMMM d, yyyy*" など)、他のビジュアルや状況では日付が "*Wednesday, March 14, 2001*" のように書式設定されますが、日付範囲スライサーでは、"*03/14/2001*" のようにスライサーに表示されます。

スライサーで **[短い日付]** 形式を表示することで、文字列の長さに一貫性が与えられ、スライサー内でコンパクトに収まります。 


## <a name="limitations-and-considerations"></a>制限事項と考慮事項
現在、**数値範囲スライサー**には次の制限事項と考慮事項が適用されています。

* 現在、**数値範囲スライサー**では、集計値ではなく、データの基になるすべての行がフィルターされます。 たとえば、*Sales Amount* フィールドが使用されている場合、ビジュアルのデータ ポイントごとの *Sales Amount* の合計ではなく、*Sales Amount* に基づく各トランザクションがフィルターされます。
* 現在、メジャーでは動作しません。
* 数値スライサーのテキスト ボックスには、基礎となる列の値範囲から外れるものも含め、あらゆる数値を入力できます。 そのため、今後、データが変わる可能性があることがわかっている場合、フィルターを設定できます。
