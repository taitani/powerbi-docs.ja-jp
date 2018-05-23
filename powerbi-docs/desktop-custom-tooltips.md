---
title: Power BI Desktop でのヒントのカスタマイズ
description: ドラッグ アンド ドロップでビジュアル用カスタム ヒントを作成
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 75cafe7c3de05d901e95662829e30c809ae54ace
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Power BI Desktop でのヒントのカスタマイズ
ヒントにより、ビジュアル上のデータ ポイントのコンテキスト情報と詳細を、洗練された方法で提供できます。 次の図は、Power BI Desktop のグラフに適用されたヒントを示しています。

![](media/desktop-custom-tooltips/custom-tooltips_1.png)

視覚エフェクトが作成されると、既定のヒントに、データ ポイントの値とカテゴリが表示されます。 ヒント情報をカスタマイズできると便利な例は多数あります。また、カスタマイズすることで、ビジュアルを表示しているユーザーに、追加のコンテキストと情報が提供されます。 カスタム ヒントを使用すると、ヒントの一部として表示する追加のデータ ポイントを指定できます。

## <a name="how-to-customize-tooltips"></a>ヒントをカスタマイズする方法
カスタマイズされたヒントを作成するには、次の図に示すように、**[視覚化]** ウィンドウの **[フィールド]** ウェルで、フィールドを **[ヒント]** バケットにドラッグするだけです。 次の図では、4 つのフィールドが **[ヒント]** バケットに配置されています。

![](media/desktop-custom-tooltips/custom-tooltips_2.png)

ヒントがフィールド ウェルに追加されると、視覚エフェクトのデータ ポイントにポインターを合わせたときに、そのフィールドの値がヒントに表示されます。

![](media/desktop-custom-tooltips/custom-tooltips_3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>集計または簡単な計算でのヒントのカスタマイズ
ヒントをさらにカスタマイズするには、**[ヒント]** バケットのフィールドの横にある矢印を使用して集計関数または *[簡単な計算]* を選択し、使用可能なオプションを選択します。

![](media/desktop-custom-tooltips/custom-tooltips_4.png)

データセットで使用できるフィールドを使って**ヒント**をカスタマイズし、ダッシュボードやレポートを閲覧しているユーザーに情報と洞察をすばやく伝える方法は多数あります。

