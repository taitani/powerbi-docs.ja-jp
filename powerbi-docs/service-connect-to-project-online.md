---
title: "Power BI で Project Online に接続する"
description: "Power BI 用 Project Online"
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
LocalizationGroup: Connect to services
ms.openlocfilehash: 6272b3f175d7da851e5d8086c574a91f0f00c933
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-project-online-with-power-bi"></a>Power BI で Project Online に接続する
Microsoft Project Online は、プロジェクト ポートフォリオ管理 (PPM) および日常の作業用の柔軟なオンライン ソリューションです。 Project Online を使用すると、プロジェクト ポートフォリオの投資を開始して優先順位を設定し、意図したとおりのビジネス価値を提供できます。 Power BI 用 Project Online コンテンツ パックでは、ポートフォリオの状態やプロジェクトへの準拠などの既定のメトリックで、プロジェクトのデータを調べることができます。

Power BI 用 [Project Online コンテンツ パック](https://app.powerbi.com/getdata/services/project-online)に接続します。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
    ![](media/service-connect-to-project-online/getdata.png)
2. **[サービス]** ボックスで、 **[取得]**を選択します。
   
   ![](media/service-connect-to-project-online/services.png)
3. **[Microsoft Project Online]** \> **[取得]** の順に選択します。
   
   ![](media/service-connect-to-project-online/mproject.png)
4. **[Project Web App の URL]** テキスト ボックスに接続する Project Web App (PWA) の URL を入力し、 **[次へ]**をクリックします。 カスタム ドメインを使用している場合は例と異なる場合があることに注意してください。
   
    ![](media/service-connect-to-project-online/params.png)
5. [認証方法] として **[oAuth2]** を選択し、**[サイン イン]** をクリックします。 プロンプトが表示されたら、Project Online の資格情報を入力し、認証プロセスに従います。
   
    ![](media/service-connect-to-project-online/creds.png)
6. データを読み込んでいることを示す通知が表示されます。 アカウントの大きさによっては時間がかかる可能性があります。 Power BI によるデータのインポート後、新しいダッシュ ボード、レポート、データセットが左側のナビゲーション ウィンドウに表示されます。 これは、データを表示するために Power BI によって作成された既定のダッシュボードです。 このダッシュボードを変更し、希望する方法でデータを表示できます。
   
   ![](media/service-connect-to-project-online/dashboard2.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](power-bi-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="next-steps"></a>次の手順
[Power BI の概要](service-get-started.md)

[Power BI でデータを取得する](service-get-data.md)

