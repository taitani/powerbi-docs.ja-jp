---
title: Power BI Desktop から Power BI サービスのデータセットに接続する
description: 複数の Power BI Desktop レポートに共通のデータセットを使い、レポートのライフサイクルを管理します
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9a0e87eca537fc8c22dffaad6a725dc949b2b121
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54275573"
---
# <a name="connect-to-datasets-in-the-power-bi-service-from-power-bi-desktop"></a>Power BI Desktop から Power BI サービスのデータセットに接続する
Power BI サービスの共有データセットへのライブ接続を確立し、同じデータセットから多数の異なるレポートを作成できます。 つまり、Power BI Desktop で完全なデータ モデルを作成し、それを Power BI サービスに発行した後、その同じ共通のデータ モデルから複数の異なるレポート (異なる .pbix ファイル) を作成できます。 この機能は、**Power BI サービス ライブ接続**と呼ばれます。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_01.png)

この機能にはベスト プラクティスなどあらゆる種類の利点があり、この記事ではそれについて説明します。 考慮事項と制限もいくつかあり、この記事の最後に記載してあるので、よく読んでおいてください。

## <a name="using-a-power-bi-service-live-connection-for-report-lifecycle-management"></a>レポートのライフサイクル管理に Power BI サービス ライブ接続を使う
Power BI の 1 つの課題は、レポート、ダッシュボード、およびその基になるデータ モデルの急増です。 このようなことが問題になるのは、**Power BI Desktop** で説得力のあるレポートを簡単に作成し、そのレポートを **Power BI サービス**で共有 ([発行](desktop-upload-desktop-files.md)) して、それらのデータセットから優れたダッシュボードを作成できるためです。 非常に多くのユーザーが、多くの場合は同じ (またはほぼ同じ) データセットを使って、これを行うため、レポートの基になっているデータセットや、各データセットの新しさを把握することが、困難になります。 **Power BI サービス ライブ接続**はそのような課題に対処し、共通のデータセットに基づくレポートとダッシュボードの作成、共有、拡張を、簡単かつ一貫性のあるものにします。

### <a name="create-a-dataset-everyone-can-use-then-share-it"></a>誰でも使用できるデータセットを作成して共有する
Anna (ビジネス アナリスト) は、優れたデータ モデル (データセット) を作成するものとします。 Anna は専門知識を駆使してデータセットとレポートを作成し、そのレポートを **Power BI サービス**で共有します。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_02a.png)

誰もが Anna のレポートとデータセットを好みますが、それが問題の始まりです。チームの全員がそのデータセットの "*自分用バージョン*" を作成し、自分のレポートをチームで共有しようとします。 そして突然、**Power BI サービス**のチームのワークスペースに、(異なるデータセットに基づく) 大量のレポートが出現します。 どれが最新のものでしょう。 データセットは同じですか、それともほぼ同じなだけですか。 何が違うのですか。 **Power BI サービス ライブ接続**機能を使うと、このようなことをすべて改善できます。 次のセクションでは、Anna が発行したデータセットを、他のユーザーが自分のレポートに使用し、誰もが同じ発行されたデータセットを使って独自のレポートを作成できるようにする方法を説明します。

### <a name="connect-to-a-power-bi-service-dataset-using-a-live-connection"></a>ライブ接続を使用して Power BI サービス データセットに接続する
Anna が自分のレポート (および、その基になるデータセット) を作って **Power BI サービス**に発行すると、Power BI サービスのチームのワークスペースに表示されます。 そのワークスペースに含まれるすべてのユーザーが、それを表示して使用できます。

ワークスペースの詳細については、「[アプリ ワークスペース](service-create-workspaces.md)」を参照してください。

ワークスペースの他のメンバーは、**Power BI サービス ライブ接続**機能を使って Anna の共有データ モデルへのライブ接続を確立し、" *の元のデータセット*" から独自のレポートを作成できます。

次の図は、Anna が **Power BI Desktop** レポートを作成し、**Power BI サービス**に (データ モデルを含む) それを発行する様子を示しています。 ワークスペースの他のユーザーは、**Power BI サービス ライブ接続**を使ってそのデータ モデルに接続し、それを基にして独自のレポートを作成できます。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_03.png)

> [!NOTE]
> データセットは 1 つのワークスペースでのみ共有されます。 Power BI サービス ライブ接続を確立するには、接続先のデータセットが共有されているワークスペースのメンバーである必要があります。
> 
> 

## <a name="step-by-step-for-using-the-power-bi-service-live-connection"></a>Power BI サービス ライブ接続を使う手順
**Power BI サービス ライブ接続**の有用性と、レポート ライフサイクル管理のベスト プラクティス手法としてそれを使う方法はわかったので、Anna の優れたレポート (およびデータセット) を Power BI ワークスペースのチームメートが使用できる共有データセットに発行する手順を見ていきます。

### <a name="publish-a-power-bi-report-and-dataset"></a>Power BI レポートとデータセットを発行する
**Power BI サービス ライブ接続**を使ってレポートのライフサイクルを管理する最初の手順は、チームメートが使いたくなるレポート (とデータセット) を用意することです。 したがって、まず、Anna は **Power BI Desktop** からレポートを**発行**する必要があります。 それには、Power BI Desktop の **[ホーム]** リボンで **[発行]** を選びます。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_02a.png)

発行を行うには、Power BI サービス アカウントにサインする必要があります。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_04.png)

レポートとデータセットの発行先のワークスペースを選びます。 レポートが発行されるワークスペースにアクセスできるメンバーだけが、**Power BI サービス ライブ接続**を使ってデータセットにアクセスできることに注意してください。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_05.png)

発行プロセスが開始し、**Power BI Desktop** に進行状況が表示されます。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_06.png)

完了すると、**Power BI Desktop** に、成功したことと、**Power BI サービス**内のレポート自体およびレポートの**クイック分析情報**を取得するための 2 つのリンクが表示されます。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_07.png)

次に、レポート (とデータセット) が発行されたワークスペースにアクセスできる他のチームメートが、データセットに接続して独自のレポートを作成する方法を説明します。

### <a name="establish-a-power-bi-service-live-connection-to-the-published-dataset"></a>発行されたデータセットへの Power BI サービス ライブ接続を確立する
発行されたレポートへの接続を確立し、発行されたデータセットを基にして独自のレポートを作るには、**Power BI Desktop** の **[ホーム]** リボンで **[データの取得]** を選び、**[Power BI サービス]** を選びます。 **[データの取得] > [オンライン サービス] > [Power BI サービス]** から選ぶこともできます。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_08.png)

Power BI にサインインしていない場合は、サインインするように促されます。 ログインすると、自分がメンバーであるワークスペースを示すウィンドウが表示され、**Power BI サービス ライブ接続**の確立先データセットを含むワークスペースを選ぶことができます。

ワークスペースの横にあるかっこ内の数字は、そのワークグループで使用可能な共有データセットの数を示し、左側にある三角形を選択すると、ワークスペースが展開して、共有データセットを選ぶことができます。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_09a.png)

前の **Power BI サービス** ライブ接続ウィンドウでは、注意することがいくつかあります。

* 共有データセットを検索できますが、検索結果は展開されている項目に限定され、展開されていないワークスペースは含まれません。
* 複数のワークスペースを開いて検索対象を拡大できます。

ウィンドウから **[読み込み]** を選ぶと、選んだデータセットへのライブ接続が確立されます。つまり、表示されるデータ (フィールドおよび値) は、リアルタイムで **Power BI Desktop** に読み込まれます。

![](media/desktop-report-lifecycle-datasets/report-lifecycle_10.png)

複数のユーザーが同じデータセットからカスタム レポートを作成して共有できるようになります。 これは、Anna のような有能なユーザーがよくできたデータセットを作成し、他の多くのチームメートは共有データセットを使って独自のレポートを作成できる、優れた方法です。

> [!NOTE]
> **Power BI サービス**へのライブ接続を使ってデータセットから作成したレポートは、使われたデータセットを含む同じ Power BI サービス ワークスペースに対してのみ発行できます。
> 
> 

## <a name="limitations-and-considerations"></a>制限事項と考慮事項
**Power BI サービス ライブ接続**を利用するとき、注意すべきいくつかの制限事項と考慮事項があります。

* ワークスペースの読み取り専用のメンバーは、**Power BI Desktop** からデータセットに接続できません。
* 公開されたデータセットに **Power BI サービス ライブ接続**を使って接続できるのは、同じ **Power BI サービス** ワークスペースのユーザーだけです。 ユーザーは複数のワークスペースに属すことができます (多くの場合、実際に属しています)。
* これはライブ接続のため、**SQL Server Analysis Services** に接続するときの動作と同様に、左側のナビゲーションおよびモデリングは無効になります。
* これはライブ接続のため、**SQL Server Analysis Services** に接続するときと同様に、RLS (行レベルとロール レベルのセキュリティ)、OneDrive for Business、および他のそのような接続動作が適用されます。
* **Power BI サービス**で接続するデータセットを選ぶとき、検索ボックスは展開されているワークスペースにのみ適用されます。
* 所有者が元の共有 .pbix ファイルを変更すると、**Power BI サービス**で共有されているデータセットおよびレポートが上書きされます。
* ワークスペースのメンバーは、もともと共有されていたレポートを置き換えることはできません。 置き換えようとすると、ファイルの名前を変更して発行するよう求める警告が表示されます。
* **Power BI サービス**で共有データセットを削除した場合、他の **Power BI Desktop** (.pbix ファイル) は正常に動作しないか、ビジュアルが表示されなくなります。
* コンテンツ パックの場合は、**Power BI サービス**に .pbix レポートおよびデータセットを共有するための基礎として使う前に、コンテンツ パックのコピーを作成しておく必要があります。
* "*自分の所属組織*" からのコンテンツ パックの場合、コピーした後は、サービスで作成されたレポートや、ライブ接続でのコンテンツ パックのコピーの一部として作成されたレポートを、置き換えることはできません。 置き換えようとすると、ファイルの名前を変更して発行するよう求める警告が表示されます。 このような状況では、発行されたライブ接続されているレポートのみを置換できます。
* **Power BI サービス**へのライブ接続を使ってデータセットから作成したレポートは、使われたデータセットを含む同じ Power BI サービス ワークスペースに対してのみ発行できます。
* **Power BI サービス**で共有データセットを削除すると、**Power BI Desktop** からそのデータセットにアクセスできなくなります。

