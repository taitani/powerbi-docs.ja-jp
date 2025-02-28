---
title: 美しいレポートを作成するためのヒント
description: Power BI サービス と Power BI Desktop でレポートを作成するときのヒントとテクニックです
author: davidiseminger
manager: kfile
ms.reviewer: willthom
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: davidi
LocalizationGroup: Reports
ms.openlocfilehash: 4d686a807d9413c15b19ff382e5ac54fb696b10b
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721360"
---
# <a name="tips-and-tricks-for-creating-reports-in-power-bi-desktop-and-power-bi-service"></a>Power BI Desktop と Power BI サービスでのレポート作成のヒントとテクニック
データを最大限に活用するには、少しのヒントが必要な場合があります。 Microsoft Power BI Desktop、Power BI サービス、"*および*" Power Pivot のアドインを有効にし、Power Query をインストールして有効にした Microsoft Excel 2016 または Excel 2013 Pro-Plus エディションで、レポートを作成する場合に役立つヒントとテクニックをまとめました。

## <a name="power-bi-desktop"></a>Power BI Desktop

### <a name="learning-to-use-the-query-editor"></a>クエリ エディターの使用方法
Power BI Desktop のクエリ エディターは、Excel 2013 の Power Query アドイン機能に似ています。 Power BI サポートにも役立つ記事がありますが、support.office.com にある Power Query に関する資料を最初に読まれることをお勧めします。

[Power Query リソース センター](https://support.office.com/article/Microsoft-Power-Query-for-Excel-Help-2b433a85-ddfb-420b-9cda-fe0e60b82a94)から追加情報を取得できます。

また、[式の参照](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f)を表示することもできます。

### <a name="data-types-in-query-editor"></a>クエリ エディターのデータ型
Power BI Destop でクエリ エディターを使用するときには、最善の推測によってデータ型の検出が行われます。  数式を使用する場合、列にデータ型の設定が保持されないことがあります。 データを初めてクエリ タブに読み込んだ後、先頭行を見出しとして設定した後、列を追加した後、Group by の後、Merge の後、Append の後、データを初めて読み込む前には、列のデータ型が正しいことをご確認ください。

データ グリッド内の斜体部分はデータ型が正しく設定されていることを表しているのではなく、単にテキストとして扱われないことを意味しているということを忘れないでください。

### <a name="reference-queries-in-the-query-editor"></a>クエリ エディターでのクエリの参照
Power BI Desktop のクエリ エディターのナビゲーターでいずれかのクエリを右クリックすると、"参照" 用として指定できるオプションが表示されます。  これは、次の理由により便利です。

* クエリのデータ ソースとしてファイルを使用すると、ファイルの絶対パスがクエリに保存されます。 Power BI Desktop ファイルまたは Excel ブックを共有または移動するときは、パスを 1 つ 1 つ更新するよりも、Power BI Desktop ファイルまたは Excel ブックを 1 回だけ更新してパスを更新する方が時間を短縮できます。

既定では、すべてのクエリが Excel ワークシートまたはデータ モデル (あるいはその両方) に読み込まれます。 一部のクエリは中間的な手順であり、エンドユーザー向けのものではありません。  既に説明したように、クエリを参照する場合は、その多くがこれに該当します。  クエリの読み込み動作を制御するには、ナビゲーターでクエリを右クリックし、[読み込みを有効にする] オプションを切り替えます。  [読み込みを有効にする] の横にチェック マークが表示されない場合、そのクエリはクエリ タブで引き続き使用可能であり、他のクエリとともに使用できます。  特に、Merge、Append、および Reference 変換と組み合わせて使用すると便利です。  ただしクエリの結果はデータ モデルに読み込まれないため、クエリがレポートのフィールドの一覧やデータ モデルを乱雑にすることはありません。

### <a name="scatter-charts-need-a-point-identifier"></a>散布図にはポイント識別子が必要
一例として、気温と時刻の単純なテーブルがあり、これらの値を読み取ったとしましょう。 これを散布図に直接プロットする場合、Power BI はすべての値を 1 点に集約します。 個々のデータ ポイントを表示するためには、フィールド内の詳細バケットにフィールドを追加します。   Power BI Desktop でこれを簡単に行うには、クエリ タブの [列の追加] リボンにある [インデックス列の追加] オプションを使います。

### <a name="reference-lines-in-your-report"></a>レポート内の参照行
Power BI Desktop の計算列を使って、参照行を定義できます。  参照行を作成するテーブルと列を識別します。  リボンで [新しい列] を選択し、数式バーに次の数式を入力します。

    Target Value = 100

この計算列は、使用されている場所に関係なく、値 100 を返します。  フィールドの一覧に新しい列が表示されます。  [ターゲット値] 計算列を折れ線グラフに追加すると、一連の値と特定の参照行との関連性がわかります。  

### <a name="sort-by-another-column"></a>別の列を基準とした並べ替え
カテゴリ別 (文字列) の値を Power BI でグラフの軸に使用する場合、またはスライサーやフィルターで使用する場合、既定の順序はアルファベット順です。 曜日や月の名前のように、アルファベット順をオーバーライドする必要がある場合は、Power BI Desktop に別の列を基準に並べ替えるように指示します。詳細については、「[Power BI Desktop における列による並べ替え](desktop-sort-by-column.md)」をご覧ください。

### <a name="building-maps-more-easily-with-hints-to-bing"></a>Bing にヒントを与えることでより簡単にマップを作成
Power BI は Bing と統合されており、既定のマップ座標 (ジオコーディングと呼ばれるプロセス) を提供するため、マップを簡単に作成できます。  Bing はいくつかのアルゴリズムとヒントを使用して適切な場所を取得しようとしますが、あくまでも最善の推測に過ぎません。 ジオコーディングの正確性を高めるために、次のヒントを使用してください。

マップを作成するとき、国、都道府県、市区町村をプロットすることがよくあります。  Power BI Desktop では、住所指定の後で列の名前を指定すると、Bing による推測結果の正確性が増します。 たとえば、「カリフォルニア」や「ワシントン」などの米国の州名を入力するフィールドがある場合、Bing は「ワシントン」という語からワシントン州ではなくワシントン DC を返す可能性があります。  この列に「州」という名前を付けておけば、ジオコーディングが改善されます。  同様に、列には "国" や "市区町村" のように名前を付けます。   

この指定は、複数の国や地域のコンテキストではあいまいになることもあります。  国や地域によっては、「州」と呼ばれるものが、「都道府県」や「郡」などと呼ばれる場合があります。  ジオコーディングの正確性を増すには、作成する列に複数のフィールドを追加し、それらのフィールドをデータの場所のプロットに使用します。  たとえば、"Wiltshire" という値のみを渡すのではなく、"Wiltshire, England" という値を渡せば、ジオコーディング結果の正確性が高まります。

これにより、Power BI サービスおよび Power BI Desktop において特定の緯度と経度を組み合わせた場所を必ず提供できるようになります。  このとき、場所のフィールドも渡しておかないと、データが既定どおりに集約されるため、緯度と経度で示される場所が期待どおりの場所でなくなる可能性があります。

### <a name="categorizing-geographic-fields-to-hint-bings-geocoding"></a>Bing のジオコーディングにヒントを与える地理的フィールドの分類
フィールドを正確にジオコーディングするもう 1 つの方法、データ フィールドにデータ カテゴリを設定することです。   Power BI Desktop で目的のテーブルを選択し、[詳細設定] リボンに移動し、データ カテゴリを [住所]、[市区町村]、[大陸]、[国/地域]、[国]、[郵便番号]、または [都道府県] に設定します。  これらのデータのカテゴリは、Bing で日付を正しくエンコードするために役立ちます。 詳細については、「[Power BI Desktop でのデータ分類](desktop-data-categorization.md)」を参照してください。

### <a name="better-geocoding-with-more-specific-locations"></a>ジオコーディングの正確性を増すために場所を詳細に指定
マッピング用のデータ カテゴリの設定だけでは不十分な場合があります。  Power BI Desktop のクエリ エディターを使用すると、番地などの詳細な場所指定を作成できます。  [列の追加] 機能を使用して、カスタム列を作成します。  その後、次のように必要な場所指定を作成します。

    = [Field1] & " " & [Field2]

この結果のフィールドをマップ表示で使用します。 これは、データ セットによくある配送先住所フィールドから番地を作成するときに非常に便利です。  注意しなければならないのは、連結がテキスト フィールドにしか機能しない点です。  必要に応じて、番地をテキスト データ型に変換してから、住所の作成に使用してください。

### <a name="histograms-in-the-query-stage"></a>クエリ ステージのヒストグラム
Power BI Desktop ではヒストグラムを複数の方法で作成できます。最初は最も簡単な方法です。

最も単純なヒストグラム - ヒストグラム作成の基準とするフィールドが含まれているクエリを判別します。  クエリの [参照] オプションを使用して、新しいクエリを作成し、"FieldName Histogram" という名前を付けます。 [変換] リボンの [グループ化] オプションを使用し、[行のカウント] 集計を選択します。  結果の集計列のデータ型が数値であることを確認してください。 その後、このデータをレポート ページで視覚化します。  これは短時間で簡単に作成できますが、データ ポイントの数が多い場合はうまく機能せず、ビジュアル間でのブラッシングは許可されません。

バケットを定義してヒストグラムを作成 - ヒストグラム作成の基準とするフィールドが含まれているクエリを判別します。  クエリの [参照] オプションを使用して、新しいクエリを作成し、"FieldName" という名前を付けます。  ルールを使用してバケットを定義します。  [列の追加] リボンの [カスタム列の追加] オプションを使用し、カスタム ルールを作成します。  次に、バケットの単純なルールの例を示します。

    if([FieldName] \< 2) then "\<2 min" else
    if([FieldName] \< 5) then "\<5 min" else
    if([FieldName] \< 10) then "\<10 min" else
    if([FieldName] \< 30) then "\<30 min" else
    "longer")

結果の集計列のデータ型が数値であることを確認してください。 「最も単純なヒストグラム」で説明した手法でグループを使用して、ヒストグラムを完成させます。  このオプションでは、より多くのデータ ポイントを処理しますが、ブラッシングはやはり使用できません。

ブラッシングをサポートするヒストグラムを定義 - ブラッシングとは、ビジュアルが相互リンクされている状態を表します。つまり、あるビジュアルでユーザーがデータ ポイントを選ぶと、レポート ページの他のビジュアルでは、選ばれたデータ ポイントに関連するデータ ポイントが強調表示またはフィルター処理されます。  クエリ時にはデータを操作するので、テーブル間のリレーションシップを作成し、どの詳細項目がヒストグラムのバケットに関連するか、またその逆方向の関連性を把握しておく必要があります。

プロセスを開始するため、ヒストグラム作成の基準とするフィールドが含まれているクエリの「参照」オプションを使用します。  新しいクエリに "Buckets" という名前を付けます。  この例では元のクエリを "Details" と呼ぶことにしましょう。  次に、ヒストグラムのバケットとして使用する列以外の列をすべて削除します。  その後、クエリの [重複の削除] 機能を使用します。この機能は、列を選択したときに右クリック メニューとして表示されます。そのため、列では残りの値は固有の値になります。   10 進数がある場合は、「バケットを定義してヒストグラムを作成」のヒントを使用すると、管理可能なバケットのセットを取得できます。  ここで、クエリのプレビューに表示されるデータを確認します。  空白の値または null が表示される場合は、それらを修正してからリレーションシップを作成する必要があります。  「データに null または空白の値が含まれている場合のリレーションシップの作成」を参照してください。   この方法では並べ替えが必要となるため、問題が生じる可能性があります。  バケットを正しく並べ替えるには、「並べ替えの順序: カテゴリを必要な順序で表示」を参照してください。  

>[!NOTE]
>ビジュアルを作成する前に並べ替え順序を考えておくことをお勧めします。   

プロセスの次の手順では、バケットの列で "Buckets" クエリと "Details" クエリのリレーションシップを定義します。  Power BI Desktop のリボンで **[リレーションシップ管理]** をクリックします。  "Buckets" が左側のテーブル、"Details" が右側のテーブルに表示されるリレーションシップを作成し、ヒストグラムに使用するフィールドを選択します。

最後の手順は、ヒストグラムの作成です。  "Buckets" テーブルから [バケット] フィールドをドラッグします。  結果として得られる縦棒グラフから、既定のフィールドを削除します。  その後、"Details" テーブルのヒストグラム フィールドを同じビジュアルまでドラッグします。  このフィールドで、既定の集計を [カウント] に変更します。  これでヒストグラムの完成です。 ツリーマップのようなビジュアルを "Details" テーブルから作成する場合は、ツリーマップのデータ ポイントを選択して、ヒストグラムの強調表示を確認し、データセット全体の傾向に関連する選択済みデータ ポイントのヒストグラムを表示します。

### <a name="histograms"></a>ヒストグラム
Power BI Desktop では、計算フィールドを使ってヒストグラムを定義できます。  ヒストグラム作成の基準とするテーブルと列を識別します。  計算領域で、次の数式を入力します。

> Frequency:=COUNTROWS(\<Column Name\>)
>
>

変更を保存し、レポートに戻ります。  \<Column Name\> と Frequency をテーブルに追加してから、横棒グラフに変換します。  \<Column Name\> は x 軸、計算済みの Frequency フィールドは y 軸です。

### <a name="tips-and-tricks-for-creating-relationships-in-power-bi-desktop"></a>Power BI Desktop におけるリレーションシップ作成のヒントとテクニック
複数のソースから詳細なデータ セットを読み込むと、多くの場合、null 値、空白値、または重複する値などが問題となってリレーションシップを作成できません。

例を見てみましょう。

アクティブなカスタマー サポート要求からデータセットを読み込み、スキーマを含む作業項目の別のデータセットをさらに読み込む場合は、次のようになります。

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName }
>
>

特定のカスタマー名 (CustomerName) に関連するすべてのインシデント (Incident) と作業項目 (WorkItem) を追跡する場合、これらの 2 つのデータセット間のリレーションシップは簡単には作成できません。  一部の WorkItem が CustomerName に関連していない可能性があり、そのフィールドは空白または null になります。  特定の CustomerName の WorkItem と CustomerIncident に複数のレコードが存在する場合があります。  

#### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-null-or-blank-values"></a>データに null または空白の値が含まれている場合の Power BI Desktop でのリレーションシップの作成
データのセットには多くの場合、null または空白の値を持つ列が含まれています。  これにより、リレーションシップを使用しようとすると、問題が発生することがあります。  この問題に対処するためのオプションは、基本的に 2 つあります。  1 つ目のオプションは、null または空白の値を持つ行を削除する方法です。  削除するには、クエリ タブでフィルター機能を使用します。また、クエリをマージしている場合は、[一致する行だけを保持する] オプションを選択します。 2 つ目のオプションは、null または空白の値を、リレーションシップで機能する値 (一般的には "NULL" や "(Blank)" などの文字列) に置き換える方法です。   この時点で適切なアプローチがない - クエリ ステージにおいて行をフィルターで除外すると、行が削除され、概要統計情報や計算に影響を及ぼす可能性があります。  後者のアプローチでは、そのデータ行が保持されますが、関連のない行がモデルに関連するように見える可能性があるため、計算ミスにつながります。  後者のソリューションを採用する場合は、必要に応じてビューやグラフでフィルター処理を使用して、正確な結果が得られていることを確認してください。  最も重要なのは、どの行を保持し、どの行を削除するかを評価すること、および分析への全体的な影響を理解することです。  

#### <a name="creating-relationships-in-power-bi-desktop-when-the-data-has-duplicate-values"></a>データに重複する値が含まれている場合の Power BI Desktop でのリレーションシップの作成
複数のソースから詳細なデータセットを読み込むと、多くの場合、重複する値が原因となってリレーションシップを作成できません。  この問題を克服するには、両方のデータ セットの一意の値を使用してディメンション テーブルを作成します。

例を見てみましょう。

アクティブなカスタマー サポート要求からデータセットを読み込み、スキーマを含む作業項目の別のデータセットをさらに読み込む場合は、次のようになります。

> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, Status} WorkItems: {WorkItemID, IncidentID, WorkItemName, OpenedDate, Status, CustomerName }
>
>

特定のカスタマー名 (CustomerName) に関連するすべてのインシデント (Incident) と作業項目 (WorkItem) を追跡する場合、これらの 2 つのデータ セット間のリレーションシップは簡単には作成できません。  一部の WorkItem が CustomerName に関連していない可能性があり、そのフィールドは空白または null になります。  CustomerNames テーブルに空白の値または null が含まれている場合にも、リレーションシップを作成できません。「データに null または空白の値が含まれている場合のリレーションシップの作成」を参照してください。  1 つの CustomerName に複数の WorkItem と CustomerIncident が存在する場合があります。  

この場合、リレーションシップを作成するには、2 つのデータセットのすべての CustomerName の論理データセットを作成する必要があります。  論理データセットを作成するには、[クエリ] タブで次のシーケンスを使用します。

1. 両方のクエリを複製し、最初のクエリに **Temp** 、2 番目のクエリに **CustomerNames**という名前を付けます。
2. 各クエリで、CustomerName 列 *以外* のすべての列を削除します。
3. 各クエリで  **[重複を削除]** を使用します。
4. **CustomerNames** クエリで、リボンの **[追加]** オプションを選択し、 **Temp**クエリを選択します。
5. **CustomerNames** クエリで **[重複を削除]** を選択します。

これで、相互にすべての値を含む CustomerIncidents と WorkItems を関連付けるために使用できるディメンション テーブルが作成されました。  

### <a name="patterns-to-jump-start-your-use-of-the-query-editor"></a>クエリ エディターの使用をジャンプ スタートできるパターン
クエリ エディターは非常に強力なツールで、整形するデータを操作したり、クリーンアップして視覚化またはモデル化に備えたりすることができます。 覚えておくべきパターンがいくつかあります。

#### <a name="temporary-columns-can-be-deleted-after-computing-a-result"></a>結果の計算後に一時的な列を削除可能
Power BI Desktop では、多くの場合、複数の列のデータを 1 つの新しい列に変換する計算を作成する必要があります。  これは複雑な計算になる可能性があります。  この問題を解決するための簡単な方法の 1 つは、操作を複数の手順に分解する方法です。  まずは最初の列を複製します。 次に、手順を一時列に作成します。 さらに、最終的な結果の列を作成します。  ここで一時列を削除しておけば、最終的なデータセットは乱雑になりません。 これが可能なのは、クエリ タブでは手順が順序どおり実行されるからです。

#### <a name="duplicate-or-reference-queries-followed-by-merge-to-original-query"></a>クエリの複製または参照の後に元のクエリへのマージを実行
データセットの概要統計情報を計算すると便利な場合があります。  この計算を簡単に実行するには、クエリ タブでクエリを複製または参照します。その後、 **[グループ化]** を使用して、概要統計情報を計算します。  元のデータ内のデータを正規化して、それらが比較可能になるようにする上で、概要統計情報は役立ちます。  これは特に、個々の値を全体と比較する場合に役立ちます。  これを行うには、元のクエリに移動し、マージ オプションを選択します。  その後、適切な識別子に一致する概要統計情報クエリからデータをマージします。  これで、分析に必要な場合にデータを正規化する準備ができました。

### <a name="using-dax-for-the-first-time"></a>DAX を初めて使用する場合
DAX は、Power BI Desktop で使用される計算式言語です。  それは BI の分析のために最適化されています。  これまでに使ったことがある言語が SQL のようなクエリ言語のみの場合、使用感が若干異なります。 DAX を学習するための非常に優れたリソースがオンラインにも出版物としても存在します。

[Power BI Desktop における DAX の基本事項を学習する](desktop-quickstart-learn-dax-basics.md)

[Data Analysis Expressions (DAX) リファレンス](https://msdn.microsoft.com/library/gg413422.aspx)

[DAX リソース センター](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)

## <a name="power-bi-service-and-power-bi-desktop"></a>Power BI サービス "*および*" Power BI Desktop

### <a name="read-the-whitepaper-principles-for-designing-power-bi-reportsvisualspower-bi-visualization-best-practicesmd"></a>次のホワイトペーパーをお読みください:「[Power BI レポートのデザインの原則](visuals/power-bi-visualization-best-practices.md)」
このホワイト ペーパーでは、Power BI でレポートをデザインするためのベスト プラクティスについて説明します。 計画から始めて、レポートと、レポートを構成するページおよび個々のビジュアルに適用できる、デザインの原則について説明します。 これらのベスト プラクティスの多くは、ダッシュボードのデザインにも当てはまります。

### <a name="read-andor-watch-how-to-design-visually-stunning-reports-and-dashboards-in-power-bi"></a>"Power BI で視覚的に美しいレポート (とダッシュボード) をデザインする方法" を読む/見る
コミュニティ メンバーである Miguel Myers は、データ サイエンティスト兼グラフィック デザイナーです。

![](media/power-bi-reports-tips-and-tricks-for-creating/power-bi-reports.png)

* [ブログを読む](https://powerbi.microsoft.com/blog/how-to-design-visually-stunning-reports/)
* [ウェビナーを見る](https://info.microsoft.com/CO-PowerBI-WBNR-FY16-04Apr-19-Design-Reports-in-PowerBI-Registration.html)

### <a name="consider-your-audience"></a>閲覧者をよく考える
閲覧者の意思決定に役立つ重要なメトリックは何でしょうか。 レポートはどのように使われるのでしょうか。 学習された (つまり文化的な) どんな前提が、デザインの選択に影響を与える可能性がありますか。 閲覧者が成功するためにどのような情報が必要ですか。

レポートはどのようなデバイスで表示されますか。 大型のモニターの場合、より多くのコンテンツを配置できます。 閲覧者がタブレットに表示する場合は、視覚エフェクトの数を少なくする方が読みやすくなります。

### <a name="tell-a-story-and-keep-it-to-one-screen"></a>ストーリーを持たせ、それを 1 つの画面に収める
レポートの各ページでは、ストーリーが一目でわかる必要があります。 スクロール バーがページに表示されないようにできますか。 レポートが乱雑またはにぎやかすぎませんか。  不可欠な情報以外のすべてを削除して、読みやすく、分かりやすいものにします。

### <a name="make-the-most-important-information-biggest"></a>最も重要な情報を最も大きくする
レポート ページ上のテキストと視覚エフェクトがすべて同じサイズの場合、閲覧者は最も重要なことを見つけるのに苦労します。 たとえば、次のようなカードの視覚化は、重要な数値を目立つように表示するための優れた方法です。  
![カード視覚エフェクト](media/service-dashboards-design-tips/pbi_card.png)

### <a name="but-be-sure-to-provide-context"></a>ただし、必ずその意味を示す  

テキスト ボックスやヒントなどの機能を使って、視覚エフェクトにコンテキストを追加します。

### <a name="put-the-most-important-information-in-the-upper-corner"></a>最も重要な情報は、上部の隅に配置する
たいていの人は上から下に向かって情報を読むため、概要の情報は上部に配置し、より詳しい情報は閲覧者が読み進む方向 (左から右、または右から左) で下に向かって配置していきます。

### <a name="use-the-right-visualization-for-the-data-and-format-it-for-easy-reading"></a>データに適した視覚エフェクトを使用し、見やすく書式設定する
趣向を変えて変化をつけるためだけにさまざまな視覚化を使用することは避けてください。  視覚化は絵を描くように作成し、しかも読みやすく分かりやすいものにしてください。  データや視覚化によっては、シンプルなグラフの視覚化で十分です。 ただし、データの中にはより複雑な視覚化が必要になるものもあります。その場合は、必ずタイトル、ラベル、およびその他のカスタマイズを活用して、閲覧者に理解しやすいようにしてください。  

* 事実を歪曲するグラフ、つまり 3-D グラフやゼロから始まっていないグラフの使用には注意してください。 人間の脳は円形のものを解読することがより困難であることに留意してください。 円グラフ、ドーナツ グラフ、ゲージ、およびその他の円形の種類のグラフは見栄えはよいですが、代わりに使用できる別のビジュアルがあるはずです。    
* 軸上のグラフの目盛、グラフのディメンションの順序、およびグラフ内のディメンション値に使用する色と調和させます。    
* 量的なデータを必ず読みやすくエンコードします。 数値を表示する場合、数字を 3 ～ 4 桁までにしてください。 小数点の左側に 1 桁または 2 桁までの数字と、千または百万の尺度 (つまり、3,400,000 ではなく 3.4 M (日本語の場合は「千」、「万」など)) で測定単位を表示します。    
* 精度と時間のレベルを混在させないようにします。 期間がよくわかるようにします。  前月のある 1 つのグラフを、その年の特定の 1 つの月からフィルター処理されたグラフの横に配置しないでください。    
* また、折れ線グラフや横棒グラフなど、同じ尺度に大きい測定単位と小さい測定単位を混在させないようにします。  たとえば、1 つの測定単位が数百万単位で、もう一方の測定単位が数千単位のような指定の方法です。  このような大きい縮尺では、数千単位の測定値の違いがわかりにくくなります。  測定単位を混在させる必要がある場合は、複合グラフのような 2 つ目の軸の使用を可能にする視覚エフェクトを選びます。    
* グラフが不要なデータ ラベルで雑然とならないようにします。 通常、横棒グラフの値は、***グラフが十分に大きければ***、実際の数値を示さなくても十分にわかります。   
* [グラフの並べ替え](consumer/end-user-change-sort.md)方法にご注意ください。  最大数または最小数に注目させる必要がある場合は、測定単位に従って並べ替えます。  閲覧者が他の多くのカテゴリの中の特定のカテゴリをすばやく見つけられるようにするには、軸に従って並べ替えます。  
* 円グラフは、カテゴリが 7 つ以下の場合に最適です。 円グラフ内の各値の比較は、値を並べて比較できないため横棒グラフや縦棒グラフよりも難しくなります。 円グラフは、部分の比較ではなく、全体に対する部分の関係を示すために適しています。 ゲージ グラフは、ある目標に関して現在の状態を示すために適しています。    

視覚化について詳しくは、「[Power BI での視覚化の種類](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md)」をご覧ください。  

### <a name="learn-more-about-best-practice-dashboard-design"></a>ダッシュボード デザインのベスト プラクティスの詳しい情報
役立つ書籍としては、次のものがあります。

* 『*Storytelling with Data*』(データでのストーリーテリング)、Cole Nussbaumer Knafic 著
* 『*Data points*』(データ ポイント)、Nathan Yau 著
* 『*The truthful Art*』(真実を語るアート)、Alberto Cairo 著
* *Now You See It* Stephen Few 著  
* *Envisioning Information* Edward Tufte 著  
* 『*Advanced Presentations by Design*』(高度なプレゼンテーションのデザイン)、Design Andrew Abela 著   

## <a name="next-steps"></a>次の手順
[Power BI サービスのデザイナー向けの基本的な概念](service-basic-concepts.md)

[Power BI のレポート](consumer/end-user-reports.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。
