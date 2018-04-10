---
title: Power BI サービスの読み取りビューまたは編集ビューでレポートを開く
description: Power BI レポートを読み取りビューまたは編集ビューで開く
services: powerbi
documentationcenter: ''
author: mihart
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
ms.date: 03/01/2018
ms.author: mihart
ms.openlocfilehash: 17921d1fe28a1b4c0640748123efe4b70982b18d
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2018
---
# <a name="open-a-report-in-power-bi-service-apppowerbicom"></a>Power BI サービス (app.powerbi.com) でレポートを開く
レポートは Power BI サービス、Power BI Desktop、Power BI モバイルで使用でき、Power BI Embedded でも使用できます。 この記事は、***Power BI サービス***でレポートを開く場合に適用されます。

Power BI サービスには、レポートを表示および操作するための 2 つのモード ([読み取りビューと編集ビュー](service-reading-view-and-editing-view.md)) があります。 読み取りビューはすべてのユーザーが利用でき、特にレポートの*コンシューマー*向けに設計されていますが、編集ビューはレポートの*作成者*と所有者のみが利用できます。 

## <a name="open-a-report-from-a-workspace-via-the-reports-content-view-list"></a>ワークスペースからレポートを開く (**[レポート]** コンテンツ ビュー リストを使用)

1. ワークスペースで開始し、**[レポート]** タブを選んで、そのワークスペース内のすべてのレポートを表示します。  
   
   ![ワークスペースの [レポート] タブ](media/service-report-open/power-bi-open-report.png)
2. レポート名を選択し、読み取りビューで開きます。  
   
    ![読み取りビューのレポート](media/service-report-open/power-bi-reading-view.png)
3. [読み取りビューでは、多くのことができます](service-reading-view-and-editing-view.md)。  このサンプル レポートには複数のページがあります。最初に、レポート キャンバスの下部にある各タブを選択してみましょう。 

## <a name="open-a-report-from-a-dashboard"></a>ダッシュボードからレポートを開く
他にもさまざまな方法でレポートを開くことができます。たとえば、ダッシュボードで開始し、レポートから作成したタイルを選択する方法もあります。  タイルを選択すると、読み取りビューでレポートが開きます。 作業を進めるために、[売上およびマーケティングのサンプル ダッシュボードを開きます](sample-datasets.md)。

1. ダッシュボードを開き、タイルを選択します。

   [Q&A を使用して作成](service-dashboard-pin-tile-from-q-and-a.md)されたタイルを選択すると、Q&A 画面が開きます。 [ダッシュボードの **[タイルの追加]** ウィジェットを使用して作成](service-dashboard-add-widget.md)されたタイルを選択すると、そのウィジェットを編集するためのウィザードが開きます。  

2.  この例では、"Total Units YTD..." という縦棒グラフ タイルを選択しています。

    ![タイルが選択されているダッシュボード](media/service-report-open/power-bi-dashboard.png)

3.  関連付けられたレポートが読み取りビューで開きます。 "YTD Category" ページが表示されていることがわかります。 これは、ダッシュボードから選択した縦棒グラフを含むレポート ページです。

    ![読み取りビューで開かれたレポート](media/service-report-open/power-bi-report.png)

4. 読み取りビューに留まるか、**[レポートの編集]** を選択して、編集ビューでレポートを開きます。 編集ビューでレポートを開くことができるのは、そのレポートの編集アクセス許可を持つユーザーのみであることに注意してください。

    ![[レポートの編集] アイコンが表示されたレポート エディター](media/service-report-open/power-bi-edit-report.png)

## <a name="create-a-brand-new-report-from-a-dataset"></a>データセットから新しいレポートを作成する
データセットからレポートを開くもう 1 つの方法があります。 データセットから開始すると、レポート キャンバスが空白になるため、この方法は、所有しているデータセットに基づいて新しいレポートを作成しようとしているレポートの*作成者*にお勧めします。 上記の例のように、先に進む前に、[売上およびマーケティングのサンプル アプリ](sample-datasets.md)をダウンロードします。

1. レポートの基礎として使用するデータセットを含むワークスペースから開始します。

   ![アプリ ワークスペースが表示された左ナビゲーション ウィンドウ](media/service-report-open/power-bi-workspace.png)

2. **[データセット]** タブを選択して、そのワークスペースのすべてのデータセットのリストを表示します。 これを、**データセット** コンテンツ ビュー リストといいます。
   
   ![データセットのリスト](media/service-report-open/power-bi-dataset.png)

1. データセットを見つけて**レポートの作成**アイコンを選択し、編集ビューでデータセットを開きます。 データセットの編集アクセス許可がない場合は開くことができません。 
   
    ![レポートの作成アイコンが表示されたデータセット](media/service-report-open/power-bi-create-report.png)

3. データセットがレポート エディターで開きます。 データ フィールドが右側に表示されるのがわかります。これは、視覚エフェクトの探索と作成が開始されるのをただ待機している状態です。 

   ![レポート キャンバス](media/service-report-open/power-bi-blank-canvas.png)

##  <a name="still-more-ways-to-open-a-report"></a>レポートを開く他の方法
Power BI サービスのナビゲーションに慣れてくると、最適なワークフローを見つけ出すことができます。 レポートにアクセスする他の方法をいくつか以下に示します。
- 左側のナビゲーション ウィンドウから、**[お気に入り]**、**[最近使った項目]**、**[アプリ]**、**[自分と共有]** を使用する。 
- [[関連の表示]](service-related-content.md) を使用する
- メールで (他のユーザーに[共有してもらう](service-share-reports.md)場合、または自分で[アラートを設定する](service-set-data-alerts.md)場合)。    
- [通知センター](service-notification-center.md)から    
- その他

## <a name="next-steps"></a>次の手順
[Power BI のレポート](service-reports.md)で詳細を確認する

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。  

