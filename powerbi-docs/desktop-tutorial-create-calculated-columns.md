---
title: "チュートリアル: Power BI Desktop で計算列を作成する"
description: "チュートリアル: Power BI Desktop で計算列を作成する"
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: acdaa95908cd03006170eb06ddfc780c836c64ac
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>チュートリアル: Power BI Desktop で計算列を作成する
ときどき、分析しているデータに、必要とする結果の取得に必要な特定のフィールドが含まれていないことがあります。 これが、計算列が入る場所です。 計算列は、列の値を定義するのに Data Analysis Expressions (DAX) 数式を使用します。 この値は、ほとんど何でも可能です。モデル内にある異なるいくつかの列のテキスト値をまとめたものでも、他の値からの数値の計算でも可能です。 たとえば、データに ([フィールド] の一覧のフィールドとして) [市区町村] 列と [都道府県] 列があるとします。しかし、単一値として両方を持つ [地域] フィールドを 1 つ必要としています (「Miami、FL」 など)。 これこそまさに計算列の目的です。

計算列は、メジャーと同様 DAX 数式に基づきますが、使い方が異なります。 メジャーが最も使用されるのは、テーブルの行にある他のフィールドに基づいて結果を計算するための視覚化の [値] 領域です。また、視覚化の [軸] や [凡例]、[グループ] 領域でも使用されます。 一方、計算列が使用されるのは、テーブル内の行や、[軸] 領域、[凡例] 領域、または [グループ] 領域内の行の列の結果が必要な場合です。

このチュートリアルでは、計算列について説明し、独自の計算列を Power BI Desktop で作成する手順を紹介します。 Power BI Desktop を使用して高度なモデルを作成することに既に慣れている Power BI ユーザー向けに書かれています。 また、クエリを使用してデータをインポートする操作、複数の関連したテーブルを取り扱う操作、およびレポート キャンバスにフィールドを追加する操作に既に習熟している必要もあります。 Power BI Desktop を新しく使い始めたユーザーの場合は、まず「[Power BI Desktop の概要](desktop-getting-started.md)」をお読みください。

このチュートリアルの手順を実行するには、[Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) ファイルをダウンロードする必要があります。 これは、「[Power BI Desktop で独自のメジャーを作成する](desktop-tutorial-create-measures.md)」チュートリアルで使用しているのと同じサンプル ファイルです。 このファイルには、Contoso, inc. という架空の会社の売上データが既に含まれています。ファイル内のデータはデータベースからインポートしたものであるため、データソースに接続したり、クエリ エディターで表示したりすることはできません。 自分のコンピューターに独自のファイルがある場合は、そのファイルを Power BI Desktop で開いてください。

## <a name="lets-create-a-calculated-column"></a>計算列を作成しましょう
たとえば、[携帯電話]－[アクセサリ]、[携帯電話]－[スマートフォンおよび PDA] などのように、行の単一の値に、製品カテゴリを製品サブカテゴリと一緒に表示するとします。 レポート ビューまたはデータ ビューで (ここではレポート ビューを使用します)、製品テーブルのフィールドの一覧を見ると、必要なフィールドがないことが分かります。 しかし、ProductCategory フィールドと ProductSubcategory フィールドはあります。それぞれ、独自のテーブルにあります。

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

新しい計算列を作成し、その 2 つの列の値を結合して、新しい列の新しい値にします。 興味深いことに、2 つの異なるテーブルのデータを、1 つの列に結合する必要があります。 DAX を使用して新しい列を作成するため、既存のモデルの機能を最大限活用することができます。これには、異なるテーブル間に既に存在するリレーションシップが含まれます。

### <a name="to-create-a-productfullcategory-column"></a>ProductFullCategory 列を作成するには
1.  フィールド リストで **ProductSubcategory** テーブルを右クリックするか、下矢印をクリックしてから、**[新しい列]** をクリックします。 これにより、新しい列が ProductSubcategory テーブルに追加されます。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)
    
    レポート キャンバスまたはデータ グリッドの上部に数式バーが表示されます。 数式バーで、列の名前を変更したり、DAX 数式を入力したりできます。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)
    
    既定では、新しい計算列の名前は "Column" です。 名前を変更しないで別の列を作成した場合は、"Column 2"、"Column 3"、以下同様、という列名が付けられます。 列をより識別しやすくするために、新しい列に新しい名前を付けます。
    
2.  **Column** という名前は既に数式バーで強調表示されているため、「**ProductFullCategory**」と入力するだけです。
    
    これで、数式の入力を開始できます。 新しい列の値が ProductCategory テーブルの ProductCategory 名から始まるようにします。 この列は異なる (しかし関連する) テーブルにあるため、[RELATED](https://msdn.microsoft.com/library/ee634202.aspx) 関数を使用して取得します。
    
3.  等号の後に、「**R**」と入力します。ドロップダウンに候補リストが表示され、"R" で始まるすべての DAX 関数が列挙されます。さらに文字を入力すると、候補リストが絞り込まれて、必要な関数を見つけやすくなります。 関数の隣に、関数の説明が表示されます。 下へスクロールして **[RELATED]** を選択し、Enter キーを押します。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)
    
    始めかっこが表示され、別の候補リストに、RELATED 関数に渡すことのできるすべての列が表示されます。 必要なパラメーターの説明と詳細も表示されます。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)
    
    式は、常に、始めかっこと終わりかっこの間に入ります。 今回のケースでは、式には、RELATED 関数に渡される単一の引数が含まれます (値が戻される関連列)。 列の一覧が自動的に絞り込まれ、関連する列だけが表示されます。 今回のケースでは、必要なのは ProductCategory テーブル内の ProductCategory 列です。
    
    **ProductCategory[ProductCategory]**を選択してから、閉じかっこを入力します。
    
    > [!TIP]
    > 構文エラーが最も発生しやすいケースは、終わりかっこの入力漏れか、入力位置の間違いです。 ただし多くの場合、忘れていても Power BI Desktop が追加してくれます。
    > 
    > 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)
    
4. ダッシュ記号を個々の値に追加したいので、最初の式の閉じかっこの後ろに、スペース、アンパサンド (&)、引用符、スペース、ダッシュ (-)、スペース、閉じ引用符、アンパサンドを入力します。 数式は、次のようになるはずです。
    
    **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & " - " &**
    
    > [!TIP]
    > 数式バーの右側にある下向きのシェブロンをクリックすると、数式エディターが展開されます。 下の行に移動するには Alt と Enter を押し、場所を開けるには Tab を押します。
    > 
    > 
    
5.  最後に、もう 1 つ左角かっこを入力し、**[ProductSubcategory]** 列を選択して、数式を完成させます。 数式は、次のようになるはずです。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)
    
    お気づきのとおり、ProductSubcategory 列を呼び出す 2 番目の式では、RELATED 関数を使用しませんでした。 これは、この列は、新しい列を作成しているテーブルと同じテーブル内に既にあるためです。 [ProductCategory] は、テーブル名とともに入力することも (完全修飾)、テーブル名を省略して入力することもできます (非修飾)。
    
6.  Enter を押すか、数式バーのチェック マークをクリックして、数式を完成させます。 数式が検証され、 **ProductSubcategory** テーブルのフィールド リストに追加されます。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)
    
    お気づきのとおり、計算列はフィールドの一覧で特別なアイコンを取得します。 これは、数式が含まれていることを示しています。 Power BI Desktop では単に次のように表示されます。 PowerBI サービス (Power BI サイト) では数式を変更できないため、計算列のフィールドにはアイコンが含まれません。
    
## <a name="lets-add-our-new-column-to-a-report"></a>次に、新しい列をレポートに追加してみましょう。
これで、新しい ProductFullCategory 列をレポート キャンバスに追加できるようになりました。 ProductFullCategory ごとの SalesAmount を見てみましょう。

**[ProductFullCategory]** 列を **[ProductSubcategory]** テーブルから [レポート] キャンバスにドラッグし、 **[SalesAmount]** フィールドを **[Sales]** テーブルからグラフにドラッグします。

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>別の計算列を作成する
これで、計算列を作成する方法がわかりましたので、別の計算列を作成してみましょう。

Power BI Desktop モデルの Contoso Sales のサンプルには、アクティブ ストアと非アクティブ ストアの両方の販売データが含まれます。 非アクティブ ストアで表示されるデータはそのように識別されることを明確にしたいと思います。 実際、Active StoreName というフィールドが必要です。 そのために、別の列を作成します。 今回のケースでは、ストアが非アクティブのときに、ストアの名前を “Inactive” として表示するための新しい Active StoreName 列が (フィールドとして) 必要です。しかし、アクティブ ストアになったときにはストアの実際の名前を表示します。

幸い、Stores テーブルには Status という列があります。その列の値は、アクティブ ストアの場合は On、非アクティブ ストアの場合は Off となります。 Status 列の各行の値をテストし、新しい列に新しい値を作成できます。

### <a name="to-create-an-active-storename-column"></a>Active StoreName 列を作成するには
1.  **Active StoreName** という新しい計算列を **Stores** テーブルに作成します。
    
    この列に対して、DAX 数式は各ストアの状況をチェックします。 ストアの状態がオンの場合は、数式はストアの名前を返します。 オフになっている場合は、“Inactive” の名前になります。 これを行うには、論理関数 [IF](https://msdn.microsoft.com/library/ee634824.aspx) を使用して、ストアの状況をテストし、結果が true と false の場合にそれぞれ特定の値を返します。
    
2.  **IF** の入力を開始します。 追加可能な項目が候補リストに表示されます。 **[IF]**を選択します。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)
    
    IF の最初の引数は、論理テストです。 ストアの状態が “On” かどうかをテストします。
    
3.  開きかっこ (**[**) を入力します。これにより、Stores テーブルから列を選択できます。 **[Status]** を選択します。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)
    
4.  **[Status]** の直後に「**="On"**」を入力し、コンマ (**,**) を入力して、2 つ目の引数を入力します。 ツールヒントにより、結果が true になるときの値を追加するよう提案されます。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)
    
5.  ストアが On の場合、ストアの名前を表示することにします。 左角かっこ (**[**) を入力し、**[StoreName]** 列を選択して、もう 1 つコンマを入力します。これにより、3 つ目の引数を入力できます。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)
    
6.  結果が false になった場合の値を追加する必要があります。今回のケースでは、値を **"Inactive"** にします。
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)
    
7.  Enter を押すか、数式バーのチェック マークをクリックして、数式を完成させます。 数式が検証され、Stores テーブルのフィールド リストに追加されます。
    
    他のフィールドと同様、新しい Active StoreName 列を視覚化で使用できます。 このチャートでは、状況が "On" になっているストアは名前別に個別に表示されますが、状況が "Off" になっているストアはグループ化され、"Inactive" として示されます。 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)
    
## <a name="what-weve-learned"></a>チュートリアルの復習
計算列は、データを充実させ、より簡単に洞察が得られるようになります。 数式バーを使用して計算列を作成する方法、候補の一覧を使用する方法、および新しい列に最もふさわしい名前を付ける方法を学びました。

## <a name="next-steps"></a>次の手順
DAX の数式についてさらに詳しく知りたい場合や、さらに高度な DAX の数式で計算列を作成する場合は、「[Power BI Desktop における DAX の基本事項](desktop-quickstart-learn-dax-basics.md)」をご覧ください。 この記事では、構文、関数、およびコンテキストの詳しい理解など、DAX の基本的な概念について説明します。

また、「[Data Analysis Expressions (DAX) リファレンス](https://msdn.microsoft.com/library/gg413422.aspx)」を、ぜひお気に入りに追加してください。 DAX の構文、演算子、および 200 種類を超える DAX 関数について詳細を調べることができます。

