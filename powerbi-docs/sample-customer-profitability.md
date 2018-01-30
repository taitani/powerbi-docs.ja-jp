---
title: "Power BI のお客様の収益性のサンプル: 使ってみる"
description: "Power BI のお客様の収益性のサンプル: 使ってみる"
services: powerbi
documentationcenter: 
author: amandacofsky
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
ms.date: 01/22/2018
ms.author: mihart
ms.openlocfilehash: 82e909962a0ed1db50f2ba3729988fd7aacadc80
ms.sourcegitcommit: 1a5446c3136dc0787f2a1d5b8cad1113704301ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2018
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Power BI のお客様の収益性のサンプル: 使ってみる
「お客様の収益性のサンプル」のコンテンツ パックには、マーケティング資料を製作する会社向けのダッシュボード、レポート、データセットが含まれています。 このダッシュボードは、5 つの事業部のマネージャー (経営陣とも言う)、製品、顧客、粗利益 (GM) に関する主要なメトリックを確認するために、CFO によって作成されました。 どの要因が収益性に影響を与えているかが一目で確認できます。

このサンプルは、ビジネス用のデータ、レポート、ダッシュボードを用いて Power BI を使う方法について説明するシリーズの一部です。 これは、obviEnce ([www.obvience.com](http://www.obvience.com/)) が収集している匿名化された実データです。

## <a name="prerequisites"></a>前提条件

このサンプルを使用するには、事前にサンプルをコンテンツ パック、.pbix ファイル、または Excel ブックとしてダウンロードしておく必要があります。

### <a name="get-the-content-pack-for-this-sample"></a>このサンプルのコンテンツ パックを入手する

1. Power BI サービス (app.powerbi.com) を開いてログインします。
2. 左下隅にある **[データの取得]** を選びます。
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. 表示される [データの取得] ページで、**[サンプル]** アイコンを選びます。
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. **[お客様の収益性のサンプル]** を選び、**[接続]** を選びます。  
   
   ![データを取得](media/sample-customer-profitability/get-supplier-sample.png)
5. Power BI がコンテンツ パックをインポートし、新しいダッシュボード、レポート、データセットを現在のワークスペースに追加します。 新しいコンテンツは黄色のアスタリスクで示されます。 サンプルを使って Power BI を試してみます。  
   
   ![アスタリスク](media/sample-customer-profitability/supplier-sample-asterisk.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>このサンプルの .pbix ファイルを取得する

あるいは、Power BI Desktop で使用するために設計された .pbix ファイルとして、サンプルをダウンロードすることもできます。 

- [お客様の収益性のサンプル](http://download.microsoft.com/download/6/A/9/6A93FD6E-CBA5-40BD-B42E-4DCAE8CDD059/Customer Profitability Sample PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>このサンプルの Excel ブックを取得する

[このサンプルのデータセット (Excel ブック) だけをダウンロード](http://go.microsoft.com/fwlink/?LinkId=529781)することもできます。 ブックには、表示および変更可能な Power View シートが含まれています。 生データを表示するには、**[Power Pivot] > [管理]** を選択します。

## <a name="what-is-our-dashboard-telling-us"></a>ダッシュボードからわかること

お客様の収益性のサンプルのダッシュボードは、**[マイ ワークスペース]** の下にあります。

![お客様の収益性のサンプルのダッシュボード](media/sample-customer-profitability/power-bi-dash.png)

### <a name="company-wide-dashboard-tiles"></a>会社全体のダッシュボードのタイル
これらのタイルは、CFO にとって重要な会社メトリックの概要を提供します。  何か興味深いものがある場合は、タイルを選んで詳しいデータを確認できます。

1. 粗利益は 42.5% です。
2. 80 の顧客が存在します。
3. 5 つの異なる製品を販売しています。
4. 予算に対する収益差異 % が最低だったのは 2 月で、その後の 3 月は最高でした。
5. 収益のほとんどは東部および北部の地域からです。 粗利益が予算を超えたことはなく、ER-0 と MA-0 はさらに調査を必要とします。
6. 年間の総収益はほぼ予算どおりです。

### <a name="manager-specific-dashboard-tiles"></a>マネージャー固有のダッシュボード タイル
これらのタイルはチームのスコアカードを提供します。 CFO はマネージャーについて把握しておく必要があり、これらのタイルは GM% を使用して利益の概要を説明します。 いずれかのマネージャーに関して予期しない GM% の傾向が見られる場合は、さらに調査できます。

Annelie の GM% は最低ですが、3 月以降、安定的に増加しているのがわかります。 その一方で、Valery は GM% が大幅に低下しています。 また、Andrew は不安定な 1 年でした。 マネージャー固有のタイルのいずれかをクリックして、基になっているレポートを開きます。 レポートに含まれる 3 ページのうち、"業界の利益分析" というページが表示されます。

## <a name="explore-the-pages-in-the-report"></a>レポート内のページの調査
レポートに含まれる 3 ページ:

* "チーム スコアカード" では、5 人のマネージャーの業績とその "顧客管理手法" に焦点を合わせます。
* "業界の利益分析" では、業界全体の状況と比較して収益性を分析する方法が提供されます。
* "役員スコアカード" では、Cortana での表示用に書式設定されたマネージャーのそれぞれのビューが提供されます。

### <a name="team-scorecard-page"></a>「チーム スコアカード」ページ
![](media/sample-customer-profitability/customer2.png)

2 人のチーム メンバーを詳しく考察し、どのような洞察が得られるかを確認してみましょう。 左側のスライサーで Andrew の名前を選んで、Andrew のデータのみが表示されるようにレポート ページをフィルター処理します。

* クイック KPI の場合、Andrew の**収益状態**を見ます。- Andrew は緑色です。 Andrew の業績は良好です。
* 「月別の予算に対する収益差異 %」面グラフには、2 月の落ち込みを除き、Andrew は全体として良好な結果を出していることが示されています。 Andrew の主要な地域は東部で、49 社の顧客と (7 つのうち) 5 つの製品を扱っています。 Andrew の GM% は最高でも最低でもありません。
* 「月別の RevenueTY と予算に対する収益差異 %」には、安定した一様の収益履歴が示されています。ところが、地域ツリーマップ内の **[Central]** (中部) の四角形をクリックしてフィルター処理すると、Andrew は 3 月にインディアナ州でのみ売上があることがわかります。 これは計画的なものでしょうか、それとも検討する必要があるでしょうか。

次は Valery です。 スライサーで Valery の名前を選んで、Valery のデータのみを表示するようにレポート ページをフィルター処理します。  
![](media/sample-customer-profitability/customer3.png)

* **[RevenueTY Status]**(RevenueTY の状態) の赤の KPI にご注意ください。 これは明らかにさらなる調査が必要です。
* Valery の収益差異は懸念点を示しています。Valery は収益マージンを満たしていません。
* Valery の顧客はわずか 9 社で、2 製品のみを扱い、取引先はほぼ北部の顧客のみに限られています。 この特殊性は、Valery の変動幅が大きいことの説明になる可能性があります。
* ツリーマップ内の **[North]** (北部) の四角形を選ぶと、北部での Valery の粗利益が彼女の全体的な利益と一貫性があることがわかります。
* 他の **[Region]** (地域) の四角形を選ぶと興味深いことがわかります。Valery の GM% の範囲は 23% から 79% で、北部を除く全地域での収益値は大きく季節に依存します。

なぜ Valery の領域で業績が良くないかを知るためにデータの詳しい考察を続けます。 複数の地域、他の事業部、レポートの次のページ「業界の利益分析」をご覧ください。

### <a name="industry-margin-analysis"></a>業界の利益分析
このレポート ページでは、データの別のスライスを提供します。 これは、セグメントごとに分割した、業界全体の粗利益を考察します。 CFO はこのページを利用して、会社と事業部のメトリックを業界のメトリックと比較し、傾向と収益性の説明に役立てます。 「月と役員名別の粗利益」面グラフはチーム固有であるにもかかわらず、なぜこのページ上にあるのか不思議に思われるかもしれません。 ここに表示することで、事業部のマネージャー別にページをフィルター処理することができます。  
![](media/sample-customer-profitability/customer6.png)

業界によって収益性はどのように異なるでしょうか。 製品と顧客は業界別にどのように分類されるでしょうか。 左上から、1 つまたは複数の業界を選びます。 (CPG 業界から開始) フィルターを消去するには、消しゴムのアイコンを選びます。

バブル チャートで、CFO は最大のバブルを検索します。これらが収益に最も大きく影響するものだからです。 面グラフ内のマネージャー名をクリックし、マネージャーごとにページをフィルター処理すると、業界セグメント別の各マネージャーの影響を確認しやすくなります。

* Andrew が影響を与える領域は多数のさまざまな業界セグメントにまたがり、GM% (ほとんどの正の側) と Var% は大きく異なります。 
* Annelie のグラフは似ていますが、少数の業界セグメントにのみ集中し、連邦政府セグメントと Gladius 製品に焦点を合わせています。 
* Carlos は明らかにサービスのセグメントに重点を置き、良好な収益を得ています。 Carlos はハイテク セグメントで差異 % を大幅に向上させ、彼にとっての新しいセグメントである製造業では、業界では、予算に対して特に優れた業績を上げています。 
* Tina がいくつかのセグメントを担当し、最高の GM% を実現していますが、バブルのほとんどが小さいことは、企業の最終的な収益への影響が最小限であることを示しています。 
* Valery が扱っている製品は 1 つのみで、担当の業界セグメントはわずかに 5 つです。 Valery の業界への影響は季節的ですが常に大きなバブルを生み出すことは、会社の最終的な収益に大きな影響を与えていることを示します。 業界は彼女の業績が悪いことの説明になりますか。

### <a name="executive-scorecard"></a>役員スコアカード
このページは Cortana の回答カードとして書式が設定されています。 詳細については、[Cortana の回答カードの作成方法のページ](service-cortana-answer-cards.md)を参照してください。

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Q&A で質問をすることによるデータの詳しい考察
どの業界が Valery の最大の収益を生み出すかを判別することは分析に役立つ場合があります。 Q&A を利用してみましょう

1. 上部のナビゲーション バーで **[Power BI]** を選択して、ダッシュボードに戻ります。
2. ダッシュボードの上部にある Q&A 質問ボックスを選択します。
   
    ![](media/sample-customer-profitability/customer4.png)
3. **「total revenue by industry for Valery (Valery の業界別合計売上)」**と入力します。 質問を入力するに従って視覚化が更新されることにご注意ください。
   
    ![](media/sample-customer-profitability/customer5.png)
   
   流通は Valery にとって最大の売上領域です。

### <a name="dig-deeper-by-adding-filters"></a>フィルターの追加による詳しい調査
*流通* 業界を見てみましょう。  

1. ダッシュボードに戻り、Andrew の粗利益の傾向を示す面グラフを選びます。 「業界の利益分析」ページのレポートが表示されます。
2. レポート ページで可視化が選択されていない状態で、右側のフィルター ウィンドウを展開します。 フィルター ウィンドウには、ページ レベル フィルターのみが表示されます。  
   
   ![](media/sample-customer-profitability/power-bi-filters.png)
3. **[Industry]** フィルターを選択し、矢印を選択して一覧を展開します。 流通業界のページ フィルターを追加してみましょう。 まず **[Select All]** チェックボックスをオフにして、すべての選択を解除します。 次に **[Distribution]** を選択します。  
   
   ![](media/sample-customer-profitability/customer7.png)
4. 「月および役員名別の粗利益」面グラフから、この業種の顧客を担当しているのは Valery と Tina だけで、Valery がこの業種を担当していたのは 6 月から 11 月までの間だけであることがわかります。   
5. 「月および役員名別の粗利益」面グラフの凡例で、**[Tina]**、**[Valery]** の順に選びます。 「製品別の合計売上」の Tina の部分は、Valery と比較して非常に小さい点にご注意ください。 
6. 実売上を確認するには、ダッシュボードに戻り、Q&A を使用して、**役員のシナリオ別の流通業の合計売上**を尋ねます。  
   
   ![](media/sample-customer-profitability/customer8.png)

同様に他の業界を調査して、視覚化に顧客を追加し、Valery の業績の原因を理解することもできます。

これは、試してみるのに安全な環境です。 変更内容を保存しないようにいつでも選択できます。 一方、保存すると、常にこのサンプルの新しいコピーに対する **データの取り込み** に進むことができます。

[このサンプルのデータセット (Excel ブック) だけをダウンロード](http://go.microsoft.com/fwlink/?LinkId=529781)することもできます。

## <a name="next-steps-connect-to-your-data"></a>次の手順: データへの接続
この記事から、Power BI ダッシュボード、Q&A、レポートから顧客データへの洞察をどのように得られるかがご理解いただけたでしょうか。 次はあなたの番です。ご自分のデータを接続してみてください。 Power BI を使用すると、広範なデータ ソースに接続することができます。 詳細については、「[Power BI の概要](service-get-started.md)」をご覧ください。

[Power BI のサンプルに戻る](sample-datasets.md)  

