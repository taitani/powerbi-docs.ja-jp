---
title: Power BI で Lithium に接続する
description: Power BI 用 Lithium
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6cbd67a9c35726830fc862326d9a015b96952b83
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "37136297"
---
# <a name="connect-to-lithium-with-power-bi"></a>Power BI で Lithium に接続する
Lithium は、人々が回答を得たり、エクスペリエンスを共有したりするのを手助けして、世界最高のブランドと顧客との間に信頼関係を築きます。 Lithium コンテンツ パックを Power BI に接続してオンライン コミュニティに関する主要指標を測定すると、販売の促進、サービス コストの削減、ロイヤルティの向上に役立ちます。 

Power BI 用 [Lithium コンテンツ パック](https://app.powerbi.com/getdata/services/lithium)に接続します。

>[!NOTE]
>Power BI コンテンツ パックは、Lithium API を使用します。 API への過剰な呼び出しは、Lithium からの追加料金につながる可能性があります。Lithium 管理者にご確認ください。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. **[サービス]** ボックスで、 **[取得]** を選択します。
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. **[Lithium]** \> **[取得]** の順に選択します。
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Lithium コミュニティの URL を指定します。 *https://community.yoursite.com* という形式になります。
   
   ![](media/service-connect-to-lithium/params.png)
5. ダイアログが表示されたら、Lithium の資格情報を入力します。 認証方式として **[oAuth 2]** を選び、 **[サインイン]** をクリックして、Lithium 認証フローに従います。
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. ログイン フローが完了すると、インポート プロセスが開始します。 完了すると、ナビゲーション ウィンドウに、新しいダッシュ ボード、レポート、モデルが表示されます。 インポートされたデータを表示するダッシュボードを選択します。
   
    ![](media/service-connect-to-lithium/lithium.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](power-bi-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="system-requirements"></a>システム要件
Lithium コンテンツ パックには、Lithium Community v15.9 以降が必要です。 Lithium の管理者に問い合わせてご確認ください。

## <a name="next-steps"></a>次の手順
[Power BI とは?](power-bi-overview.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

