---
title: Power BI Desktop の例を指定して Web ページからデータを抽出する (プレビュー)
description: プルするデータの例を指定して Web ページからデータを抽出する
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 55c1a70e054b6bb6ff06c7fe6f83b58d8b1f26f3
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290984"
---
# <a name="get-data-from-a-web-page-by-providing-an-example-preview"></a>例を指定して Web ページからデータを取得する (プレビュー)

Web ページからのデータ取得を利用すると、ユーザーは Web ページからデータを簡単に抽出し、そのデータを **Power BI Desktop** にインポートすることができます。 ただし、多くの場合、Web ページ上のデータは、抽出が容易な整理されたテーブル形式ではないので、たとえ構造化され、一貫していても、そのようなページからデータを取得することは困難です。 

そこで解決策があります。 **[Get Data from Web by example]\(例を指定して Web からデータを取得する\)** 機能を使用すると、基本的にはコネクタ ダイアログで 1 つ以上の例を指定して抽出するデータを **Power BI Desktop** に示すことができます。その結果、指定した例に合うその他のデータが収集され、ページに表示されます。 この解決策を利用すると、テーブルで見つかったデータ*だけでなく*、その他のテーブル以外のデータなど、Web ページからあらゆる種類のデータを抽出できます。 

![例を指定して Web からデータを取得する](media/desktop-connect-to-web-by-example/web-by-example_01.png)


## <a name="enabling-the-preview-feature-get-data-from-web-by-example"></a>プレビュー機能の [Get Data from Web by example]\(例を指定して Web からデータを取得する\) を有効にする

**[Get Data from Web by example]\(例を指定して Web からデータを取得する\)** はプレビュー段階の機能なので、**Power BI Desktop** でこの機能を有効にする必要があります。 この機能を有効にするには、**[ファイル] > [オプションと設定] > [オプション] > [プレビュー機能]** の順に選択し、**[Web での新しいエクスペリエンス]** チェックボックスをオンにします。 選択を行った後、Power BI Desktop を再起動する必要があります。

![プレビュー機能を有効にする](media/desktop-connect-to-web-by-example/web-by-example_02.png)

プレビュー機能を有効にしたら、使い始める準備は完了です。 

## <a name="using-get-data-from-web-by-example"></a>[Get Data from Web by example]\(例を指定して Web からデータを取得する\) の使用

**[Get Data from Web by example]\(例を指定して Web からデータを取得する\)** を使用するには、**[ホーム]** リボン メニューから **[データを取得]** を選択します。 表示されるウィンドウで、左ウィンドウのカテゴリから **[その他]** を選択し、**[Web]** を選択します。

![[データを取得] から [Web] を選択する](media/desktop-connect-to-web-by-example/web-by-example_03.png)

ここから、データを抽出する Web ページの URL を入力します。 この記事では、Microsoft Store の Web ページを使用し、このコネクタのしくみを紹介します。 

この記事に従って操作する場合は、この記事で使用している [Microsoft Store の URL](https://www.microsoft.com/en-us/store/top-paid/games/xbox?category=classics) を利用できます。

    https://www.microsoft.com/en-us/store/top-paid/games/xbox?category=classics

![Web ダイアログ](media/desktop-connect-to-web-by-example/web-by-example_04.png)

**[OK]** を選択すると、**[ナビゲーター]** ダイアログが表示され、Web ページから自動検出されたテーブルが表示されます。 下図の例では、テーブルは見つかりませんでしたが、ページの下部に、**[Extract table using examples]\(例を使用してテーブルを抽出する\)** というボタンが表示されます。このボタンをクリックして例を指定できます。


![[ナビゲーター] ウィンドウ](media/desktop-connect-to-web-by-example/web-by-example_05.png)

**[Extract table using examples]\(例を使用してテーブルを抽出する\)** を選択すると、対話型ウィンドウが表示されます。ここでは、Web ページのコンテンツをプレビューし、抽出するデータのサンプル値を入力できます。 

この例では、ページ上のゲームごとに*名前*と*価格*を抽出します。 次の図に示すように、ページの各列からいくつかの例を指定することで、抽出することができます。 このように例を入力すると、**Power Query** (Web ページからデータを抽出する基礎となるテクノロジ) で、スマート データ抽出アルゴリズムを使用してサンプル エントリのパターンに適合するデータを抽出することができます。

![例を指定したデータ](media/desktop-connect-to-web-by-example/web-by-example_06.png)

Web ページから抽出されたデータに満足したら、**[OK]** を選択して **[クエリ エディター]** に移動します。クエリ エディターではさらに変換を適用したり、データを整形したりすることができます (このデータを他のデータ ソースと組み合わせるなど)。

![例を指定したデータ](media/desktop-connect-to-web-by-example/web-by-example_07.png)

そこからビジュアルを作成したり、**Power BI Desktop** レポートを作成するときに Web ページ データを使用したりすることができます。


## <a name="next-steps"></a>次の手順
**Power BI Desktop** を使用して接続できるデータの種類は他にもあります。 データ ソースの詳細については、次のリソースを参照してください。

* [例から列を追加する](desktop-add-column-from-example.md)
* [Web ページに接続する](desktop-connect-to-web.md)
* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop で Excel ブックに接続する](desktop-connect-excel.md)   
* [Power BI Desktop で CSV ファイルに接続する](desktop-connect-csv.md)   
* [Power BI Desktop にデータを直接入力する](desktop-enter-data-directly-into-desktop.md)   

