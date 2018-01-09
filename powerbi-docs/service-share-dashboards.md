---
title: "同僚や他のユーザーとダッシュボードを共有する - Power BI"
description: "Power BI ダッシュボードを組織の内外で同僚と共有する方法と共有について知るべきこと。"
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: monitoring
qualitydate: 08/14/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/18/2017
ms.author: maggies
ms.openlocfilehash: 4cc7f12eb4964c67ae9f91cfcb51eac77d690555
ms.sourcegitcommit: ea247cb3cfc1cac076d4b076c1ad8e2fc37e15a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2017
---
# <a name="share-your-power-bi-dashboards-with-coworkers-and-others"></a>同僚や他のユーザーと自分の Power BI ダッシュボードを共有する
"*共有*" は、自分のダッシュボードおよびレポートに他のユーザーがアクセスできるようにするのによい方法です。 Power BI では、[複数の方法でダッシュボードで共同作業を行い](service-how-to-collaborate-distribute-dashboards-reports.md)、ダッシュボードを配布できますが、共有はその 1 つにすぎません。

![ダッシュボードの一覧での共有アイコン](media/service-share-dashboards/power-bi-share-dash.png)

共有を行うには、コンテンツの共有先が組織内でも組織外でも、共有元と共有先の両方に [Power BI Pro ライセンス](service-free-vs-pro.md)が必要です。または、コンテンツを [Premium 容量](service-premium.md)に格納する必要があります。 Power BI チームへのご提案は、 [Power BI コミュニティ サイト](https://community.powerbi.com/)でフィードバックをお送りください。

ダッシュボードは、独自のマイ ワークスペースまたはアプリ ワークスペースで共有することができます。 同僚とダッシュボードを共有した場合、共有された相手はダッシュボードの表示と対話操作を実行できますが、ダッシュボードを編集することはできません。 [行レベル セキュリティ (RLS)](service-admin-rls.md) を適用しない限り、自分のダッシュボードおよびレポートに表示されるものと同じデータが同僚にも表示されます。 共有元のユーザーが許可した場合、共有先のユーザーはダッシュボードを同僚と共有できます。 組織外のユーザーも、ダッシュボードの表示と対話操作を実行できますが、他のユーザーと共有することはできません。 

[任意の Power BI モバイル アプリからダッシュボードを共有する](mobile-share-dashboard-from-the-mobile-apps.md)こともできます。 ダッシュボードの共有は、Power BI Desktop からではなく、Power BI サービスおよび Power BI モバイル アプリから行うことができます。

## <a name="video-share-a-dashboard"></a>ビデオ: ダッシュボードの共有
Amanda が社内および社外の同僚とダッシュボードを共有するところをご覧ください。 その後、ビデオで説明されている手順に従って、ご自分でやってみてください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard"></a>ダッシュボードの共有
1. マイ ワークスペースまたはアプリ ワークスペースで、ダッシュボードを開き、**[共有]** ![共有アイコン](media/service-share-dashboards/power-bi-share-icon.png) を選びます。
2. 上部のボックスに、個々のユーザーの完全なメール アドレス、配布グループ、またはセキュリティ グループを入力します。 動的配布リストと共有することはできません。 
   
   アドレスが組織外のユーザーとも共有できますが、警告が表示されます。
   
   ![外部共有に関する警告](media/service-share-dashboards/power-bi-share-dialog-warning.png)  
3. 必要な場合はメッセージを追加します。 これはオプションです。
4. 同僚が他のユーザーとダッシュボードを再共有できるようにするには、**[受信者がダッシュボードを共有できるようにする]** をオンにします。
   
   他のユーザーに共有を許可することを "*再共有*" と呼びます。 共有を許可すると、そのユーザーは Power BI サービスやモバイル アプリから再共有したり、組織内の他のユーザーにメール招待状を転送したりできます。 招待状は 1 か月後に期限が切れます。 組織外のユーザーは、再共有を行えません。 ダッシュボードの所有者は、再共有を無効にしたり、個別に再共有を取り消したりできます。後の「[ダッシュボードの共有または他のユーザーによる再共有を停止する](service-share-dashboards.md#stop-sharing-a-dashboard-or-stop-others-from-sharing)」をご覧ください。
5. **[共有]** を選択します。
   
   ![[共有] ボタンを選ぶ](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI によって、共有するダッシュボードへのリンクを含む招待の電子メールが、グループではなく個人宛てに送信されます。**成功**通知が表示されます。 
   
   組織内の受信者がリンクをクリックすると、Power BI はダッシュボードをそのユーザーの **[自分と共有]** リスト ページに追加します。 自分の名前を選択すると、共有したすべてのダッシュボードが表示されます。 
   
   ![[自分と共有] リスト ページ](media/service-share-dashboards/power-bi-shared-with-me-list-page.png)
   
   組織外の受信者がリンクをクリックすると、ダッシュボードは表示されますが、通常の Power BI ポータルではありません。 詳しくは、後の「[組織外のユーザーとダッシュボードを共有する](service-share-dashboards.md#share-a-dashboard-with-people-outside-your-organization)」をご覧ください。

## <a name="who-has-access-to-a-dashboard-you-shared"></a>自分が共有したダッシュボードにアクセスできるユーザー
場合によっては、自分がダッシュボードを共有している相手や、その相手がダッシュボードを再共有しているユーザーを確認する必要があります。

1. ダッシュボードの一覧またはダッシュボード自体で、**[共有]** ![共有アイコン](media/service-share-dashboards/power-bi-share-icon.png) を選びます。 
2. **[ダッシュボードの共有]** ダイアログ ボックスで、**[アクセス]** を選びます。
   
    ![[ダッシュボードの共有] ダイアログ ボックスの [アクセス] タブ](media/service-share-dashboards/power-bi-share-dialog-access.png)
   
    組織外のユーザーは、 **[ゲスト]**として一覧に含められます。

## <a name="stop-sharing-a-dashboard-or-stop-others-from-sharing"></a>ダッシュボードの共有または他のユーザーによる再共有を停止する
再共有をオンおよびオフにできるのは、ダッシュボードの所有者のみです。

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>共有の招待をまだ送信していない場合
* 招待を送信する前に、招待の下部にある **[受信者がダッシュボードを共有できるようにする]** チェック ボックスをオフにします。

### <a name="if-youve-already-shared-the-dashboard"></a>ダッシュボードを既に共有している場合
1. ダッシュボードの一覧またはダッシュボード自体で、**[共有]** ![共有アイコン](media/service-share-dashboards/power-bi-share-icon.png) を選びます。 
2. **[ダッシュボードの共有]** ダイアログ ボックスで、**[アクセス]** を選びます。
   
    ![[ダッシュボードの共有] ダイアログ ボックスの [アクセス] タブ](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. **[読み取りと共有し直し]** の横にある省略記号 **[...]** をクリックして、以下を選択します。
   
   ![[読み取りと共有し直し] の省略記号](media/service-share-dashboards/power-bi-change-access.png)
   
   * そのユーザーが他のユーザーと共有できないようにするには、**[読み取り]** を選びます。
   * そのユーザーがダッシュボードをまったく表示できないようにするには、**[アクセスの削除]** を選びます。

4. **[アクセス許可の削除]** ダイアログ ボックスで、レポートやデータセットなど、関連するコンテンツへのアクセスを削除するかどうかを決定します。 警告アイコン ![Power BI の警告アイコン](media/service-share-dashboards/power-bi-warning-icon.png) が付いた項目を削除する場合、関連するコンテンツは正しく表示されなくなるため、削除することをお勧めします。

## <a name="share-a-dashboard-with-people-outside-your-organization"></a>組織外のユーザーとダッシュボードを共有する
組織外のユーザーと共有すると、共有相手は共有ダッシュボードへのリンクを含むメールを受け取ります。そのユーザーがダッシュボードを表示するには、Power BI にサインインする必要があります。 Power BI ライセンスがない共有相手は、リンクをクリックした後でサインアップできます。

サインインした後は、通常の Power BI ポータルではなく、左側にナビゲーション ウィンドウのない専用のブラウザー ウィンドウに共有ダッシュボードが表示されます。 共有相手がこのダッシュボードを後でアクセスできるようにするには、リンクにブックマークを設定する必要があります。

共有相手は、このダッシュボードまたはレポートのコンテンツを編集できません。 レポート内のグラフとの対話 (クロス強調表示) や、ダッシュボードに接続されたレポートで使用できるフィルターやスライサーの変更は可能ですが、その変更を保存することはできません。

共有ダッシュボードを表示できるのは、直接の共有相手だけです。 たとえば、Vicki@contoso.com にメールを送信した場合、ダッシュボードを見ることができるのは Vicki だけです。 他のユーザーは、たとえリンクを受け取っても、ダッシュボードを表示できません。また、Vicki は、同じ電子メール アドレスを使ってダッシュボードにアクセスする必要があります。 他の電子メール アドレスでサインアップした場合は、ダッシュボードにアクセスできません。

オンプレミスの Analysis Services の表形式モデルでロール レベルまたは行レベルのセキュリティが実装されている場合、組織外のユーザーはデータを何も表示できません。

Power BI モバイル アプリから組織外のユーザーにリンクを送信した場合、ユーザーがリンクをクリックすると、ダッシュボードは Power BI モバイル アプリではなくブラウザーで開きます。

## <a name="limitations-and-considerations"></a>制限事項と考慮事項
ダッシュボードの共有について留意すべき事項:

* 一般に、自分と仕事仲間はダッシュボード内の同じデータを表示することになります。 そのため、自分の方がより多くのデータを表示できるアクセス許可を持っている場合、相手はこちらのダッシュボードのすべてのデータを表示できることになります。 ただし、ダッシュボードの基礎になるデータセットに[行レベル セキュリティ (RLS)](service-admin-rls.md) が適用されている場合は、各ユーザーの資格情報を使用して各々がアクセスできるデータが決定されます。
* ダッシュボードのすべての共有相手は、[読み取りビュー](service-report-open-in-reading-view.md)であなたのダッシュボードを表示し、レポートを操作できます。 同僚はレポートを作成したり、既存のレポートへの変更を保存したりすることはできません。
* どの共有相手も、データセットの表示やダウンロードは行えません。
* [ダッシュボード データの更新](refresh-data.md)はだれでも手動で行えます。
* 電子メールに Office 365 を使用している場合は、配布グループに関連付けられた電子メール アドレスを入力することにより、配布グループのメンバーと共有できます。
* 自分と同じ電子メール ドメインに属している同僚と、ドメインが異なっていても同じテナントに登録されている同僚は、ダッシュボードを他のユーザーと共有できます。 たとえば、ドメイン contoso.com と contoso2.com が同じテナント内に登録されているとします。 自分の電子メール アドレスが konrads@contoso.com の場合、ravali@contoso.com と gustav@contoso2.com は、共有のアクセス許可が付与されていれば、共有が可能です。
* 同僚が既に特定のダッシュボードへのアクセスが可能な場合、自分がそのダッシュボードにいるときの URL をそのままコピーして、ダッシュボードへの直接リンクを送信できます。 例: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* 同様に、同僚が特定のダッシュボードに既にアクセスできる場合は、[基になるレポートへの直接リンクを送信する](service-share-reports.md)ことができます。 

## <a name="troubleshoot-sharing"></a>共有のトラブルシューティング

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>ダッシュボードの受信者に、タイルまたは「アクセス許可が必要」のメッセージにロック アイコンが表示される

共有相手がレポートを表示しようとしたときに、ダッシュボードにロックされたタイルが表示されたり、"アクセス許可が必要です" というメッセージが表示されたりすることがあります。

![Power BI のロックされたタイル](media/service-share-dashboards/power-bi-locked_tile_small.png)

その場合は、基になるデータセットへのアクセス許可を共有相手に付与する必要があります。 次にその方法を示します。

1. コンテンツ リストの **[データセット]** タブに移動します。

1. データセットの横にある省略記号 (**...**)、**[アクセス許可の管理]** の順に選択します。

    ![アクセス許可の管理](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

3. **[ユーザーの追加]** を選びます。

    ![[ユーザーの追加] を選択](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. 個々のユーザーの完全なメール アドレス、配布グループ、またはセキュリティ グループを入力します。 動的配布リストと共有することはできません。

    ![メール アドレスの追加](media/service-share-dashboards/power-bi-add-user-dataset.png)

5. **[追加]**を選択します。

### <a name="i-cant-share-a-dashboard"></a>ダッシュボードを共有できない

ダッシュボードを共有するには、基になるコンテンツ (関連するすべてのレポートやデータセット) を再共有するアクセス許可を持っている必要があります。 共有できませんというメッセージが表示された場合は、レポートの作成者にこれらのレポートおよびデータセットを再共有するアクセス許可を依頼してください。


## <a name="next-steps"></a>次の手順
* ご意見およびご提案がある場合は、 [Power BI コミュニティ サイト](https://community.powerbi.com/)をご利用ください。
* [ダッシュボードとレポートを共有する方法](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Power BI レポートのみを共有する](service-share-reports.md)
* わからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

