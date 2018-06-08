---
title: 顧客向けのアプリケーションに Power BI コンテンツを埋め込む
description: Power BI API を使って、Web アプリに顧客向けのレポート、ダッシュボード、タイルを統合する (埋め込む) 方法を説明します。
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: ae683dfbeb7b3848575ab766c33b695eb823d497
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721043"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-customers"></a>チュートリアル: 顧客向けのアプリケーションに Power BI のレポート、ダッシュボード、タイルを埋め込む
**Azure の Power BI Embedded** を使うと、**アプリ所有データ**を使用してレポート、ダッシュボード、またはタイルをアプリケーションに埋め込むことができます。 **アプリ所有データ**がある場合、Power BI を埋め込み分析プラットフォームとして使用するアプリケーションが含まれます。 これは通常、**ISV 開発者**のシナリオです。 **ISV 開発者**は、アプリケーションのユーザーが Power BI ライセンスを必要としたり、さらには内部に Power BI があることすら意識したりせずに、完全に統合された対話型のアプリケーションにレポート、ダッシュボード、またはタイルを表示する Power BI コンテンツを作成することができます。 このチュートリアルでは、**アプリ所有データ**を使用する顧客向けに **Azure の Power BI Embedded** を使用しているときに、**Power BI** .NET SDK と **Power BI** JavaScript API を使って、アプリケーションにレポートを統合する方法を示します。

このチュートリアルで学習する内容は次のとおりです。
>[!div class="checklist"]
>* Azure にアプリケーションを登録します。
>* Power BI レポートをアプリケーションに埋め込みます。

## <a name="prerequisites"></a>前提条件
作業を始めるには、**マスター アカウント**になる **Power BI Pro** アカウントと **Microsoft Azure** サブスクリプションが必要です。

* **Power BI Pro** にサインアップしていない場合は、[無料の試用版にサインアップ](https://powerbi.microsoft.com/en-us/pricing/)してください。
* Azure サブスクリプションをお持ちでない場合は、始める前に[無料アカウントを作成](https://azure.microsoft.com/free/?WT.mc_id=A261C142F)してください。
* 独自の [Azure Active Directory テナント](create-an-azure-active-directory-tenant.md)のセットアップが必要です。
* [Visual Studio](https://www.visualstudio.com/) がインストールされている必要があります (バージョン 2013 以降)。

## <a name="setup-your-embedded-analytics-development-environment"></a>埋め込み分析開発環境をセットアップする

アプリケーションへのレポート、ダッシュボード、タイルの埋め込みを開始する前に、埋め込めるように環境がセットアップされていることを確認する必要があります。 セットアップの一環として、以下を行う必要があります。

[オンボード エクスペリエンス ツール](https://aka.ms/embedsetup/AppOwnsData)を使うと、環境の作成とレポートの埋め込みに役立つサンプル アプリケーションを間単にダウンロードして実行できます。

ただし、手動で環境をセットアップする場合は、以下を続行できます。
### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Azure Active Directory (Azure AD) にアプリケーションを登録する

アプリケーションを Azure Active Directory に登録すると、アプリケーションは Power BI REST API にアクセスできるようになります。 これにより、アプリケーションの ID を設定し、Power BI REST リソースへのアクセス許可を指定することができます。

1. [Microsoft Power BI API 条項](https://powerbi.microsoft.com/api-terms)に同意します。

2. [Azure Portal ](https://portal.azure.com)にサインインします。
 
    ![Azure Portal メイン](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

3. 左側のナビゲーション ウィンドウで、**[すべてのサービス]**、**[アプリの登録]**、**[新しいアプリケーションの登録]** の順に選びます。
   
    ![アプリの登録の検索](media/embed-sample-for-customers/embed-sample-for-customers-003.png)</br>
    ![新しいアプリの登録](media/embed-sample-for-customers/embed-sample-for-customers-004.png)

4. 画面の指示に従って、新しいアプリケーションを作成します。 アプリ所有データの場合、アプリケーションの種類には **[ネイティブ]** を使う必要があります。 また、**Azure AD** がトークンの応答を返すために使用する**リダイレクト URI** を指定する必要もあります。 アプリケーション固有の値を入力します (例: http://localhost:13526/redirect))。

    ![アプリを作成する](media/embed-sample-for-customers/embed-sample-for-customers-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Azure Active Directory でアプリケーションにアクセス許可を適用する

アプリ登録ページで指定されたものに加え、アプリケーションに対する追加のアクセス許可を有効にする必要があります。 埋め込みに使った "*マスター*" アカウントでログインする必要があります。これは、グローバル管理者アカウントである必要があります。

### <a name="use-the-azure-active-directory-portal"></a>Azure Active Directory ポータルを使用する

1. Azure Portal で [[アプリの登録]](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) を参照して、埋め込みに使うアプリを選びます。
   
    ![アプリの選択](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

2. **[設定]** を選び、**[API アクセス]** で **[必要なアクセス許可]** を選びます。
   
    ![必要なアクセス許可](media/embed-sample-for-customers/embed-sample-for-customers-008.png)

3. **[Windows Azure Active Directory]** を選択してから、**[サインインしたユーザーとしてディレクトリにアクセスします]** が選択されていることを確認します。 **[保存]** を選択します。
   
    ![Windows Azure AD のアクセス許可](media/embed-sample-for-customers/embed-sample-for-customers-011.png)

4. **[追加]** を選択します。

    ![アクセス許可の追加](media/embed-sample-for-customers/embed-sample-for-customers-012.png)

5. **[API を選択します]** を選びます。

    ![API アクセスの追加](media/embed-sample-for-customers/embed-sample-for-customers-013.png)

6. **[Power BI サービス]** を選んでから、**[選択]** を選びます。

    ![PBI サービスの選択](media/embed-sample-for-customers/embed-sample-for-customers-014.png)

7. **[デリゲートされたアクセス許可]** のすべてのアクセス許可を選択します。 選択内容を保存するために 1 つずつ選択する必要があります。 完了したら、**[保存]** を選択します。
   
    ![デリゲートされたアクセス許可の選択](media/embed-sample-for-customers/embed-sample-for-customers-015.png)

8. **[必要なアクセス許可]** 内で、**[アクセス許可の付与]** を選択します。
   
    "*マスター アカウント*" で Azure AD により同意を求めるプロンプトが表示されないようにするには、**[アクセス許可の付与]** アクションが必要です。 この操作を実行するアカウントがグローバル管理者である場合は、組織のすべてのユーザーにこのアプリケーションに対するアクセス許可を与えることになります。 このアクションを実行するアカウントが "*マスター アカウント*" であり、グローバル管理者ではない場合は、"*マスター アカウント*" にのみこのアプリケーションに対するアクセス許可を与えます。
   
    ![[必要なアクセス許可] ダイアログの [アクセス許可の付与]](media/embed-sample-for-customers/embed-sample-for-customers-016.png)

## <a name="setup-your-power-bi-environment"></a>Power BI の環境を設定する

### <a name="create-an-app-workspace"></a>アプリ ワークスペースを作成する

顧客向けのレポート、ダッシュボード、またはタイルを埋め込む場合は、コンテンツをアプリ ワークスペース内に配置する必要があります。 "*マスター*" アカウントは、アプリ ワークスペースの管理者である必要があります。

1. 最初に、ワークスペースを作成します。 **[ワークスペース]**  > **[アプリのワークスペースの作成]** の順に選びます。 この場所に、アプリケーションでアクセスする必要のあるコンテンツを配置します。

    ![ワークスペースの作成](media/embed-sample-for-customers/embed-sample-for-customers-020.png)

2. ワークスペースの名前を付けます。 対応する**ワークスペース ID** が使用できない場合は、一意の ID になるように編集します。 これはアプリの名前にもなります。

    ![ワークスペース名の指定](media/embed-sample-for-customers/embed-sample-for-customers-021.png)

3. 設定にはいくつかのオプションがあります。 **[パブリック]** を選択すると、組織内のすべてのユーザーがワークスペースの内容を表示できます。 一方、**[プライベート]** の場合、ワークスペースのメンバーしかその内容を表示できません。

    ![プライベート/パブリック](media/embed-sample-for-customers/embed-sample-for-customers-022.png)

    グループを作成した後は、公開/非公開を変更することはできません。

4. メンバーが**編集**可能かどうか、**表示専用**のアクセス許可を持つかどうかも選択できます。

    ![メンバーの追加](media/embed-sample-for-customers/embed-sample-for-customers-023.png)

5. ワークスペースへのアクセス許可を与えるユーザーの電子メール アドレスを追加して、**[追加]** を選択します。 追加できるのは個別ユーザーのみで、グループのエイリアスは追加できません。

6. ユーザーごとにメンバーか管理者かを判断します。管理者は、他のメンバーの追加を含め、ワークスペース自体を編集できます。 メンバーは、表示専用のアクセス許可を持っていないかぎり、ワークスぺースのコンテンツを編集できます。 管理者とメンバーの両方がアプリを発行できます。

新しいワークスペースを表示できるようになります。 Power BI でワークスペースが作成され、開きます。 メンバーであるワークスペースの一覧が表示されます。 管理者は、省略記号 (...) を選択すると、前の画面に戻って新しいメンバーの追加やアクセス許可の変更などの変更を加えることができます。

   ![新しいワークスペース](media/embed-sample-for-customers/embed-sample-for-customers-025.png)

### <a name="create-and-publish-your-reports"></a>レポートを作成して発行する

Power BI Desktop を使用してレポートとデータセットを作成し、アプリ ワークスペースにこれらのレポートを発行できます。 レポートを発行するエンド ユーザーには、アプリ ワークスペースに発行するための Power BI Pro ライセンスが必要です。

1. GitHub からサンプルの [Blog Demo](https://github.com/Microsoft/powerbi-desktop-samples) をダウンロードします。

    ![レポートのサンプル](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. **Power BI Desktop** でサンプルの PBIX レポートを開きます

   ![PBI デスクトップ レポート](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. **アプリ ワークスペース**に発行します

   ![PBI デスクトップ レポート](media/embed-sample-for-customers/embed-sample-for-customers-028.png)

    Power BI サービスを使ってオンラインでレポートを表示できるようになります

   ![PBI デスクトップ レポート](media/embed-sample-for-customers/embed-sample-for-customers-029.png)

## <a name="embed-your-content"></a>コンテンツを埋め込む

アプリケーション内で顧客向けの埋め込みを行うには、**Azure AD** からマスター アカウントの**アクセス トークン**を取得する必要があります。 Power BI API への呼び出しを行う前に、アプリ所有データを使用する Power BI アプリケーションのための [Azure AD アクセス トークンを取得する](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data)必要があります。

次の手順に従い、サンプル アプリケーションを使用してコンテンツの埋め込みを開始します。

1. 最初に、GitHub から [App Owns Data サンプル](https://github.com/Microsoft/PowerBI-Developer-Samples)をダウンロードします。

    ![App Owns Data アプリケーションのサンプル](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

2. サンプル アプリケーションで Web.config ファイルを開きます。 アプリケーションを正常に実行するために入力する必要のあるフィールドが 5 つあります。 **clientID**、**groupId**、**reportId**、**pbiUsername**、**pbiPassword** です。

      ![Web Config ファイル](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

    * **clientId** には、**Azure** から**アプリケーション ID** を設定します。 **clientId** は、アクセス許可を要求しているアプリケーションをユーザーが一意に識別するために使われます。 **clientId** を取得するには、次の野手順のようにします。

    1. [Azure Portal ](https://portal.azure.com)にサインインします。

        ![Azure Portal メイン](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

    2. 左側のナビゲーション ウィンドウで、**[すべてのサービス]**、**[アプリの登録]** の順に選びます。

        ![アプリの登録の検索](media/embed-sample-for-customers/embed-sample-for-customers-003.png)
    3. **clientId** を取得するアプリケーションを選びます。

        ![アプリの選択](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

    4. **アプリケーション ID** が GUID として一覧表示されます。 この**アプリケーション ID** を、アプリケーションの **clientId** として使います。

        ![clientId](media/embed-sample-for-customers/embed-sample-for-customers-007.png)     

    * **groupId** には、Power BI から**アプリ ワークスペースの GUID** を設定します。

        ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    * **reportId** には、Power BI から**レポートの GUID** を設定します。

        ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)    

    * **pbiUsername** には、マスター ユーザーの Power BI アカウントを設定します。
    * **pbiPassword** には、マスター ユーザーの Power BI アカウントのパスワードを設定します。

3. アプリケーションを実行します。

    最初に、**Visual Studio** で **[実行]** を選びます。

    ![アプリケーションの実行](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

    次に、**[Embed Report]** を選びます。 テスト対象に選んだコンテンツ (レポート、ダッシュボード、タイル) に応じて、アプリケーションでそのオプションを選びます。

    ![コンテンツの選択](media/embed-sample-for-customers/embed-sample-for-customers-034.png)
 
    サンプル アプリケーションでレポートを表示できるようになります。

    ![アプリケーションの表示](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

## <a name="move-to-production"></a>運用開始

アプリケーションの開発が終わったら、専用の容量を持つアプリのワークスペースに戻ります。 運用を開始するには、専用の容量が必要です。

### <a name="create-a-dedicated-capacity"></a>専用の容量を作成する
専用の容量を作成することで、顧客専用のリソースを所有する利点が得られます。 専用の容量に割り当てられていないワークスペースの場合、これらは共有された容量にあります。 専用の容量を作成するには、Azure の [Power BI Embedded 専用の容量](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity)ソリューションを使用します。

>[!Note]
>PRO ライセンスの埋め込みトークンは、開発テストのためのものです。そのため、Power BI マスター アカウントで生成できる埋め込みトークンの数には限りがあります。 運用環境で埋め込むには、専用の容量を購入する必要があります。 専用の容量があると、生成できる埋め込みトークンの数には上限がありません。 現在の埋め込み使用パーセンテージを示す使用状況の値を確認するには、「[Get Available Features](https://msdn.microsoft.com/library/mt846473.aspx)」(使用可能な機能の入手) をご覧ください。
>

### <a name="assign-app-workspace-to-dedicated-capacity"></a>専用の容量にアプリ ワークスペースを割り当てる

専用の容量が作成されたら、アプリ ワークスペースを専用の容量に割り当てます。 これを行うには、次の手順に従います。

1. **Power BI サービス**内でワークスペースを展開し、コンテンツを埋め込んでいるワークスペースの省略記号ボタンを選択します。 次に、**[Edit workspaces]\(ワークスペースの編集\)** を選択します。

    ![ワークスペースの編集](media/embed-sample-for-customers/embed-sample-for-customers-036.png)

2. **[詳細]** を展開し、**[専用の容量]** を有効にして、作成した専用の容量を選びます。 その後、**[保存]** を選びます。

    ![専用の容量の割り当て](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

JavaScript API の使用に関する完全なサンプルについては、[Playground ツール](https://microsoft.github.io/PowerBI-JavaScript/demo)を使用できます。 このツールを使うと、さまざまな種類の Power BI Embedded のサンプルを簡単に再生できます。 JavaScript API について詳しくは、[PowerBI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) のページもご覧ください。

Power BI Embedded についてさらに質問がある場合は、[FAQ](embedded-faq.md) のページをご覧ください。  アプリケーションでの Power Bi Embedded に関して問題が発生した場合は、[トラブルシューティング](embedded-troubleshoot.md)のページをご覧ください。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。