---
title: Power BI で QuickBooks Online に接続する
description: Power BI 用 QuickBooks Online
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: ec13f396ea1a322a79263320a169330f24a2e5f0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "61151270"
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Power BI で QuickBooks Online に接続する
Power BI から QuickBooks Online データに接続すると、すぐに Power BI ダッシュボードと Power BI レポートにより、ビジネス キャッシュ フロー、収益性、顧客などに関する情報を得られます。 ダッシュボードとレポートはそのまま使用することもできますし、カスタマイズして最も関心のある情報を強調表示することもできます。 データは、1 日 1 回自動的に更新されます。

Power BI 用 [QuickBooks Online コンテンツ パック](https://dxt.powerbi.com/getdata/services/quickbooks-online)に接続します。

>[!NOTE]
>QuickBooks Online のデータを Power BI をインポートするには、QuickBooks Online アカウントの管理者であるとともに、管理者アカウントの資格情報でサインインする必要があります。 QuickBooks Desktop ソフトウェアでは、このコネクタは使用できません。 

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。
   
   ![](media/service-connect-to-quickbooks-online/pbi_getdata.png) 
2. **[サービス]** ボックスで、 **[取得]** を選択します。
   
   ![](media/service-connect-to-quickbooks-online/pbi_getservices.png) 
3. **[QuickBooks Online]** を選択し、 **[取得]** を選択します。
   
   ![](media/service-connect-to-quickbooks-online/qbo.png)
4. 認証の方式として **[oAuth2]** を選択してから、 **[サインイン]** を選びます。 
5. プロンプトが表示されたら、QuickBooks Online 資格情報を入力し、QuickBooks Online 認証プロセスに従います。 ブラウザーで既に QuickBooks Online にサインインした場合には、資格情報を求めるプロンプトが表示されないことがあります。
   >[!NOTE]
   >QuickBooks Online アカウントの管理者資格情報が必要です。
6. 次の画面で Power BI に接続する会社を選択します。
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)
7. 次の画面で **[承認]** を選択し、インポート プロセスを開始します。 会社のデータ サイズによっては数分かかることがあります。 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
   Power BI にデータがインポートされると、新しいダッシュボード、レポート、データセットが左側のナビゲーション ウィンドウに表示されます。 新しい項目には黄色のアスタリスク \* でマークが付けられます。
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_leftnavnew.png)
8. QuickBooks Online ダッシュ ボードを選択します。 これは、Power BI によって自動的に作成されたダッシュボードで、インポートされたデータが表示されます。 このダッシュボードを変更し、希望する方法でデータを表示できます。 
   
   ![](media/service-connect-to-quickbooks-online/pbi_qbo_dash.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](consumer/end-user-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](consumer/end-user-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新するようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="troubleshooting"></a>トラブルシューティング
**「問題が発生しました。」**

**[承認]** を選択した後に、次のメッセージが表示されることがあります。

「 問題が発生しました。」 このウィンドウを閉じて、もう一度やり直してください。

アプリケーションが、この会社の別のユーザーによって既にサブスクライブされています。 [管理者電子メール] に連絡し、このサブスクリプションを変更してください。」

![](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

このメッセージは、社内の別の管理者が Power BI を使用して社内データに既に接続していることを意味します。 該当する管理者に、ダッシュ ボードを共有するように依頼してください。 現時点では、特定の QuickBooks Online の会社データセットを Power BI に接続できるのは、1 人の管理者ユーザーだけです。 Power BI によってダッシュ ボードが作成された後、管理者は同じ Power BI テナントの同僚とそのダッシュボードを共有できます。

**"This app is not set up to allow connections from your country" (このアプリは、お客様の国からの接続が許可されていません)**

現在、Power BI がサポートしているのはQuickBooks Online の米国版のみです。 

![](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>次の手順
[Power BI とは?](power-bi-overview.md)

[Power BI - 基本的な概念](consumer/end-user-basic-concepts.md)

