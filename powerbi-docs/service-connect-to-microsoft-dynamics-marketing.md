---
title: Power BI で Microsoft Dynamics Marketing に接続する
description: Power BI 用 Microsoft Dynamics Marketing
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 94b019f04fb6fabcad3092524fd2724015a6d8e1
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242192"
---
# <a name="connect-to-microsoft-dynamics-marketing-with-power-bi"></a>Power BI で Microsoft Dynamics Marketing に接続する
Power BI 用 Microsoft Dynamics Marketing コンテンツ パックを使用すると、Dynamics Marketing のデータに簡単にアクセスして分析することができます。 コンテンツ パックは、OData フィードに加えて記述モデルを使用します。その際、必要なすべてのエンティティやメジャーを使用します。たとえば、プログラム、キャンペーン、マーケティング取引先担当者およびマーケティング会社、潜在顧客、潜在顧客の相互作用と潜在顧客のスコアリング、電子メール マーケティング メッセージと Web サイト、動作の監視、予算、金融取引、パフォーマンス KPI などです。 

Power BI 用 [Dynamics Marketing コンテンツ パック](https://app.powerbi.com/getdata/services/microsoft-dynamics-marketing)に接続します。

>[!NOTE]
>Dynamics Marketing のインスタンスの有効な OData URL を指定する必要があります (コンテンツ パックは、オンプレミスの CRM バージョンでは機能しません)。 下の追加要件を参照してください。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある [データの取得] を選択します。
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_getdata.png) 
2. **[サービス]** ボックスで、 **[取得]** を選択します。
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_getservices.png) 
3. **[Microsoft Dynamics Marketing]** \> **[取得]** を選択します。
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/mdmarketing.png)
4. アカウントと関連付けられている OData URL を指定します。  これは次の形式になります: "https://[instance\_name].marketing.dynamics.com/analytics"
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynmktgserviceurl.png)
5. メッセージが表示されたら、資格情報を指定します (ブラウザーで既にサインインしている場合、この手順は省略される可能性があります)。 認証方式として、「 **oAuth2** 」と入力し、 **[サインイン]** をクリックします。
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynammktgoauth2.png)
6. 接続すると、独自のデータを示した Dynamics Marketing ダッシュボードが表示されます。 新しい項目は、左側のナビゲーション ウィンドウで黄色のアスタリスク でマークされます。
   
   ![](media/service-connect-to-microsoft-dynamics-marketing/pbi_dynammktgnewdash.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](power-bi-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="system-requirements"></a>システム要件
* Dynamics Marketing のインスタンスの有効な OData URL を指定する必要があります (コンテンツ パックは、オンプレミスの CRM バージョンでは機能しません)。  
* 管理者は、サイトの設定で OData エンドポイントを有効にする必要があります。 OData エンドポイントのアドレスは、**[組織のデータ サービス]** セクションの **[ホーム] \> [設定] \> [サイトの設定]** にあります。  OData URL の形式は次のとおりです: https://[instance\_name].marketing.dynamics.com/analytics  
* Microsoft Dynamics Marketing へのアクセスに使用するユーザー アカウント/ID は、Power BI を使ってサインアップしたものと同じにする必要があります。 Microsoft Dynamics Marketing にログインする際、Power BI で使用しているものと同じ ID で 自動的にサインインします。 別のアカウントで Microsoft Dynamics Marketing にサインインする場合、その別のアカウントを使用する Power BI ユーザーとして登録してください。 今後のリリースでこの問題は解決される予定です。   

## <a name="troubleshooting"></a>トラブルシューティング
Dynamics CRM アカウントに接続する際に "Login failed" というメッセージが表示される場合、CRM Online OData フィードへのアクセスに使用するものと同じアカウントで Power BI にサインインしていることを確認してください。 ブラウザーでフィードへのログインも試行し、そこでテストを行ってください。

OData URL が正しいこと、および OData エンドポイントが有効であることを確認するよう管理者に依頼してください。

お使いの Dynamics Marketing のバージョンを確認してください。18.0 と 18.1 には追加の修正が行われています。問題が解決せず、前のバージョンをお使いの場合、アップグレードすることを検討してください。

問題が解決されない場合は、サポート チケットを開き、Power BI チームと連絡を取ってください。

* Power BI アプリを使用中の場合は、[?] \> **[サポートへの問い合わせ]** の順に選択します。
* Power BI サポート サイト (現在ご覧になっているこの記事) ページの右側にある、 **[サポートへの問い合わせ]** を選択します。

## <a name="next-steps"></a>次の手順
[Power BI のデータの取得](service-get-data.md)

[Power BI の概要](service-get-started.md)

