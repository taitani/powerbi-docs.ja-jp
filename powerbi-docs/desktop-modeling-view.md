---
title: Power BI Desktop でモデルリング ビューを使用する (プレビュー)
description: Power BI Desktop でモデリング ビューを使用して、複雑なデータセットをビジュアル形式で表示させます
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 67a04f1ae1bd5858aa4413c77a6d98ac5a04d32f
ms.sourcegitcommit: 6a6f552810a596e1000a02c8d144731ede59c0c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51620102"
---
# <a name="modeling-view-in-power-bi-desktop-preview"></a>Power BI Desktop でのモデルリング ビュー (プレビュー)

**Power BI Desktop** の**モデルリング ビュー**を使用すると、多くのテーブルを含む複雑なデータセットを表示して操作することができます。 モデリング ビューを使用すると、次の操作を実行できます。


## <a name="enabling-the-modeling-view-preview-feature"></a>モデリング ビューのプレビュー機能の有効化

モデリング ビュー機能はプレビュー段階であり、**Power BI Desktop** で有効にする必要があります。 モデリング ビューを有効にするには、**[ファイル] > [オプションと設定] > [オプション] > [プレビュー機能]** の順に選択してから、次の図のように **[モデリング ビュー]** チェック ボックスをオンにします。

![Power BI Desktop でモデリング ビューのプレビュー機能を有効にする](media/desktop-modeling-view/modeling-view_01.png)

プレビュー機能を有効にするためには、**Power BI Desktop** を再起動する必要があるというメッセージが表示されます。 

![プレビュー機能を有効にするために Power BI Desktop を再起動する](media/desktop-modeling-view/modeling-view_01b.png)

## <a name="using-modeling-view"></a>モデルリング ビューの使用

モデルリング ビューにアクセスするには、次の図のように、**Power BI Desktop** の左側にある [モデルリング ビュー] アイコンを選択します。

![Power BI Desktop のモデルリング ビュー アイコン](media/desktop-modeling-view/modeling-view_02.png)

## <a name="creating-separate-diagrams"></a>個別のダイアグラムの作成

モデリング ビューを使用すると、モデル内のテーブルのサブセットのみを含む、モデルのダイアグラムを作成できます。 これによって作業するテーブルにわかりやすいビューを導入することができ、複雑なデータセットを操作しやすくなります。 テーブルのサブセットのみを使用して新しいダイアグラムを作成するには、Power BI Desktop のウィンドウの下部にある **[すべてのテーブル]** タブの隣にある **+** 記号をクリックします。

![タブ セクションの + 記号をクリックして新しいダイアグラムを作成する](media/desktop-modeling-view/modeling-view_03.png)

その後、**[フィールド]** 一覧からダイアグラムの画面上にテーブルをドラッグします。 テーブルを右クリックし、表示されるメニューから **[関連テーブルを追加する]** を選択します。

![テーブルを右クリックして [関連テーブルを追加する] を選択する](media/desktop-modeling-view/modeling-view_04.png)

実行すると、元のテーブルに関連するテーブルが新しいダイアグラムに表示されます。 **[関連テーブルを追加する]** メニュー オプションを選択した後に関連テーブルが表示されている様子を、次の図に示します。

![関連テーブルの表示](media/desktop-modeling-view/modeling-view_05.png)

## <a name="setting-common-properties"></a>共通プロパティの設定

**CTRL** キーを押したまま複数のテーブルをクリックすることで、モデリング ビューで一度に複数のオブジェクトを選択することができます。 複数のテーブルを選択すると、それらがモデルリング ビュー内で強調表示されます。 複数のテーブルが強調表示されている場合、**[プロパティ]** ウィンドウで適用した変更は選択したテーブルすべてに対して適用されます。

たとえば、ダイアグラム ビューにある複数のテーブルの[ストレージ モード](desktop-storage-mode.md)を変更するには、**CTRL** キーを押しながらテーブルを選択した後、**[プロパティ]** ウィンドウでストレージ モードの設定を変更します。

![CTRL キーを押しながら複数のテーブルを選択した後、選択したテーブル全体の共通プロパティを設定する](media/desktop-modeling-view/modeling-view_06.png)


## <a name="next-steps"></a>次の手順

以下の記事では、データ モデルと DirectQuery について詳しく説明しています。

* [Power BI Desktop での集計 (プレビュー)](desktop-aggregations.md)
* [Power BI Desktop の複合モデル (プレビュー)](desktop-composite-models.md)
* [Power BI Desktop のストレージ モード (プレビュー)](desktop-storage-mode.md)
* [Power BI Desktop (プレビュー) での多対多のリレーションシップ](desktop-many-to-many-relationships.md)


DirectQuery に関する記事:

* [Power BI で DirectQuery を使用する](desktop-directquery-about.md)
* [Power BI の DirectQuery でサポートされるデータ ソース](desktop-directquery-data-sources.md)
