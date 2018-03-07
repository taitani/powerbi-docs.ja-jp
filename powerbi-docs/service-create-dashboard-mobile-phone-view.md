---
title: "携帯電話用の Power BI ダッシュボードのビューを作成する"
description: "携帯電話での表示専用に Power BI サービスでダッシュボードのカスタマイズしたビューを作成する方法について説明します。"
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/12/2017
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: babc9f97ed8c45c2cb9ac994d881941d03629676
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="create-a-view-of-a-power-bi-dashboard-optimized-for-mobile-phones"></a>携帯電話用に最適化された Power BI ダッシュボードのビューを作成する
スマートフォンで Power BI モバイル アプリのダッシュボードを開くと、ダッシュボードのタイルがすべて同じサイズで並んで表示されることに気付くでしょう。 Power BI サービスでは、スマートフォンでの表示専用に、所有しているダッシュボードのカスタマイズしたビューを作成できます。

スマートフォンを横向きにすると、ダッシュボードはサービスでのレイアウトと同じように表示され、スマートフォン用にデザインしたレイアウトでは表示されません。

> [!NOTE]
> Phone ビューを編集すると、スマートフォンでダッシュボードを見ているユーザーに対して、ビューの変更がリアルタイムで表示される場合があります。 たとえば、ダッシュボードの Phone ビューですべてのタイルの固定を解除すると、突然スマートフォン上のダッシュボードにタイルが 1 つもなくなります。 
> 
> 

## <a name="create-a-phone-view-of-a-dashboard"></a>ダッシュボードの Phone ビューを作成する
1. Power BI サービスでダッシュボードを開きます。
2. 右上隅の **[Web ビュー]** の横にある矢印を選んでから、**[Phone ビュー]** を選びます。

    ![](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-dashboard.png)

    ダッシュボードの所有者でない場合、このオプションは表示されません。

    ![](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-canvas.png)

    スマートフォン用ダッシュボードの編集ビューが開きます。 ここで、スマートフォンでの表示に合わせてタイルの固定解除、サイズ変更、並べ替えができます。 ダッシュボードの Web バージョンは変更されません。


1. タイルを選択してドラッグ、サイズ変更、または固定解除します。 タイルをドラッグすると、他のタイルが移動します。
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-unpin-tile-phone-dashboard.png)
   
    固定解除されたタイルは [ピンを外したタイル] ウィンドウに移動し、再度追加しない限り、そのままです。
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-post-edit.png)
2. 操作を取り消す場合は、**[タイルのリセット]** を選ぶと、前のサイズと順序に戻ります。
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-reset-tiles.png)
   
    Power BI サービスでスマートフォン用編集ビューを開くだけで、スマートフォン上のタイルのサイズと形状がわずかに変更されます。 ダッシュボードをスマートフォン用編集ビューで開く前の正確な状態に戻すには、**[タイルのリセット]** を選択します。
3. スマートフォン用ダッシュボードのレイアウト編集が完了したら、右上隅の **[Phone ビュー]** の横にある矢印を選んだ後、**[Web ビュー]** を選びます。
   
    スマートフォン用レイアウトが自動的に保存されます。

## <a name="next-steps"></a>次の手順
* [Power BI 電話アプリ用に最適化したレポートを作成する](desktop-create-phone-report.md)
* [任意のサイズに最適化されるレスポンシブ ビジュアルを作成する](desktop-create-responsive-visuals.md)
* 他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

