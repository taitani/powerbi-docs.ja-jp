---
title: "Power BI で VMob に接続する"
description: "Power BI 用 VMob"
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
ms.openlocfilehash: f81c132de6ab2d7c086379dc538e23fd2f4072e8
ms.sourcegitcommit: c24e5d7bd1806e0d637e974b5143ab5125298fc6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="connect-to-vmob-with-power-bi"></a>Power BI で VMob に接続する
VMob データの追跡と探索は、Power BI と VMob コンテンツ パックを使って簡単に行うことができます。 Power BI によって取得されるデータは、すべての期間と過去 30 日間のユーザー統計情報、過去 30 日間の販売 KPI、過去 30 日間のキャンペーンの成果です。

Power BI 用 [VMob コンテンツ パック](https://app.powerbi.com/getdata/services/vmob)に接続します。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
    ![](media/service-connect-to-vmob/getdata.png)
2. **[サービス]** ボックスで、 **[取得]**を選択します。
   
   ![](media/service-connect-to-vmob/services.png)
3. **[VMob]** \> **[接続]** を選びます。
   
   ![](media/service-connect-to-vmob/vmob.png)
4. プロンプトが表示されたら、VMob URL を入力し、[次へ] をクリックします。 この URL は、VMob によって個別に提供されます。
   
    ![](media/service-connect-to-vmob/params.png)
5. [認証方法] ドロップダウンで **[基本]** オプションを選択し、VMob のユーザー名とパスワードを入力して、 **[サイン イン]** をクリックします。
   
    ![](media/service-connect-to-vmob/creds.png)
6. インポート処理が自動的に開始され、Power BI によって VMob データが取得され、すぐに使えるダッシュボードとレポートが作成されます。
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](power-bi-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="next-steps"></a>次の手順
[Power BI の概要](service-get-started.md)

[Power BI でデータを取得する](service-get-data.md)

