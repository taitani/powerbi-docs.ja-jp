---
title: "Power BI Desktop ビジュアルでのデータの確認とレコードの確認"
description: "Power BI Desktop のデータの確認機能とレコードの確認機能を使用して、詳細情報にドリルダウンします"
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
ms.date: 10/09/2017
ms.author: davidi
ms.openlocfilehash: c43ec48d1bd34a5df2578c6cc117dd3e3bbdb64f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Power BI Desktop のデータの確認とレコードの確認を使用する
**Power BI Desktop** では、ビジュアルの詳細にドリルダウンして、データのテキスト表現または選択したビジュアルの個々のデータ要素を見ることができます。 これらの機能は、*クリックスルー*、*ドリルスルー*、*詳細情報へのドリルスルー*などとも呼ばれます。

**[レコードの確認]** を使うとビジュアルから選んだ 1 つのデータ要素の基になっている行を表示でき、**[データの確認]** を使うとビジュアルで使われている値のテキスト版を表示できます。 **[データの確認]** と **[レコードの確認]** の使用についてはいくつかの制限があり、この記事の最後で説明します。

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>Power BI Desktop でのデータの確認の使用
**[データの確認]** ボタンは、リボンの **[ビジュアル ツール]** セクションの **[データ/ドリル]** タブにあります。

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

ビジュアルを右クリックし、表示されるメニューから **[データの確認]** を選択して、**データを確認する**こともできます。

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> 右クリック メニューを使うには、ビジュアル内のデータ ポイントの上にマウス ポインターを移動する必要があります。
> 
> 

**[データの確認]** を選ぶと、**Power BI Desktop** は選んだビジュアルとデータにフォーカスし、そのビジュアルとデータのテキスト表現だけをキャンバス領域に表示します。 次の図のよう、ビジュアルがキャンバスの上部に表示され、データが下部に表示されます。 これは*横*表示です。

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

右上隅のアイコンを選ぶことで、*縦表示*に切り替えることが (または、*横表示*に戻すことが) できます。

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

レポートに戻るには、キャンバスの左上隅にある **[< レポートに戻る]** を選びます。

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>Power BI Desktop でのレコードの確認の使用
ビジュアル内の 1 つのデータ要素に注目して、その背後にあるデータにドリルダウンできます。 ビジュアルを選んだ後、**[レコードの確認]** を使うには 2 つの方法があります。**[データ/ドリル]** リボンで **[レコードの確認]** トグルボタンを有効にしてから、データ要素をクリックします。または、データ要素を右クリックし、表示されるメニューから **[レコードの確認]** を選びます。

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> 選んだビジュアルが **[レコードの確認]** をサポートしていない場合、リボンのボタンは淡色になります。
> 
> 

**[レコードの確認]** を選ぶと、**Power BI Desktop** は個別のデータ要素にフォーカスし、その要素のデータだけをキャンバス領域に表示します (次の図を参照)。

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

レポートに戻るには、キャンバスの左上隅にある **[レポートに戻る]** ボタンを選びます。

## <a name="limitations"></a>制限事項
**[データの確認]** または **[レコードの確認]** を使用するときに考慮すべき制限事項がいくつかあります。

* 次のビジュアルの種類のみがサポートされています。
  * **横棒**
  * **列**
  * **マップ**
  * **ツリー マップ**
  * **塗り分け地図**
  * **円**
  * **ドーナツ**
  * **じょうご**
* 計算されるメジャーがビジュアルで使われている場合は、**[レコードの確認]** を使用できません
* ライブ多次元 (MD) モデルに接続されている場合は、**[レコードの確認]** を使用できません

## <a name="next-steps"></a>次の手順
**Power BI Desktop** には、あらゆる種類のレポートの書式指定とデータ管理機能があります。 例については、次のリソースをご覧ください。

* [Power BI Desktop でグループ化とビン分割を使用する](desktop-grouping-and-binning.md)
* [Power BI Desktop レポートで、グリッド線、グリッドへのスナップ、重ね順、配置、および分布を使用する](desktop-gridlines-snap-to-grid.md)

