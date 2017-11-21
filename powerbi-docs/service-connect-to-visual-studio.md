---
title: "Power BI で Visual Studio Team Services に接続する"
description: "Power BI 用 Visual Studio Team Services"
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
ms.openlocfilehash: 20ea9117cf1eee3d7b05be21e5964226349a58c1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-visual-studio-team-services-with-power-bi"></a>Power BI で Visual Studio Team Services に接続する
Power BI 用 Visual Studio Team Services コンテンツ パックを使用して、Git と TFVC チーム プロジェクトに関する情報を入手します。 接続が完了すると、ダッシュボードとレポートに、データが自動的に示されます。 

[Visual Studio Team Services コンテンツ パック](https://app.powerbi.com/getdata/services/visual-studio-online)に接続するか、Power BI と [Visual Studio Team Services との統合](https://powerbi.microsoft.com/integrations/visual_studio_online)について詳細をお読みください。

>[!NOTE]
>このコンテンツ パックでは、OAuth が有効なアカウントにアクセスすることが必要となります。 要件の詳細については、このあと説明します。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。  
   ![](media/service-connect-to-visual-studio/pbi_getdata.png) 
2. **[サービス]** ボックスで、 **[取得]**を選択します。  
   ![](media/service-connect-to-visual-studio/pbi_getservices.png) 
3. **Visual Studio Team Services** コンテンツ パックを選び、**[取得]** をクリックします。     
   ![](media/service-connect-to-visual-studio/vsts.png)
4. Visual Studio Team Services アカウントの情報を入力します。 [これらのパラメーターの見つけ方](#FindingParams)について詳しくは、後述します。
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin.png)
   
   アカウント名は URL の visualstudio.com に先行する部分です。    
   ![](media/service-connect-to-visual-studio/urlimage.png)
   
   プロジェクトの名前は Visual Studio Team Services 内の各ページの上部に表示される名前です:  
   ![](media/service-connect-to-visual-studio/projectimage.png)
5. oAuth2 を使用して Visual Studio Team Services を認証します。 結果として、VSTS サインイン ダイアログ ボックスが表示されることがあります。 
   
   > [!IMPORTANT]
   > 一部の Visual Studio Team Services デプロイメントは oAuth2 をサポートしていません。  サインインに失敗した場合は、「トラブルシューティング」のセクションに記載されているガイダンスに従います。
   > 
   > 
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin2.png)
6. Visual Studio Team Services 認証画面に従い、Power BI 用 Visual Studio コンテンツ パックにチーム プロジェクトのデータへのアクセスを許可します。   
   ![](media/service-connect-to-visual-studio/vsoauthorizeapp450.png)
7. Visual Studio Team Services プロジェクトに接続すると、新しいダッシュボード、レポート、データセットが左側のナビゲーション ウィンドウに表示されます。 新しい項目には黄色のアスタリスク \* でマークが付けられます。  
   ![](media/service-connect-to-visual-studio/visualstudioonline800px.png) 

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](service-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="whats-included"></a>含まれるもの
Power BI の Visual Studio Team Services では、レポートに使用するさまざまなテーブルとフィールドを提供します。 このコンテンツ パックに含まれるものの完全な一覧はこちらです:  <https://www.visualstudio.com/get-started/report/vso-pbi-whats-available-vs>

## <a name="system-requirements"></a>システム要件
* REST API を使用してデータを収集するアクセス許可を持つ Visual Studio Team Services アカウントへのアクセス  
* 初期接続中に、"Power BI" アプリケーションに付与されるアクセス許可 Power BI を切断して、Visual Studio Team Services アカウントへのアクセスの承認を削除するには、Visual Studio Team Services でアクセスを取り消すことができます。 <https://www.visualstudio.com/get-started/setup/change-application-access-policies-vs> をご覧ください。  

詳細については、<https://www.visualstudio.com/ja-jp/get-started/report/connect-vso-pbi-vs> をご覧ください。

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>パラメーターの見つけ方
アカウント名は URL の visualstudio.com に先行する部分です。    
    ![](media/service-connect-to-visual-studio/urlimage.png)

プロジェクトの名前は VSTS 内の各ページの上部に表示される名前です:  
    ![](media/service-connect-to-visual-studio/projectimage.png)

またワイルドカードを使用すると、複数のプロジェクトを選択できます。 たとえば、「\*」と入力するとすべてのプロジェクトを選ぶことができ、「Azure\*」と入力すると "Azure" で始まるすべてのプロジェクトを選ぶことができます。

## <a name="troubleshooting"></a>トラブルシューティング
Visual Studio Team Services にログインしようとすると、ログインに失敗しましたというメッセージが表示されることがあります。

正常に認証できない原因としては、次の 2 つの理由が一般的です。

1) 職場または学校のアカウントではなく、個人のアカウントを使用してサインインしている  

2) Visual Studio Team Services のデプロイで oAuth がサポートされていない 

**職場または学校アカウントによるサインイン**  
この問題が起こる場合、データの読み込みを試みているアカウントとは別のアカウントで Visual Studio Team Services の認証を既に受けている可能性があります。たとえば、個人用の Microsoft アカウントで Visual Studio Team Services に接続し、職場または学校のアカウントで PowerBI に接続した場合などです。

この問題を解決するには:  

* [構成] ダイアログ ボックスを [キャンセル] で閉じます。  
* 個人用アカウントで Visual Studio Team Services からサインアウトします。  
* 職場または学校のアカウントで Visual Studio Online にサインインします。  
* 前述の「データ取り出し」プロセスを再開します。 

職場または学校のアカウントによる接続 (Azure Active Directory / AAD):  
    ![](media/service-connect-to-visual-studio/vsologinscreen.png)

このダイアログ ボックスが表示される場合、職場または学校のアカウント (Azure Active Directory) で接続するには、必ず左側のリンクをクリックしてそのアカウントでサインインします。右側に AAD 資格情報を指定しないでください。右側に入力するのは Microsoft アカウント (個人用アカウント) だからです。

**oAuth2 をサポートしていない Visual Studio Team Services デプロイ**  
VSTS 管理者が Visual Studio Team Services デプロイメントで oAuth を無効にした可能性があります。  その場合、現時点で Power BI 用 Visual Studio コンテンツ パックは使用できません。 

![](media/service-connect-to-visual-studio/oauth.png)

## <a name="next-steps"></a>次の手順
* [Power BI の概要](service-get-started.md)
* [データの取得](service-get-data.md)

