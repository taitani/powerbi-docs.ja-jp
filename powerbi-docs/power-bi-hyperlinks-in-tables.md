---
title: テーブルにハイパーリンクを追加する
description: Power BI Desktop を使用してハイパーリンクを作成します。 レポートのテーブルとマトリックスにハイパーリンクを追加するのに Power BI Desktop または Power BI サービスのいずれかを使用します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/09/2019
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: 9611d8cd45eba89854fd6cbb485c52097f77f4c0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "61421581"
---
# <a name="add-hyperlinks-to-a-table"></a>テーブルにハイパーリンクを追加する
このトピックでは、Power BI Desktop を使ってハイパーリンクを作成する方法を説明します。 次に、Desktop または Power BI サービスを使って、レポートのテーブルとマトリックスにハイパーリンクを追加します。 

![ハイパーリンク付きのテーブル](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> [!NOTE]
> 内のハイパーリンクを作成することができます[ダッシュ ボードでタイル](service-dashboard-edit-tile.md)と[ダッシュ ボードのテキスト ボックス](service-dashboard-add-widget.md)-その場で Power BI サービスを使用します。 内のハイパーリンクを作成する[レポート内のテキスト ボックス](service-add-hyperlink-to-text-box.md)-その場で Power BI サービスと Power BI Desktop を使用します。
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>Power BI Desktop を使ってテーブルまたはマトリックスにハイパーリンクを作成するには
テーブルや、Power BI サービスではなく、Power BI Desktop でマトリックス内のハイパーリンクを作成できます。 Power BI にブックをインポートする前に、Excel Power Pivot でハイパーリンクを作成できます。 この後、この両方の方法について説明します。

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>Power BI Desktop でテーブルまたはマトリックスのハイパーリンクを作成する
ハイパーリンクを追加する手順は、データのインポートまたはデータとの接続に DirectQuery を使用したかどうかによって異なります。 この後、この両方の場合について説明します。

### <a name="for-data-imported-into-power-bi"></a>Power BI にインポートしたデータの場合
1. ハイパーリンクがデータセット内のフィールドとして存在していない場合は、Desktop を使用し、[カスタム列](desktop-common-query-tasks.md)として追加します。
2. データ ビューで、その列を選び、 **[モデリング]** タブで **[データ カテゴリ]** のドロップダウンを選びます。
   
    ![[データ カテゴリ] のドロップダウン リスト](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. **[Web URL]** を選びます。
4. レポート ビューに切り替え、Web URL としてカテゴリ化されたフィールドを使用してテーブルまたはマトリックス作成します。 ハイパーリンクは、青色で下線付きの表示です。

    ![青色で下線付きのリンク](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)

    > [!NOTE]
    > URL は、**http:// 、 https://** 、**www** のいずれかで始まっている必要があります。
    >
   
1. テーブルに長い URL が表示されないようにするには、代わりにハイパーリンク アイコン  ![ハイパーリンク アイコン](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) を表示できます。 マトリックスにはアイコンを表示できないことに注意してください。
   
    グラフを選んでアクティブにします。

    書式設定アイコンを選択する ![ペイント ローラー アイコン](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) を選んで [書式設定] タブを開きます。

    **[値]** を展開し、 **[URL アイコン]** を探して、 **[オン]** にします。

    ![アイコンの URL を有効にします。](media/power-bi-hyperlinks-in-tables/power-bi-url-icon-on.png)

1. (省略可能) [レポートを Desktop から Power BI サービスに発行](guided-learning/publishingandsharing.yml?tutorial-step=2)し、Power BI サービスでレポートを開きます。 ハイパーリンクは同様に機能します。

### <a name="for-data-connected-with-directquery"></a>DirectQuery を使用して接続したデータの場合
DirectQuery モードでは新しい列を作成できません。  ただし、データに URL が既に含まれている場合は、それらの URL をハイパーリンクに変えることができます。

1. レポート ビューで、URL が含まれるフィールドを使用してテーブルを作成します。
2. その列を選び、 **[モデリング]** タブで **[データ カテゴリ]** のドロップダウンを選びます。
3. **[Web URL]** を選びます。 ハイパーリンクは、青色で下線付きの表示です。
4. (省略可能) [レポートを Desktop から Power BI サービスに発行](guided-learning/publishingandsharing.yml?tutorial-step=2)し、Power BI サービスでレポートを開きます。 ハイパーリンクは同様に機能します。

## <a name="create-a-table-or-matrix-hyperlink-in-excel-power-pivot"></a>Excel Power Pivot でテーブルまたはマトリックスのハイパーリンクを作成する
Power BI のテーブルおよびマトリックスにハイパーリンクを追加するもう 1 つの方法は、Power BI からデータセットにインポート/接続する前に、そのデータセット内でハイパーリンクを作成することです。 この例では Excel ブックを使います。

1. Excel でブックを開きます。
2. **[PowerPivot]** タブを選び、 **[管理]** を選びます。
   
   ![Excel で PowerPivot を開く](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
1. PowerPivot が開いたら、 **[詳細設定]** タブを選びます。
   
   ![PowerPivot の [詳細設定] タブ](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. Power BI テーブル内でハイパーリンクに変換する URL が含まれている列に、カーソルを置きます。
   
   > [!NOTE]
   > URL は、**http:// 、 https://** 、**www** のいずれかで始まっている必要があります。
   > 
5. **[レポートのプロパティ]** グループで、 **[データ カテゴリ]** ドロップダウンを選び、 **[Web URL]** を選びます。 
   
   ![Excel 内の [データ カテゴリ] ドロップダウン リスト](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)

6. Power BI サービスまたは Power BI Desktop から、このブックに接続するか、このブックをインポートします。
7. [URL] フィールドが含まれるテーブル視覚化を作成します。
   
   ![Power BI で [URL] フィールド付きのテーブルを作成する](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング
質問:カスタム URL を、テーブルまたはマトリックス内のハイパーリンクとして使用できますか。    
回答:いいえ。 リンク アイコンを使用できます。 ハイパーリンク用のカスタム テキストが必要で、URL の一覧が短い場合には、代わりにテキスト ボックスを使うことができます。


## <a name="next-steps"></a>次の手順
[Power BI レポートでの視覚化](visuals/power-bi-report-visualizations.md)

[Power BI - 基本的な概念](consumer/end-user-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

