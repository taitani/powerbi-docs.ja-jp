---
title: 組織でテンプレート アプリを配布する - Power BI (プレビュー)
description: Power BI を利用し、組織内でテンプレート アプリをインストールし、カスタマイズし、配布する方法について説明します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/07/2019
ms.author: maggies
ms.openlocfilehash: cd3a1f94aa4c965327ea3e5bcb7271326aa3514d
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56249841"
---
# <a name="install-and-distribute-template-apps-in-your-organization---power-bi-preview"></a>組織でテンプレート アプリをインストールし、配布する - Power BI (プレビュー)

新しい Power BI *テンプレート アプリ*を利用すれば、Power BI パートナーはコードをほとんど、あるいはまったく記述せずに Power BI アプリを作成し、Power BI の顧客に配布できます。 この記事は Power BI アナリスト向けに作成されました。 Power BI パートナーが作成したテンプレート アプリをインストールし、カスタマイズし、配布する方法について説明しています。 自分で配布するテンプレート アプリを作成する場合、「[Create a template app in Power BI](service-template-apps-create.md)」 (Power BI でテンプレート アプリを作成する) を参照してください。

![インストールされた Power BI アプリ](media/service-template-apps-install-distribute/power-bi-get-apps.png)

Power BI パートナーが作成したテンプレート アプリをインストールするとき、組織のニーズに合わせてそれを変更し、アプリとして同僚に配布できます。  

## <a name="prerequisites"></a>前提条件  

テンプレート アプリをインストールし、カスタマイズし、配布するための要件:  

- [Power BI Pro ライセンス](service-self-service-signup-for-power-bi.md)
- [Power BI の基本的概念](service-basic-concepts.md)に関する知識
- テンプレート アプリの作成者または AppSource から受け取った有効なインストールのリンク 
- テンプレート アプリをインストールする許可 

## <a name="install-a-template-app"></a>テンプレート アプリをインストールする

テンプレート アプリのリンクは送られてくることがあります。 そうでない場合、興味のあるテンプレート アプリを AppSource で探すことができます。 いずれの方法でも、インストール後、変更し、自分の組織に配布できます。

### <a name="search-appsource-from-a-browser"></a>ブラウザーから AppSource を検索する

ブラウザーで下のリンクを選択し、AppSource を開きます。Power BI アプリに絞り込まれています。

- https://appsource.microsoft.com/marketplace/apps?product=power-bi

### <a name="search-appsource-from-the-power-bi-service"></a>Power BI サービスから AppSource を検索する

1. Power BI サービスの左側のナビゲーション ウィンドウで、**[アプリ]**、**[アプリの取得]** の順に選択します。

    ![アプリの取得](media/service-template-apps-install-distribute/power-bi-get-apps-arrow.png)

2. AppSource で **[アプリ]** を選択します。

    ![AppSource で検索する](media/service-template-apps-install-distribute/power-bi-appsource.png)

3. アプリを参照するか、検索し、**[今すぐ入手する]** を選択します。

2. ダイアログ ボックスで **[インストール]** を選択します。

    Power BI Pro ライセンスを持っている場合、アプリとそれに関連するアプリ ワークスペースがインストールされます。 関連ワークスペースでアプリをカスタマイズします。

    インストールが正常に完了すると、新しいアプリの準備ができたことが通知されます。 

3. **[アプリに移動]** を選択します。
4. **[新しいアプリを開始する]** で 3 つの選択肢のいずれかを選択します。

    ![アプリを開始する](media/service-template-apps-create/power-bi-template-app-get-started.png)

    - **アプリを探索**:基本的なサンプル データの探索。 アプリのルックアンドフィールはここから取得します。 
    - **データに接続**:データ ソースをサンプル データから独自のデータ ソースに変更します。 データセット パラメーターとデータ ソースの資格情報を再定義できます。 テンプレート アプリのヒント記事で「[既知の制限事項](service-template-apps-tips.md#known-limitations)」をご覧ください。 
    - **ワークスペースに移動** (最も細かく設定する場合): アプリ ビルダーが許可しているあらゆる変更を実行できます。

    あるいは、このダイアログ ボックスをスキップし、左側のナビゲーション ウィンドウにある **[ワークスペース]** から直接、関連ワークスペースにアクセスします。   
 
5. 同僚と共有する前に、独自のデータに接続することをお勧めします。 また、組織に合わせてレポートやダッシュボードを修正することもお勧めします。 この段階で他のレポートやダッシュボードも追加できます。

## <a name="update-and-distribute-the-app"></a>アプリを更新し、配布する

組織に合わせてアプリを調整したら、それを公開できます。 手順は、他のアプリを公開する場合と同じです。 

1. カスタマイズが終わったら、ワークスペース リスト ビューの右上隅にある **[アプリを更新]** を選択します。  

    ![アプリのインストールを開始する](media/service-template-apps-install-distribute/power-bi-start-install-app.png)

2. **[詳細]** では、説明や背景色を変更できます。

   ![アプリの説明と色を設定する](media/service-template-apps-install-distribute/power-bi-install-app-details.png)

3. **[コンテンツ]** では、ランディング ページとしてダッシュボードかレポートを選択できます。

   ![アプリのランディング ページを設定する](media/service-template-apps-install-distribute/power-bi-install-app-content.png)

4. **[アクセス]** では、選んだユーザーか組織全体にアクセスを与えます。  

   ![アプリ アクセスを設定する](media/service-template-apps-install-distribute/power-bi-install-access.png)

5. **[アプリを更新]** を選択します。 

6. 正常に公開されたら、リンクをコピーし、アクセスを与えている人と共有できます。 共有すると、共有相手にも、AppSource の **[組織]** タブでそのアプリが表示されます。

## <a name="next-steps"></a>次の手順 

[Power BI で同僚と一緒にワークスペースを作成する](service-create-workspaces.md)





￼ 

 
