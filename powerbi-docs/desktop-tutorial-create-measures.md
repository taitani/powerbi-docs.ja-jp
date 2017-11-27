---
title: "チュートリアル: Power BI Desktop で独自のメジャーを作成する"
description: "チュートリアル: Power BI Desktop で独自のメジャーを作成する"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 653895d9cfa64c9029ce9441278adcc94d76a0a8
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2017
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>チュートリアル: Power BI Desktop で独自のメジャーを作成する
Power BI Desktop でメジャーを使用すると、強力なデータ分析ソリューションを作成できます。 メジャーは、ユーザーがレポートで操作するデータに対して計算を実行するために役立ちます。 このチュートリアルでは、メジャーの基本について説明し、独自のメジャーを Power BI Desktop で作成する手順を紹介します。

この記事は、Power BI Desktop を使用して高度なモデルを作成することに既に慣れている Power BI ユーザー向けに書かれています。 [データの取得] とクエリ エディターを使用してデータをインポートする操作、複数の関連したテーブルを取り扱う操作、およびレポート キャンバスにフィールドを追加する操作に既に習熟している必要があります。 Power BI Desktop を新しく使い始めたユーザーの場合は、まず「[Power BI Desktop の概要](desktop-getting-started.md)」をお読みください。

このチュートリアルの手順を実行するには、[Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) ファイルをダウンロードする必要があります。 このファイルには、Contoso, inc. という架空の会社のオンライン売上データが既に含まれています。ファイル内のデータはデータベースからインポートしたものであるため、データソースに接続したり、クエリ エディターで表示したりすることはできません。 自分のコンピューターに独自のファイルがある場合は、そのファイルを Power BI Desktop で開いてください。

## <a name="what-are-these-measures-all-about"></a>メジャーとは何か
メジャーは、ほとんどの場合、自動的に作成されます。たとえば、**Sales** テーブルのフィールドの一覧で **SalesAmount** フィールドの横のチェック ボックスをオンにしたり、**SalesAmount** をレポート キャンバスにドラッグしたりした場合に作成されます。

![](media/desktop-tutorial-create-measures/measurestut_salesamountinfieldlist.png)

次のように、新しい視覚化グラフが表示されます。

![](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

縦棒グラフに表示されるのは、SalesAmount フィールドからの売上値を合計した金額です。  この SalesAmount フィールドは、実際には、既にインポートした Sales テーブルに含まれる SalesAmount という名前の列です。

SalesAmount 列には、200 万行以上の売上高の値が含まれています。 これらすべての値の行を含むテーブルがなぜ表示されないのだろう、と疑問に感じるでしょうか。 Power BI Desktop は、SalesAmount 内の値がすべて数値データ型であることを認識しており、ユーザーはこれらの値を何らかの形で集計したい (合計、平均、カウントなど) だろうということも認識しています。

フィールドの一覧にシグマ アイコン ![](media/desktop-tutorial-create-measures/meastut_sigma.png) 付きで表示されるフィールドは、そのフィールドが数値であることを示しており、その値は集計することができます。 このケースでは、[SalesAmount] を選択すると、Power BI Desktop によって独自のメジャーが作成され、すべての売上額の合計が計算され、グラフに表示されます。

数値データ型を持つフィールドを選択した場合の既定の集計方法は合計ですが、非常に簡単に別の種類の集計に変更できます。

**[値]** 領域で、 **[SalesAmount]**の横にある下矢印をクリックし、 **[平均]**を選択することができます。

![](media/desktop-tutorial-create-measures/meastut_salesamountaverage.png)

視覚化グラフは、"SalesAmount" フィールド内のすべての売上値の平均に変わります。

![](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

集計の種類は、必要な結果に応じて変更できます。ただし、集計のすべての種類が数値データ型に適しているとは限りません。 たとえば、"SalesAmount" フィールドの合計と平均は意味をなします。 最小値と最大値にも意味があります。 しかし、カウントは SalesAmount フィールドではあまり意味をなしません。このフィールドの値は数値ですが、実際には金額だからです。

メジャーはすべて何らかの種類の集計を実行するので、集計について理解することは、メジャーについて理解することの土台になります。 合計という集計の使用例については、少し後で、独自のメジャーを作成するときに説明します。

メジャーから計算される値は、ユーザーがレポートを操作するのに合わせて常に変化します。 たとえば、 **Geography** テーブルから **RegionCountryName** フィールドをグラフにドラッグした場合、各国の売上金額の平均が計算されて表示されます。

![](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

ユーザーがレポートを操作した結果としてメジャーが変化した場合は、ユーザーがそのメジャーの *コンテキスト*に影響を与えたことになります。 実際のところ、ユーザーがレポートを操作するたびにコンテキストが変更され、メジャーは結果を計算して表示します。

ほとんどの場合、Power BI がそれを処理します。ユーザーが追加したフィールドとユーザーが選択した集計の種類に従って計算し、値を返します。 しかし、場合によっては、さらに複雑な固有の計算を実行するために独自のメジャーを作成する必要が生じることがあります。

Power BI Desktop では、Data Analysis Expressions (DAX) 数式言語を使用して独自のメジャーを作成できます。 DAX の数式は Excel の数式とよく似ています。 実際、DAX と Excel の数式では、多くの同じ関数、演算子、および構文を使用します。 ただし、DAX の関数は、リレーショナル データを処理し、ユーザーがレポートを操作するのに合わせて動的に計算を実行するように設計されています。

200 種類を超える DAX 関数は、Sum や Average などの簡単な集計から、さらに複雑な統計関数やフィルター処理関数まで、あらゆる処理を実行できます。 この記事では DAX 言語の詳細を説明しませんが、詳細を学習するために役立つ多くのリソースがあります。 このチュートリアルを終えた後は、「[Power BI Desktop における DAX の基本事項](desktop-quickstart-learn-dax-basics.md)」をぜひお読みください。

独自のメジャーを作成すると、指定した対象テーブルのフィールドの一覧にそのメジャーが追加されます。 これは、"*モデル*" メジャーと呼ばれ、フィールドとしてテーブルに残ります。 モデル メジャーの利点として、識別しやすいように自由に名前を付けることができます。 また、メジャーを他の DAX 式で引数として使用したり、複雑な計算を非常に高速に実行するメジャーを作成したりすることもできます。

## <a name="lets-create-our-own-measure"></a>独自のメジャーを作成する
たとえば、純売上高を分析するとします。 "Sales" テーブルのフィールド リストを見ても、"NetSales" という名前のフィールドは見つかりません。 しかし、純売上高を計算する独自のメジャーを作成するために必要な構成要素はあります。

必要なメジャーは、売上高から割引額と返品を減算するものです。 作成するメジャーを、視覚化グラフでどのようなコンテキストが設定されても結果を計算できるようにするため、実際には、SalesAmount の合計から DiscountAmount と ReturnAmount の合計を減算する必要があります。 今は少しわかりにくいかもしれませんが、心配しないでください。だんだん分かるようになります。

### <a name="net-sales"></a>純売上高
1.  フィールドの一覧で **Sales** テーブルを右クリックするか、下矢印をクリックしてから、**[新しいメジャー]** をクリックします。 これは、見つけやすくするために、新しいメジャーを Sales テーブル内に保存するための操作です。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    > [!TIP]
    > Power BI Desktop の [ホーム] タブで、リボンの [新しいメジャー] ボタンをクリックして、新しいメジャーを作成することもできます。
    > 
    > ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    > 
    > リボンからメジャーを作成する場合は、そのメジャーを任意のテーブル内に作成できます。 メジャーを特定のテーブルに所属させなければならないという規則はないので、論理的にわかりやすいテーブル内に作成すれば、見つけやすくなります。 特定のテーブルに所属させる場合は、まずそのテーブルをクリックしてアクティブにします。 その後、[新しいメジャー] をクリックします。 このチュートリアルでは、最初のメジャーを Sales テーブル内に作成します。
    > 
    > 
    
    レポート キャンバスの上部に数式バーが表示されます。 数式バーでは、メジャーの名前を変更したり、DAX 数式を入力したりできます。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
    まず、新しいメジャーに名前を付けます。 新しいメジャーの既定の名前は "Measure" です。 名前を変更しないで別のメジャーを作成した場合は、"Measure 2"、"Measure 3"、以下同様、というメジャー名が付けられます。 このチュートリアルで作成する新しいメジャーには、識別しやすくするために、Net Sales (純売上) という名前を付けます。
    
2. 数式バーで **Measure** を強調表示してから、「**Net Sales**」と入力します。
    
    これで、数式の入力を開始できます。
    
3.  等号の後に、「**S**」と入力します。ドロップダウンに候補リストが表示され、"S" で始まるすべての DAX 関数が列挙されます。さらに文字を入力すると、候補リストが絞り込まれて、必要な関数を見つけやすくなります。 下へスクロールして **[SUM]** を選択し、Enter キーを押します。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    Enter キーを押すと、始めかっこが表示され、別の候補リストに、SUM 関数に渡すことのできるすべての列が表示されます。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    式は、常に、始めかっこと終わりかっこの間に入ります。 入力する式には SUM 関数に渡す 1 つの引数が入り、このチュートリアルでは合計する列です。 列の候補リストは、指定する列名の先頭から文字を入力していくと、絞り込むことができます。 このチュートリアルでは、SalesAmount 列を指定する必要があります。そこで、「salesam」と入力すると、リストの表示数が減り、選択できる 2 つの項目が表示されます。 この 2 つは、実際には同じ列です。 1 つは、"[SalesAmount]" です。SalesAmount 列が属しているのと同じテーブル内にメジャーを作成しているからです。 もう 1 つは、列名の前にテーブル名が付いています。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
    一般に、列の完全修飾名を入力することをお勧めします。 これは、数式を読みやすくするためです。
    
4. **Sales[SalesAmount]** を選択し、終わりかっこを入力します。
    
    > [!TIP]
    > 構文エラーが最も発生しやすいケースは、終わりかっこの入力漏れか、入力位置の間違いです。
    > 
    > 
    
    次に、他の 2 つの列を減算します。
    
5.  最初の式の終わりかっこの後に、スペースを入力してから、マイナス演算子 (**-**) を入力し、その後にもう 1 つスペースを入力します。 その後に別の SUM 関数を入力し、その引数として **Sales[DiscountAmount]** 列を入力します。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
    数式を入力する領域が足りなくなってきました。 問題はありません。
    
6.  数式バーの右側にある下向きのシェブロンをクリックします。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)
    
    入力する領域が増えます。 改行してから数式の新しい部分を入力するには、Alt キーを押しながら Enter キーを押します。 Tab キーを使用して場所を空けることもできます。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)
    
    これで、数式の最後の部分を追加できます。
    
7.  マイナス演算子を追加し、もう 1 つの SUM 関数を追加して、その引数として **Sales[ReturnAmount]** 列を選択します。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
    これで、数式の準備ができました。

8.  Enter キーを押すか、数式バーにあるチェック マークをクリックして、入力を完了します。 数式が検証され、Sales テーブルのフィールドの一覧に追加されます。

### <a name="lets-add-our-new-measure-to-a-report"></a>次に、新しいメジャーをレポートに追加してみましょう。
この時点で、Net Sales メジャーをレポート キャンバスに追加できます。これを追加すると、レポートに追加したその他のすべてのフィールドに対して純売上高が計算されます。 国別の純売上高を見てみましょう。

1.  **Net Sales** メジャーを **Sales** テーブルからレポート キャンバスにドラッグします。
    
2. 次に、**RegionCountryName** フィールドを **Geography** テーブルからグラフにドラッグします。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
    さらにデータを追加してみましょう。
    
3.  **SalesAmount** フィールドをグラフにドラッグして、純売上高と売上高の差を確認します。
    
    これで、本当に 2 つのメジャーがあるグラフができました。 自動的に合計された SalesAmount メジャーと、このチュートリアルで作成した Net Sales メジャーです。 どちらのメジャーの場合も、グラフにある別のフィールド、つまり [RegionCountryName] テーブルの国名のコンテキストで結果が計算されます。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)
    
    ここで、スライサーを追加して、純売上高と売上高を、カレンダー年でさらに分類できるようにしましょう。
    
4.  グラフの横に空白の領域をクリックしてから、**[視覚化]** で [テーブル] 視覚化をクリックします。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktablevisbutton.png)
    
    これで、空白のテーブルの視覚化がレポート キャンバスに作成されます。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
5.  **Year** フィールドを **Calendar** テーブルから新しい空白のテーブルにドラッグします。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
    Year は数値フィールドであるため、Power BI Desktop によってその値が合計されてグラフに表示されます。 しかし、これではスライサーとして機能しません。
    
6. **[値]** で、**[Year]** の横の下矢印をクリックして、**[集計しない]** をクリックします。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
    これで、[Year] フィールドのテーブル視覚化をスライサーに変更できるようになります。

    7.  **[視覚化]** で **[スライサー]** 視覚化をクリックします。

    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
    これで、Year がスライサーになりました。 1 つの年、または年グループを選択すると、レポートの視覚化グラフがそれに応じてスライスされます。
    
8. 次に、**[2013]** をクリックします。 グラフが変化するはずです。 "Net Sales" メジャーと "SalesAmount" メジャーが再計算され、2013 年分だけの新しい結果が表示されます。 この場合もまた、ユーザーがコンテキストを変更したのに合わせて、メジャーが計算され、結果が表示されました。
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

## <a name="lets-create-another-measure"></a>別のメジャーを作成する
これで、独自のメジャーを作成する方法がわかりましたので、別のメジャーを作成してみましょう。

### <a name="net-sales-per-unit"></a>単位あたりの純売上高
単位あたりの売上高が最も多い製品を見つけるにはどうしたらよいでしょうか?

別のメジャーを作成するという方法があります。 この場合は、純売上高を販売個数で割ります。 実際には、このチュートリアルで作成した Net Sales メジャーの結果を Sales[SalesQuantity] の合計で除算することになります。

1.  **Net Sales per Unit** という名前の新しいメジャーを、Sales テーブルまたは Products テーブル内に作成します。
    
    このメジャーでは、以前に作成した Net Sales メジャーを利用することにします。 DAX では、他のメジャーを数式から参照できます。
    
2.  「**Net Sales**」と入力を開始します。 追加可能な項目が候補リストに表示されます。 **[Net Sales]**を選択します。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    また、始め角かっこ (**[**) を入力するだけで、別のメジャーを参照することもできます。 候補リストには、現在の数式に追加できるメジャーだけが表示されます。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  **[Net Sales]** の直後にスペースを入力し、次に除算演算子 (**/**) を入力し、SUM 関数を入力し、「**Quantity**」と入力します。 候補リストに、名前に「Quantity」が含まれるすべての列が表示されます。 **Sales[SalesQuantity]**を選択します。 数式は、次のようになるはずです。
    
    > **Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])**
    > 
    > 
    
    なかなか良いと思いませんか。 DAX エディターの検索および候補リストの機能を使用すると、DAX 数式をとても簡単に入力できます。 ここで、新しい Net Sales per Unit メジャーで取得できるデータを見てみましょう。
    
4. **Net Sales per Unit** メジャーをレポート キャンバスの空白の領域にドラッグします。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
    まったく興味を惹かれせんね。 心配しないでください。
    
5.  グラフの視覚エフェクトの種類を **[ツリー マップ]** に変更します。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. 次に、**ProductCategory** フィールドを **ProductCategory** テーブルから **[グループ]** 領域にドラッグします。
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
    これはなかなかよい情報です。しかし、製品ごとに純売上高を表示するとどうなるでしょうか。
    
7. **ProductCategory** フィールドを削除し、代わりに **ProductName** フィールドを **Product** テーブルから **[グループ]** 領域にドラッグします。 
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
    これは単なる演習ですが、非常に優れた機能だと思いませんか! もちろん、このツリー マップをフィルター処理する方法はほかにもありますが、このチュートリアルでは扱っていません。

## <a name="what-weve-learned"></a>チュートリアルの復習
メジャーは、データから洞察を得るための強力な道具です。 数式バーを使用してメジャーを作成する方法を学習しました。 メジャーにはわかりやすい名前を自由に付けることができます。候補リストを使用すると、適切な要素を見つけて選択し、メジャーの数式に簡単に追加できます。 また、コンテキストについても学習しました。それは、メジャーの計算結果が他のフィールドに従って変化すること、またはメジャーの数式にある他の式によって変化することを指します。

## <a name="next-steps"></a>次の手順
DAX の数式についてさらに詳しく知りたい場合や、さらに高度なメジャーを作成する場合は、「[Power BI Desktop での DAX の基本事項](desktop-quickstart-learn-dax-basics.md)」をご覧ください。 この記事では、構文、関数、およびコンテキストの詳しい理解など、DAX の基本的な概念について説明します。

また、「[Data Analysis Expressions (DAX) リファレンス](https://msdn.microsoft.com/library/gg413422.aspx)」を、ぜひお気に入りに追加してください。 DAX の構文、演算子、および 200 種類を超える DAX 関数について詳細を調べることができます。

