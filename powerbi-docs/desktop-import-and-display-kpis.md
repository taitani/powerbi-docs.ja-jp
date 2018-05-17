---
title: Power BI で KPI をインポートして表示する
description: KPI のインポートと表示
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
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 5cb7370942cdd4b50c8315a075eb7a178b05a692
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="import-and-display-kpis-in-power-bi"></a>Power BI で KPI をインポートして表示する
**Power BI Desktop** では、KPI をインポートしてテーブル、マトリックス、カードに表示できます。

KPI をインポートして表示するには、次の手順を実行します。

1. Power Pivot モデルと KPI のある Excel ブックから始めます。 この演習では、*KPIs* という名前のブックを使用します。

1. **[ファイル] -> [インポート] -> [Excel ブック コンテンツ]** 使って、Power BI に Excel ブックをインポートします。 [ブックのインポート方法については、こちら](desktop-import-excel-workbooks.md)も参照してください。 

1. Power BI にインポートした後、KPI は **[フィールド]** ウィンドウに ![信号機](media/desktop-import-and-display-kpis/traffic.png) アイコンでマークされて表示されます。 レポートで KPI を使うには、内容を展開して、**[値]**、**[目標]**、**[状態]** フィールドを公開する必要があります。

    ![](media/desktop-import-and-display-kpis/desktoppreviewfeatureon2.png)

1. インポートした KPI は、**テーブル**など、標準の視覚化の種類で使うと最適です。 Power BI には **KPI** の視覚化種類も含まれていますが、これは新しい KPI を作成するときにのみ使う必要があります。
   
    ![](media/desktop-import-and-display-kpis/desktoppreviewfeatureon3.png)

これで完了です。 KPI を使用すると、傾向、進行状況、他の重要なインジケーターを強調して表示できます。
