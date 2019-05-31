---
title: Power BI で Zendesk に接続する
description: Power BI 用 Zendesk
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 1edc4179b000191dfeff87387417009bc28e0ee5
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578829"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Power BI で Zendesk に接続する

この記事には、Power BI テンプレートのアプリを使用して、Zendesk アカウントから、データのプルをについて説明します。 Zendesk アプリには、Power BI ダッシュ ボード、チケット ボリュームおよびエージェント パフォーマンスに関する洞察を提供する Power BI レポートのセットが提供しています。 データは、1 日 1 回自動的に更新されます。 

テンプレート アプリをインストールした後は、ダッシュ ボードとを最も関心の情報を強調表示するレポートをカスタマイズできます。 組織内の仕事仲間にアプリとしてそれを配布することができます。

[Zendesk コンテンツ パック](https://app.powerbi.com/getdata/services/zendesk)に接続するか、Power BI と [Zendesk との統合](https://powerbi.microsoft.com/integrations/zendesk)について詳細をお読みください。

テンプレート アプリをインストールした後は、ダッシュ ボードとレポートを変更できます。 組織内の仕事仲間にアプリとしてそれを配布することができます。

>[!NOTE]
>接続する Zendesk 管理者アカウントが必要です。 [要件](#system-requirements)の詳細については、このあと説明します。

## <a name="how-to-connect"></a>接続する方法

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. 選択**Zendesk** \> **今すぐ入手**します。
4. **この Power BI アプリをインストールしますか?** 選択**インストール**します。
4. **アプリ**ペインで、 **Zendesk**を並べて表示します。

    ![Power BI の Zendesk アプリのタイル](media/service-connect-to-zendesk/power-bi-zendesk-tile.png)

6. **新しいアプリの概要**、**データ接続**します。

    ![新しいアプリを開始する](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

4. アカウントと関連付けられている URL を指定します。 URL は、フォーム **https://company.zendesk.com** します。 [これらのパラメーターの見つけ方](#finding-parameters)について詳しくは、後述します。
   
   ![Zendesk に接続](media/service-connect-to-zendesk/pbi_zendeskconnect.png)

5. ダイアログが表示されたら、Zendesk の資格情報を入力します。  認証方法として **[oAuth 2]** を選択し、 **[サインイン]** をクリックします。 Zendesk 認証フローに従います。 (場合いる既にサインインして Zendesk にブラウザーで、する可能性があります求められません資格情報です。)
   
   > [!NOTE]
   > このコンテンツ パックでは、Zendesk 管理者アカウントを使用して接続する必要があります。 
   > 
   
   ![OAuth2 でサインインします。](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. [ **許可]** をクリックして、Power BI が Zendesk データにアクセスできるようにします。
   
   ![許可します。](media/service-connect-to-zendesk/zendesk2.jpg)
7. **[接続]** をクリックしてインポート プロセスを開始します。 
8. コンテンツの一覧が表示されます、Zendesk アプリに Power BI にデータがインポート: 新しいダッシュ ボード、レポート、およびデータセット。
9. 探索プロセスを開始するダッシュ ボードを選択します。

    ![Zendesk のダッシュ ボード](media/service-connect-to-zendesk/power-bi-zendesk-dashboard.png)
   
## <a name="modify-and-distribute-your-app"></a>変更し、アプリを配布

Zendesk のテンプレートのアプリをインストールしました。 Zendesk アプリ ワークスペースを作成したことを意味します。 ワークスペースで、レポートとダッシュ ボードで、変更およびとして配布、*アプリ*組織内の仕事仲間にします。 

1. 左側のナビゲーション バーで Zendesk の新規のワークスペースのすべての内容を表示する選択**ワークスペース** > **Zendesk**します。 

    ![左側のナビゲーション ウィンドウで Zendesk のワークスペース](media/service-connect-to-zendesk/power-bi-zendesk-workspace-left-nav.png)

    このビューは、ワークスペースのコンテンツの一覧を示します。 右上隅で確認**アプリを更新**します。 仕事仲間にアプリを配布する準備ができたらは、開始します。 

    ![Zendesk コンテンツ リスト](media/service-connect-to-zendesk/power-bi-zendesk-content-list.png)

2. 選択**レポート**と**データセット**にワークスペース内の他の要素を参照してください。

    について[アプリの配布](service-create-distribute-apps.md)をお勧めします。

## <a name="system-requirements"></a>システム要件
Zendesk コンテンツ パックにアクセスするには、Zendesk 管理者アカウントが必要です。 エージェントまたはエンドユーザーが Zendesk データを表示、および場合は、候補を追加し、Zendesk コネクタを確認、 [Power BI Desktop](desktop-connect-to-data.md)します。

## <a name="finding-parameters"></a>パラメーターの見つけ方
Zendesk URL は、Zendesk アカウントにサインインするときに使用した URL と同じになります。 Zendesk URL がよくわからない場合には、Zendesk [ログイン ヘルプ](https://www.zendesk.com/login/)を使用できます。

## <a name="troubleshooting"></a>トラブルシューティング
接続の問題が生じる場合は、Zendesk URL を確認し、Zendesk 管理者アカウントを使用しているを確認します。

## <a name="next-steps"></a>次の手順

* [Power BI で新しいワークスペースを作成します。](service-create-the-new-workspaces.md)
* [Power BI にアプリをインストールし、使用する](consumer/end-user-apps.md)
* [外部サービス用の Power BI アプリへの接続します。](service-connect-to-services.md)
* わからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

