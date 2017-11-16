---
title: "Power BI Q&A を使用する方法"
description: "Power BI Q&A を使用する方法"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
tags: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: a6736916a4bb2e94c1f5e1e3c3c3e5339cf990ec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-use-power-bi-qa"></a>Power BI Q&A を使用する方法
## <a name="ask-questions-of-your-data-using-natural-language"></a>自然言語を使用してデータに関する質問をする
ダッシュボードで開始します。 Q&A 質問ボックスでは、自然言語を使用して質問を入力します。 Q&A は、入力した用語を認識して、回答を探す場所 (データセット) を見つけ出します。 さらに、オートコンプリート、書き換え、その他のテキストや視覚による支援を使用して質問の作成を助けます。

![](media/service-how-to-q-and-a/powerbi-qna.png)

質問を変更すると、質問に対する回答は、対話型の視覚化と更新として表示されます。

Q&A は対話型で楽しく、視覚化によってさらに調べるべき点が見つかるため、たいていは 1 つの質問が多数の他の質問につながります。 Q&A を使用してビジュアルを作成し、それを詳しく調べて、ダッシュボードに表示する、Amanda のデモンストレーションをご覧ください。

> [!NOTE]
> [iPad、iPhone、iPod Touch デバイスの iOS 用の Microsoft Power BI アプリ](mobile-apps-ios-qna.md)で Q&A も利用できます。
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="use-natural-language-to-ask-questions-about-your-data"></a>自然言語を使用してデータに関する質問をする
1. 質問ボックスにカーソルを置きます。 入力を開始する前に、Q & A で質問を作るときに役立つ情報が新しい画面に表示されます。
   
   ![](media/service-how-to-q-and-a/powerbi-qna-cursor.png)  
   
   次のような情報が表示されます。  
   a.  既にダッシュボードにピン留めされている[タイル](service-dashboard-tiles.md)を作成するために使った質問。  
   b.  [基礎になるデータセット](service-get-data.md)に含まれているテーブルの名前。  
   
   開始点として常にこれらの質問のいずれかを選び、質問を洗練し続けて、探している具体的な回答を見つけることができます。 あるいは、テーブル名を使用して、新しい質問を言葉で表すことができます。
2. ドロップダウンから選ぶか、独自の質問の入力を開始します。  
   
   ![](media/service-how-to-q-and-a/powerbi-qna-list.png)
3. 質問を入力するにつれて、Power BI Q&A は回答を表示するための最適な[視覚化](power-bi-visualization-types-for-reports-and-q-and-a.md)を選びます。質問を修正するたびに、視覚エフェクトは動的に変更されます。 また、Q&A は、オートコンプリートによる質問の書き換えと、その他のテキストや視覚による支援により、質問の作成を助けます。  
   ![](media/service-how-to-q-and-a/powerbi-qna-viz.png)
4. クエリを入力すると、Power BI はダッシュボードにタイルが置かれたデータセットで回答を検索します。  すべてのタイルが *datasetA*のものである場合、回答は *datasetA*から取得されます。  タイルが *datasetA* と *datasetB* のものである場合、Q&A はそれら 2 つのデータセットで最適な回答を検索します。
   
   > [!TIP]
   > そのため *datasetA* からのタイルが 1 つしかない場合は、それをダッシュボードから削除すると、Q&A が *datasetA* にアクセスできなくなるのでご注意ください。
   > 
   > 
5. 結果に満足したら、右上隅にあるピンのアイコンを選んで、[ダッシュボードに視覚エフェクトをピン留め](service-dashboard-pin-tile-from-q-and-a.md)します。 他のユーザーから共有を受けているダッシュボード、またはアプリの一部であるダッシュボードの場合は、ピン留めできません。
   
   ![](media/service-how-to-q-and-a/pbi_qna_finish-typing-question.jpg)

### <a name="tell-qa-which-visualization-to-use"></a>使用する視覚化を Q&A で指定する
Q&A では、データ自身に語らせるだけでなく、データの表示方法も指定できます。 質問の最後に "as a <visualization type>" を追加して、視覚化の種類を指定するだけです。  たとえば、「show inventory volume by plant as a map」(工場ごとの在庫量をマップとして表示する)、「show total inventory as a card」(在庫合計をカードとして表示する) などです。  自分で試してみてください。

## <a name="how-does-qa-know-how-to-answer-questions"></a>Q&A は、回答する方法をどのように知るのでしょうか。
### <a name="which-datasets-does-qa-use"></a>Q&A はどのデータセットを使用しますか。
Q&A は、データに固有の質問に回答する方法をどのように知るのでしょうか。 これは、基になるデータセット内のテーブル、列、計算フィールドの名前に依存します。 そのため自分 (またはデータセットの所有者) が物事を何と呼ぶかが重要です。 

たとえば、「売上」という名前の Excel のテーブルがあり、「製品」、「月」、「販売単位」、「総売上高」、「利益」というタイトルの列があるとします。 これらのエンティティのいずれかに関する質問ができます。  "*売上*を表示する"、"*月別*の*利益*合計"、"*販売単位*を基準とした*製品*の並べ替え" などの質問を入力できます。

Q&A は、データセットがどのようにまとめられているかに基づいて質問に回答します。 Salesforce のデータではどのように機能するでしょうか。 salesforce.com のアカウントに接続すると、Power BI は自動的にダッシュボードを生成します。  Q&A で質問を開始する前に、ダッシュボードの視覚化に表示されたデータと、Q&A のドロップダウンに表示されたデータをご覧ください。

* 視覚エフェクトの軸のラベルと値に "売上"、"アカウント"、"月"、"営業案件" が含まれている場合は、"どの*アカウント*の*営業案件*が一番多いか"、または "月別の*売上*を棒グラフとして表示する" などの質問を自信を持って行えます。
* ドロップダウンに「販売員」、「状態」、「年」が含まれている場合は、「 *2013* 年に *フロリダ* で最も *売上* が低かった *販売員*はだれか」といった質問を自信を持って行えます。

Google Analytics に Web サイトのパフォーマンス データがある場合は、Web ページの利用に費やした時間、固有のページのアクセス数、ユーザーの契約率に関する Q&A を行えます。 あるいは、人口統計データのクエリを実行している場合は、年齢および場所ごとの世帯収入に関する質問をする場合があります。

### <a name="which-visualization-does-qa-use"></a>Q&A はどの視覚化を使用しますか。
Q&A は、表示されているデータに基づいて最適な視覚化を選びます。 基になるデータセットにあるデータは、特定の種類またはカテゴリとして定義されることがあります。Q&A はこれを利用して表示方法が分かります。 たとえば、データが日付型として定義されている場合は、折れ線グラフで表示される可能性が高くなります。 市区町村として分類されているデータは、マップとして表示される可能性が高くなります。

また、Q&A に独自の質問を追加して、使用する視覚化を Q&A で指定することもできます。 しかし、Q&A が常に要求した種類の視覚化でデータを表示できるとは限らないことにご注意ください。

Q & A が認識できるキーワードについては、「[Power BI Q&A で質問するためのヒント](service-q-and-a-tips.md)」を参照してください。

## <a name="next-steps"></a>次の手順
「[Power BI での Q&A](service-q-and-a.md)」に戻る  
[チュートリアル: 小売りの分析のサンプルで Q&A を使う](power-bi-visualization-introduction-to-q-and-a.md)  
[Q&A で質問するためのヒント](service-q-and-a-tips.md)  
[Q&A のためのブックの準備](service-prepare-data-for-q-and-a.md)  
[Q&A からダッシュボードにタイルをピン留めする](service-dashboard-pin-tile-from-q-and-a.md)  

