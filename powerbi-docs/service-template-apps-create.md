---
title: Power BI でテンプレート アプリを作成する (プレビュー)
description: Power BI でテンプレート アプリを作成する方法。作成したアプリは Power BI の顧客に配布できます。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: maggies
ms.openlocfilehash: c08b7e60777b720aa4fc2489b02c212bdd3e7169
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56249818"
---
# <a name="create-a-template-app-in-power-bi-preview"></a>Power BI でテンプレート アプリを作成する (プレビュー)

新しい Power BI *テンプレート アプリ*を利用すれば、Power BI パートナーはコードをほとんど、あるいはまったく記述せずに Power BI アプリを作成し、Power BI の顧客に配布できます。  この記事には、Power BI テンプレート アプリを段階的に作成する手順が含まれています。 

Power BI のレポートやダッシュボードを作成できる場合、*テンプレート アプリ ビルダー*になることができます。テンプレート アプリ ビルダーは、分析コンテンツを作成し、パッケージ化して*アプリ*にする人です。 作成したアプリは、AppSource など、利用できるあらゆるプラットフォームから他の Power BI テナントに配備できます。自分の Web サービスで使用するという方法もあります。 ビルダーは保護付きの分析パッケージを作成し、配布できます。 

Power BI テナント管理者は、組織においてテンプレート アプリを作成できる人とそれをインストールできる人を管理します。 権限を与えられた人はテンプレート アプリをインストールし、その後、そのアプリを変更したり、組織内の Power BI 利用者に配布したりできます。

## <a name="prerequisites"></a>前提条件 

テンプレート アプリの作成要件:  

- [Power BI Pro ライセンス](service-self-service-signup-for-power-bi.md)
- [Power BI Desktop をインストールしておくこと](desktop-get-the-desktop.md) (任意)
- [Power BI の基本的概念](service-basic-concepts.md)に関する知識
- テンプレート アプリを作成する許可。 詳細については、Power BI [管理ポータルのテンプレート アプリの設定](service-admin-portal.md#template-apps-settings-preview)に関するセクションを参照してください。

## <a name="enable-app-developer-mode"></a>アプリ開発者モードを有効にする

他の Power BI テナントに配布できるテンプレート アプリを作成するには、アプリ開発者モードに入る必要があります。 入らない場合、自分の組織の Power BI 利用者のためにアプリを作成することになります。
 
1. ブラウザーで Power BI サービスを開きます。
2. **[設定]**、**[全般]**、**[開発者]**、**[テンプレート アプリ開発モードを有効にする]** の順に選択します。

    ![テンプレート アプリを有効にする](media/service-template-apps-create/power-bi-dev-template-app.png)

    このオプションが表示されない場合、管理ポータルで[テンプレート アプリ開発の許可](service-admin-portal.md#template-apps-settings-preview)を与えるよう、Power BI 管理者に連絡してください。

3. **[適用]** を選びます。

## <a name="create-the-template-app-workspace"></a>テンプレート アプリ ワークスペースを作成する

他の Power BI テナントに配布できるテンプレート アプリを作成するには、それを新しいアプリ ワークスペースで作成する必要があります。 
 
1. Power BI サービスで、**[ワークスペース]**、**[アプリのワークスペースの作成]** の順に選択します。 
 
    ![アプリのワークスペースの作成](media/service-template-apps-create/power-bi-new-workspace.png)

3. **[アプリ ワークスペースを作成する]** の **[強化されたワークスペースをプレビューする]** で **[今すぐ試す]** を選択します。

    ![新しいワークスペースを試す](media/service-template-apps-create/power-bi-try-now-new-workspace.png)

5. アプリ ワークスペースの名前、説明 (任意)、ロゴ画像 (任意) を入力します。

4. **[テンプレート アプリを開発する]** を選択します。

    ![テンプレート アプリを開発する](media/service-template-apps-create/power-bi-template-app-develop.png)

5. **[保存]** を選択します。

## <a name="create-the-content-in-your-template-app"></a>テンプレート アプリでコンテンツを作成する

通常の Power BI アプリ ワークスペースと同様に、次の手順はワークスペースでコンテンツを作成することです。  このプレビュー版のテンプレート アプリでは、データセット、レポート、ダッシュボードという種類のうち、いずれかを 1 つだけ作成できます。

- アプリ ワークスペースで [Power BI コンテンツを作成します](power-bi-creator-landing.md)。

Power Query でパラメーターを使用している場合、型を明確に定義します (Text など)。 Any 型と Binary 型はサポートされていません。 

「[Power BI でのテンプレート アプリの作成に関するヒント (プレビュー)](service-template-apps-tips.md)」には、テンプレート アプリのためにレポートやダッシュボードを作成するときに考慮してほしい事項が提案されています。

## <a name="create-the-test-template-app"></a>テスト テンプレート アプリを作成する

ワークスペースにコンテンツを用意できたので、次はテンプレート アプリでそれをパッケージ化できます。 最初の手順は、テナントで組織内からのみアクセスできるテスト テンプレート アプリを作成することです。

1. テンプレート アプリ ワークスペースで **[アプリの作成]** を選択します。 

    ![アプリを作成する](media/service-template-apps-create/power-bi-create-app.png)
 
    ここでは、テンプレート アプリの追加パラメーターを入力します。4 つのカテゴリがあります。 

    **ブランド**

    - アプリ名 
    - 説明
    - アプリのロゴ (任意)
    - アプリの色 

    **コンテンツ** 

    - アプリのランディング ページ (任意):アプリのランディング ページにするレポートまたはダッシュボードを定義します。  
    
    **コントロール** 

    アプリケーションのコンテンツを使用する際の制限や制約を制御します。 このコントロールを使用し、アプリに含まれる特定の知的財産を保護できます。

    **アクセス**

    - テストの段階で、アプリをインストールし、テストできる組織内の他のユーザーを決定します。

    心配はありません。この設定は後でいつでも変更できます。  

2. **[アプリの作成]** を選択します。 

    テスト アプリが準備できたというメッセージが、コピーしてアプリ テスターと共有するためのリンクと共に表示されます。

    ![テスト アプリの準備ができました](media/service-template-apps-create/power-bi-template-app-test-ready.png)

    後続のリリース管理プロセスの最初の手順も完了しています。

    

## <a name="manage-the-template-app-release"></a>テンプレート アプリのリリースを管理する

このテンプレート アプリを公開する前に、準備完了を確認することが望まれます。 Power BI には、リリース管理ウィンドウが作成されています。このウィンドウでアプリ公開までの道のりを完全に追跡し、調査できます。 ステージ間の移行をトリガーすることもできます。 共通ステージ: 

- テスト アプリの生成: 組織内でのみテストします。 
- テスト パッケージを実稼働前ステージに昇格させる: 組織外でテストします。
- 実稼働前パッケージを実稼働に昇格させる: 運用版です。 
- パッケージを削除するか、前のステージからやり直します。 

それでは各ステージを通過しましょう。

1. テンプレート アプリ ワークスペースで **[リリース管理]** を選択します。

    ![[リリース管理] アイコン](media/service-template-apps-create/power-bi-release-management-icon.png)

2. **[アプリの作成]** を選択します。 

    上記の **[テスト テンプレート アプリを作成する]** でテスト アプリを作成した場合、**[テスト]** の隣に黄色の点が既に入っています。ここで **[アプリの作成]** を選択する必要はありません。 選択した場合、テンプレート アプリの作成プロセスに戻ります。
 
3. **[リンクの取得]** を選択します。

    ![アプリの作成、リンクの取得](media/service-template-apps-create/power-bi-dev-template-create-app-get-link.png)
 
9. アプリのインストール体験をテストするには、通知ウィンドウのリンクをコピーし、新しいブラウザー ウィンドウに貼り付けます。 

    ここからは、顧客が実行する手順と同じ手順を実行することになります。 バージョンについては、[組織でのアプリのインストールと配布](service-template-apps-install-distribute.md)に関するページを参照してください。
 
10. ダイアログ ボックスで **[インストール]** を選択します。

    インストールが正常に完了すると、新しいアプリの準備ができたことが通知されます。 
 
11. **[アプリに移動]** を選択します。
 
12. **[新しいアプリを開始する]** に自分のアプリが表示されます。これと同じ画面を顧客が見ることになります。 

    ![アプリを開始する](media/service-template-apps-create/power-bi-template-app-get-started.png)

13. **[アプリを探索]** を選択し、テスト アプリとサンプル データを確認します。

1. 変更を行うには、元のワークスペースでアプリに戻ります。 納得できるまでテスト アプリを修正します。

9. アプリを実稼働前ステージに昇格させ、テナントの外でテストする準備ができたら、**[リリース管理]** ウィンドウに戻り、**[テスト]** の隣にある **[アプリの昇格]** を選択します。
 
    ![実稼働前にアプリを昇格させる](media/service-template-apps-create/power-bi-template-app-promote.png)

11. **[昇格]** を選択し、選択を確定します。 

12. この新しい URL をコピーし、テスト目的でテナントの外と共有します。 このリンクは、AppSource でアプリを配信するプロセスを始めるときに提出するリンクでもあります。

12. アプリを運用する、あるいは AppSource 経由で共有する準備ができたら、**[リリース管理]** ウィンドウに戻り、**[実稼働前]** の隣にある **[アプリの昇格]** を選択します。
 
11. **[昇格]** を選択し、選択を確定します。 

    これでアプリは実稼働に入りました。いつでも配布できます。

    ![実稼働のアプリ](media/service-template-apps-create/power-bi-template-app-production.png)

自分のアプリを世界中に何千人といる Power BI ユーザーに広く利用してもらうために、アプリを AppSource に提出することをお勧めします。 詳細については、「[Power BI アプリケーション プラン](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer)」を参照してください。 

## <a name="update-your-app"></a>アプリを更新する

これでアプリが実稼働に入りました。実稼働のアプリを邪魔することなく、テスト段階を繰り返すことができます。 

1. **[リリース管理]** ウィンドウで **[アプリの作成]** を選択します。

1. アプリ作成プロセスを繰り返します。 
2. **[ブランド]**、**[コンテンツ]**、**[コントロール]**、**[アクセス]** を設定し、もう一度 **[アプリの作成]** を選択します。
3. **[閉じる]** を選択し、**[リリース管理]** に戻ります。 

    これで実稼働のバージョンとテスト中の新しいバージョンという 2 つのバージョンが表示されます。 

    ![テンプレート アプリの 2 つのバージョン](media/service-template-apps-create/power-bi-template-app-2-versions.png)

## <a name="next-steps"></a>次の手順

顧客がテンプレート アプリを操作するしくみについては、[組織でのアプリのインストールと配布](service-template-apps-install-distribute.md)に関するページをご覧ください。

アプリ配布の詳細については、「[Power BI アプリケーション プラン](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer)」をご覧ください。





