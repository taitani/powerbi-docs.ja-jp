---
title: Power BI Desktop での条件付きテーブルの書式設定
description: テーブルへのカスタマイズされた書式の適用
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1626c2af5906004b6b4f79f4830f003b96e241fc
ms.sourcegitcommit: 509be8852ba7595b9441c9479224f9dca298b26d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2018
---
# <a name="conditional-formatting-in-tables"></a>テーブルでの条件付き書式設定
テーブルで条件付き書式を使用すると、セルの値または他の値やフィールドに基づいてカスタマイズされたセルの背景色を指定でき、グラデーション カラーを使用できます。 条件付き書式にアクセスするには、Power BI Desktop の **[視覚化]** ウィンドウの **[フィールド]** ウェルで、書式設定する **[値]** ウェルの値の横にある下向きの矢印を選択します (または、フィールドを右クリックします)。 条件付き書式を管理できるのは、**[フィールド]** ウェルの **[値]** 領域のフィールドだけです。

![テーブルの条件付き書式設定](media/desktop-conditional-table-formatting/table-formatting_1.png)

表示されるダイアログ ボックスでは、色や、*最小*と*最大*の値を構成できます。 **[左右逆方向]** ボックスをオンにした場合は、オプションの*中央*値も構成できます。

![左右逆方向の色](media/desktop-conditional-table-formatting/table-formatting_2.png)

色のグラデーションを、データ モデルのフィールドに基づいて設定することもできます。 さらに、選択したフィールドに集計型を指定できます (選択するフィールドは **[色の適用対象]** フィールドで指定するので、追跡を維持できます)。

![フィールドの基本の色](media/desktop-conditional-table-formatting/table-formatting_2b.png)

テーブルに適用すると、条件付きで書式設定されたセルに適用されているすべてのカスタム テーブル スタイルが、上記の手順で適用したカスタマイズされた書式で上書きされます。

![テーブルの書式設定](media/desktop-conditional-table-formatting/table-formatting_3.png)

書式設定の基礎として数値を選択する限り、テキスト フィールドや日付フィールドに条件付き書式設定を適用することもできます。 

視覚化から条件付き書式を削除するには、再度フィールドを右クリックし、**[条件付き書式の削除]** を選択します。

![テーブルの書式設定の削除](media/desktop-conditional-table-formatting/table-formatting_4.png)

