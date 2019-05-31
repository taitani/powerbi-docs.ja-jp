---
title: Power BI Desktop で相対日付のスライサーまたはフィルターを使用する
description: Power BI Desktop で相対的な日付範囲を制限するスライサーまたはフィルターを使う方法について説明します
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/28/2019
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 3d8057c4d35294dd5e83638b721169e4d54d2adf
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374455"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi"></a>Power BI で、相対日付スライサーおよびフィルターを使用します。
**相対日付スライサー**または**相対日付フィルター**では、データ モデルの任意の日付列に時間ベースのフィルターを適用することができます。 たとえば、**相対日付スライサー**を使って、過去 30 日間 (または、1 か月、カレンダー月など) に発生した販売データのみを表示できます。 データを更新すると、相対期間が適切な相対日付制約を自動的に適用します。

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-01.png)

## <a name="using-the-relative-date-range-slicer"></a>相対日付範囲スライサーの使用
他のスライサーと同じように相対日付スライサーを使用できます。 レポートの**スライサー** ビジュアルを作成し、 **[フィールド]** 値の日付値を選択するだけです。 次の図では、*OrderDate* フィールドが選択されています。

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-02.png)

ビジュアルのスライサーの右上隅で、キャンバスとし、キャレットでスライサーを選択します。 オプションをメニューが表示されます、ビジュアルに日付データが含まれている場合**相対**します。 

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-03.png)

相対日付スライサーの場合は、"*相対*" を選びます。

その後、設定を選択できます。 "*相対日付スライサー*" の最初のドロップダウンには、次の選択肢があります。

* 前回
* 次へ
* この

これらの選択を次の図に示します。

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04.png)

"*相対日付スライサー*" の次の (中央) 設定では、数字を入力して、相対的な日付範囲を定義できます。

3 番目の設定では、日付の測定値を選択できます。 次の選択肢があります。

* 日
* 週
* 週 (暦)
* 月
* 月 (暦)
* 年
* 年 (暦)

これらの選択を次の図に示します。

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-05.png)

そのリストから "*月*" を選択し、中央の設定に 2 を入力すると、次のようになります: 今日が 7 月 20 日の場合、スライサーによって制約されるビジュアルのデータは、5 月 20 日から 7 月 20 日 (今日の日付) までの過去 2 か月間が表示されます。

一方、"*間 (暦)* " を選択すると、5 月 1 日から 6 月 30 日 (カレンダーで完全な過去 2 か月) のデータが表示されます。

## <a name="using-the-relative-date-range-filter"></a>相対日付範囲フィルターの使用
レポート ページまたはレポート全体の相対日付範囲フィルターを作成することもできます。 そのためには、次の図に示すように、 **[フィールド]** ウィンドウの **[ページ レベル フィルター]** 領域または **[レポート レベル フィルター]** 領域に、日付フィールドをドラッグします。

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-06.png)

その後は、**相対日付スライサー**のカスタマイズと同様の方法で、相対日付範囲を変更できます。 **[フィルターの種類]** ドロップダウンから **[相対日付フィルター]** を選びます。

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-07.png)

**[相対日付フィルター]** を選ぶと、スライサーと同じように中間の数値ボックスなど 3 つのセクションを変更できます。

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-08.png)

レポートで相対日付制約を使うのに必要なものはこれだけです。

## <a name="limitations-and-considerations"></a>制限事項と考慮事項
現在、**相対日付範囲スライサー**とフィルターには次の制限事項と考慮事項が適用されています。

* **Power BI** のデータ モデルには、タイム ゾーン情報は含まれません。 モデルは時間を保存できますが、タイム ゾーンの指定はありません。
* スライサーとフィルターは常に UTC の時刻に基づくので、レポートでフィルターを構成して別のタイム ゾーンの同僚に送ると、どちらも同じデータが表示されます。 ただし、UTC タイム ゾーンではない場合は、予想とは異なるタイム オフセットのデータが表示される可能性があります。
* ローカル タイム ゾーンでキャプチャされたデータは、**クエリ エディター**で UTC に変換できます。

