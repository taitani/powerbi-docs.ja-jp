---
title: "Power BI サービスの [分析] ウィンドウ"
description: "Power BI サービスでビジュアルの動的な参照線を作成します"
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
ms.date: 05/02/2017
ms.author: mihart
ms.openlocfilehash: 30fc0731f819f063aa04e856e8acc75a69f64a59
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="analytics-pane-in-power-bi-service"></a>Power BI サービスの [分析] ウィンドウ
**Power BI サービス**の **[分析]** ウィンドウによって、動的な*参照線*を視覚化に追加して、重要な傾向や情報に注目させることができます。

![](media/service-analytics-pane/power-bi-analytics-pane.png)

> [!NOTE]
> **[分析]** ウィンドウは、レポート キャンバスでビジュアルを選択した場合にのみ表示されます。
> 
> 

## <a name="using-the-analytics-pane"></a>[分析] ウィンドウを使用する
**[分析]** ウィンドウでは、次の種類の動的参照線を作成できます (ビジュアルの種類によっては使用できないものがあります)。

* X 軸の定数線
* Y 軸の定数線
* 最小値線
* 最大値線
* 平均線
* 中央値線
* 百分位線

次のセクションでは、**[分析]** ウィンドウと動的参照線を視覚化で使用する方法を説明します。

ビジュアルで使用可能な動的参照線を表示するには、次のようにします。

1. ビジュアルを選択または作成した後、**[視覚化]** ウィンドウの **[分析]** アイコン ![](media/service-analytics-pane/power-bi-analytics-icon.png) を選びます。
2. 作成する線の種類の下矢印を選択して、オプションを展開します。 この例では、**[平均線]** を選択します。
   
   ![](media/service-analytics-pane/power-bi-add.png)
3. 新しい線を作成するには、**[+ 追加]** を選択します。 テキスト ボックスをダブルクリックして名前を入力し、線の名前を指定できます。
   
   *色* 、 *透明度* 、 *スタイル* 、 *位置*  (ビジュアルのデータ要素を基準にして)、ラベルを表示するかどうかなど、線についてのあらゆる種類のオプションがあります。 重要なのは、**[メジャー]** ドロップダウンを選択することで線の基になるビジュアルの**メジャー**を選択できることです。[メジャー] ドロップダウンにはビジュアルのデータ要素が自動的に設定されます。 この例では、メジャーとして "*Open store count*" を選び、"*Avg # Open Stores*" というラベルを付けて、他のいくつかのオプションを次のようにカスタマイズします。
   
   ![](media/service-analytics-pane/power-bi-average-line.png)
4. データ ラベルを表示する場合は、**[データ ラベル]** スライダーをオンにします。 このスライダーをオンにすると、データ ラベルの他のオプションが表示されます。
5. **[分析]** ウィンドウの **[平均線]** 項目の横に数字が表示されます。 この数字は、ビジュアルで現在有効になっている動的な線の数とその種類を示します。 店舗数目標の 9 として **[定数線]** を追加した場合、**[定数線]** 参照線もこのビジュアルに適用されたことが **[分析]** ウィンドウに示されます。
   
   ![](media/service-analytics-pane/power-bi-reference-lines.png)
   
   選択したビジュアルに動的参照線を適用できない場合は (この例では **[マップ]** ビジュアル)、**[分析]** ウィンドウを選択すると次のように表示されます。
   
   ![](media/service-analytics-pane/power-bi-no-lines.png)

**[分析]** ウィンドウで動的参照線を作成することにより、あらゆる種類の興味深い情報に焦点を当てることができます。

動的参照線を適用できるビジュアルの拡張など、機能の拡充が予定されているので、ときどき確認してみてください。

## <a name="limitations"></a>制限事項
動的参照線を使用できるかどうかは、使用されているビジュアルの種類によって決まります。 次の一覧では、現在各動的線を使用できるビジュアルを示します。

次のビジュアルではすべての動的線を使用できます。

* 面グラフ
* 折れ線グラフ
* 散布図
* 集合縦棒グラフ
* 集合横棒グラフ

次のビジュアルでは、 **[分析]** ウィンドウの *定数線* のみを使用できます。

* 積み上げ面グラフ
* 積み上げ横棒グラフ
* 積み上げ縦棒グラフ
* 100% 積み上げ横棒グラフ
* 100% 積み上げ縦棒グラフ

次のビジュアルでは、現在は *傾向線* のみを使用できます。

* 非積み上げ折れ線グラフ
* 集合縦棒グラフ

最後に、次のような非デカルト ビジュアルには、現在は **[分析]** ウィンドウの動的線を適用できません。

* マトリックス
* 円グラフ
* ドーナツ
* テーブル

## <a name="next-steps"></a>次の手順
[Power BI Desktop の [分析] ウィンドウ](desktop-analytics-pane.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

