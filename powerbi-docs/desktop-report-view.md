---
title: Power BI Desktop のレポート ビュー
description: Power BI Desktop のレポート ビュー
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 5026de163aa870c042fe4c3a13b6ff3fbf8849f0
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290800"
---
# <a name="report-view-in-power-bi-desktop"></a>Power BI Desktop のレポート ビュー
Power BI を操作したことがあるユーザーは、レポートを作成して動的なパースペクティブとデータへの洞察を得ることがいかに簡単であるかをご存知でしょう。 Power BI では、Power BI Desktop にさらに多くの高度な機能を備えています。 Power BI Desktop を使用すると、高度なクエリの作成、複数のソースからのデータのマッシュアップ、テーブル間のリレーションシップの作成などを行えます。

Power BI Desktop には、**[レポート] ビュー**が含まれています。ここでは、視覚化を含む任意の数のレポート ページを作成することができます。 [レポート] ビューには、Power BI サービスのレポートの [編集] ビューとほとんど同じデザイン機能が用意されています。 視覚化の移動、コピーと貼り付け、マージなどを行うことができます。

これらの相違点は、Power BI Desktop を使用すると、データのクエリとモデルを操作して、レポートでの最適な分析を支えるデータが確実に得られるようになることです。 その後、Power BI Desktop のファイルは、ローカルのドライブまたはクラウドに関係なく、お好みの場所に保存することができます。

## <a name="lets-take-a-look"></a>では、見てみましょう。
最初にデータを Power BI Desktop に読み込むとき、**[レポート] ビュー**が空白のキャンバスであることがわかります。

![](media/desktop-report-view/pbi_reportviewinpbidesigner_reportview.png)

左側のナビゲーション バーのアイコンを選択して、**[レポート] ビュー**、**[データ] ビュー**、**[リレーションシップ] ビュー**の間で切り替えることができます。

![](media/desktop-report-view/pbi_reportviewinpbidesigner_changeview.png)

一部のデータを追加すると、キャンバスの新しい視覚化にフィールドを追加できます。

![](media/desktop-report-view/pbid_reportview_addvis.gif)

視覚化の種類を変更するには、リボンの **[視覚化]** グループから視覚化を選択するか、右クリックして **[視覚化の種類を変更]** アイコンから別の視覚化を選択します。

![](media/desktop-report-view/pbid_reportview_changevis.gif)

> [!TIP]
> 必ず複数の視覚化の種類をお試しください。 データの情報を明確に伝える視覚化を使用することが重要です。
> 
> 

レポートは、1 つ以上の空白ページから開始します。 ページは、キャンバスの左側にある [ナビゲーター] ウィンドウに表示されます。 あらゆる種類の視覚化をページに追加できますが、過剰にならないように注意します。 ページに視覚化が多すぎると、込み入った表示になり、適切な情報を見つけにくくなります。 レポートには新しいページを追加することができます。 リボンの **[新しいページ]** をクリックするだけです。

![](media/desktop-report-view/pbidesignerreportviewnewpage.png)

ページを削除するには、[レポート] ビューの下部にあるページのタブで、**[X]** をクリックします。

![](media/desktop-report-view/pbi_reportviewinpbidesigner_deletepage.png)

> [!NOTE]
> レポートと視覚化は、Power BI Desktop からダッシュボードにピン留めすることはできません。 これを行うには、Power BI サイトに [[Power BI Desktop からの発行]](desktop-upload-desktop-files.md) を行う必要があります。

## <a name="hide-report-pages"></a>レポート ページを非表示にする

レポートを作成するとき、レポートからページを非表示にすることもできます。 これは、レポートで基になるデータやビジュアルを作成する必要があるが、そのページを他のユーザーに見せたくない場合に便利です。他のレポート ページで使用されているテーブルや補助ビジュアルを作成するときなどです。 その他にも、制作上のさまざまな理由から、レポート ページを作成しても、公開するレポートではそれを非表示にすることがあります。 

レポート ページは簡単に非表示にできます。 レポート ページ タブを右クリックし、表示されたメニューから **[非表示]** を選択するだけです。

![](media/desktop-report-view/report-view_05.png)

レポート ページを非表示にするとき、注意すべきことがいくつかあります。

* ページのタイトルが淡色表示になっていても、**Power BI Desktop** の使用中、非表示レポート ページを見ることができます。次の画像ではページ 4 が非表示です。

    ![](media/desktop-report-view/report-view_06.png)

* **Power BI サービス**でレポートを表示するとき、非表示レポート ページを表示することは*できません*。

* レポート ページを非表示にすることは、セキュリティ対策では*ありません*。 ユーザーはこの非表示ページにアクセスできます。ドリルスルーやその他の手段でページのコンテンツにアクセスできます。

* ページが非表示のときは、表示モードでも表示モード ナビゲーションの矢印が表示されません。

