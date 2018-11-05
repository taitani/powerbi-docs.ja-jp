---
title: Power BI サービスでレポートを表示する
description: Power BI レポートを読み取りビューで開きます。
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/10/2018
ms.author: mihart
ms.openlocfilehash: 4d37c1389628078466d8fedb290d928c3f02e7d5
ms.sourcegitcommit: dc8b8a2cf2dcc96ccb46159802ebd9342a7fa840
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49112017"
---
# <a name="view-a-report-in-power-bi-service-apppowerbicom"></a>Power BI サービスでレポートを表示する (app.powerbi.com)
レポートは、ビジュアルで構成される 1 つまたは複数のページです。 レポートは Power BI *レポート デザイナー*で作成され、[ユーザーと直接共有されます](end-user-shared-with-me.md)。あるいは[アプリ](end-user-apps.md)の一部として共有されます。 

レポートはさまざまな方法で開くことができます。そのうちの 2 つを紹介します。ホーム ページから開く方法とダッシュボードから開く方法です。 

<!-- add art-->


## <a name="open-a-report-from-your-home-page"></a>ホーム ページからレポートを開く
それでは、ユーザーと直接共有されているレポートを開いてみましょう。その後で、アプリの一部として共有されたレポートを開いてみましょう。

   ![ホーム ページ](./media/end-user-report-open/power-bi-home.png)

### <a name="open-a-report-that-has-been-shared-with-you"></a>ユーザーと共有されているレポートを開く
Power BI *デザイナー*では、上部メニュー バーの **[共有]** ボタンをクリックすることでレポートを直接共有できます。 この方法で共有されたコンテンツは左のナビゲーション バーの **[共有アイテム]** コンテナーとホーム ページの **[共有アイテム]** セクションに表示されます。

1. Power BI サービスを開きます (app.powerbi.com)。

2. 左のナビゲーション バーから **[ホーム (プレビュー)]** を選択し、ホーム ページを開きます。  

   ![ホーム ページ](./media/end-user-report-open/power-bi-select-home.png)
   
3. **[共有アイテム]** が表示されるまで下方向にスクロールします。 レポート アイコン ![レポート アイコン](./media/end-user-report-open/power-bi-report-icon.png) を見つけます。 このスクリーンショットには、*Financial* と *Northwind* という 2 つのレポートがあります。 
   
   ![ホーム ページの [共有アイテム] セクション](./media/end-user-report-open/power-bi-shared.png)

4. レポート カードの 1 つを選択し、レポートを開きます。

   ![レポート ページ](./media/end-user-report-open/power-bi-report1.png)

5. 下にタブが並んでいます。 各タブはレポート *ページ*を表します。 現在、*IT Spend Trend* ページを開いています。 別のタブを選択し、そのレポート ページを開きます。 

   ![レポート ページ タブ](./media/end-user-report-open/power-bi-tabs.png)

6. この時点ではレポート ページの一部だけが表示されます。 ページの表示 (ズーム) を変更するには、**[表示]**、**[ページに合わせる]** の順に選択します。

   ![ズームの変更](./media/end-user-report-open/power-bi-fit.png)

   ![ページに合わせる](./media/end-user-report-open/power-bi-report2.png)

### <a name="open-a-report-that-is-part-of-an-app"></a>アプリの一部となっているレポートを開く
同僚や AppSource からアプリを受け取っている場合、そのアプリはホーム ページと左のナビゲーション バーの **[アプリ]** コンテナーから利用できます。 [アプリ](end-user-apps.md)はダッシュボードとレポートをまとめたものです。

1. 左のナビゲーション バーから **[ホーム (プレビュー)]** を選択し、ホーム ページに戻ります。

7. **[マイ アプリ]** が表示されるまで下方向にスクロールします。

   ![ホーム ページ](./media/end-user-report-open/power-bi-my-apps.png)

8. アプリの 1 つを選択して開きます。 アプリでは、アプリ *デザイナー*によって設定されたオプションに基づき、ダッシュボードまたはレポートが開きます。 アプリを選択し、
    - レポートが開いた場合、そこで操作はおしまいです。
    - ダッシュボードが開いた場合、下の「[ダッシュボードからレポートを開く](#Open-a-report-from-a-dashboard)」を参照してください。



## <a name="open-a-report-from-a-dashboard"></a>ダッシュボードからレポートを開く
レポートはダッシュボードから開くことができます。 ほとんどのダッシュボード タイルはレポートから*ピン留め*されています。 タイルを選択すると、タイルの作成に使用されたレポートが開きます。 

1. ダッシュボードからタイルを選択します。 この例では、"Total Units YTD..." という縦棒グラフ タイルを選択しています。

    ![タイルが選択されているダッシュボード](./media/end-user-report-open/power-bi-dashboard.png)

2.  関連付けられているレポートが開きます。 "YTD Category" ページが表示されていることがわかります。 これは、ダッシュボードから選択した縦棒グラフを含むレポート ページです。

    ![読み取りビューで開かれたレポート](./media/end-user-report-open/power-bi-report-new.png)

> [!NOTE]
> 一部のタイルはレポートに関連付けられていません。 [Q&A を使用して作成](../service-dashboard-pin-tile-from-q-and-a.md)されたタイルを選択すると、Q&A 画面が開きます。 [ダッシュボードの **[タイルの追加]** ウィジェットで作成された](../service-dashboard-add-widget.md)タイルを選択すると、**[タイルを編集]** ウィザードが開きます。  


##  <a name="still-more-ways-to-open-a-report"></a>レポートを開く他の方法
Power BI サービスのナビゲーションに慣れてくると、最適なワークフローを見つけ出すことができます。 レポートにアクセスする他の方法をいくつか以下に示します。
- 左のナビゲーション ウィンドウにある **[お気に入り]** と **[最近]** を使用する    
- [[関連の表示]](end-user-related.md) を使用する    
- メールで (他のユーザーに[共有してもらう](../service-share-reports.md)場合、または自分で[アラートを設定する](../service-set-data-alerts.md)場合)    
- 自分の [通知センター] から (end-user-notification-center.md)    
- その他

## <a name="next-steps"></a>次の手順
[レポートはさまざまな方法で操作](end-user-reading-view.md)できます。  最初に、レポート キャンバスの下部にある各タブを選択してみましょう。

