---
title: "Power BI で Lithium に接続する"
description: "Power BI 用 Lithium"
services: powerbi
documentationcenter: 
author: joeshoukry
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
ms.author: yshoukry
ms.openlocfilehash: ed7255df535cf2e6703fe9235b192c85d98d92d3
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-lithium-with-power-bi"></a>Power BI で Lithium に接続する
Lithium は、人々が回答を得たり、エクスペリエンスを共有したりするのを手助けして、世界最高のブランドと顧客との間に信頼関係を築きます。 Lithium コンテンツ パックを Power BI に接続してオンライン コミュニティに関する主要指標を測定すると、販売の促進、サービス コストの削減、ロイヤルティの向上に役立ちます。 

Power BI 用 [Lithium コンテンツ パック](https://app.powerbi.com/getdata/services/lithium)に接続します。

>[!NOTE]
>Power BI コンテンツ パックは、Lithium API を使用します。 API への過剰な呼び出しは、Lithium からの追加料金につながる可能性があります。Lithium 管理者にご確認ください。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. **[サービス]** ボックスで、 **[取得]**を選択します。
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. **[Lithium]** \> **[取得]** の順に選択します。
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Lithium コミュニティの URL を指定します。 *https://community.yoursite.com* の形式になります。
   
   ![](media/service-connect-to-lithium/params.png)
5. ダイアログが表示されたら、Lithium の資格情報を入力します。 認証方式として **[oAuth 2]** を選び、 **[サインイン]** をクリックして、Lithium 認証フローに従います。
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. ログイン フローが完了すると、インポート プロセスが開始します。 完了すると、ナビゲーション ウィンドウに、新しいダッシュ ボード、レポート、モデルが表示されます。 インポートされたデータを表示するダッシュボードを選択します。
   
    ![](media/service-connect-to-lithium/lithium.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](service-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="system-requirements"></a>システム要件
Lithium コンテンツ パックには、Lithium Community v15.9 以降が必要です。 Lithium の管理者に問い合わせてご確認ください。

## <a name="next-steps"></a>次の手順
[Power BI の概要](service-get-started.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

