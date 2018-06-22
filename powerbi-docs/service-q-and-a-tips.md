---
title: Power BI の Q&A で質問するヒントとテクニック
description: Power BI の Q&A で質問するヒントとテクニック
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/18/2018
ms.author: jastru
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 0165eb7161e9ba931c336300f73316d215b1c88d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34247072"
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Power BI Q&A で質問するためのヒント
## <a name="words-and-terminology-that-qa-recognizes"></a>Q&A で認識される語句と用語
このキーワード一覧に含まれていないキーワードもあります。  Power BI でキーワードが認識されるかどうかを確認する最良の方法は、質問ボックスに入力して試してみることです。  語句または用語がグレー表示される場合は、Power BI で認識されません。または、現在のコンテキストでは認識されません。

以下のリストでは現在形を使用していますが、ほとんどの場合はすべての時制が認識されます。 たとえば、"is" には are、was、were、will be、have、has、had、will have、has got、do、does、did が含まれます。  "sort" には sorted および sorting が含まれます。  また、PowerBI では単語の単数形と複数形の両方が認識されます。 たとえば、"year" と "years" が認識されます。

> [!NOTE]
> [iPad、iPhone、iPod Touch デバイスの iOS 用の Microsoft Power BI アプリ](mobile-apps-ios-qna.md)で Q&A も利用できます。
> 
> 

データセットの所有者は、お客様の Q&A の結果を向上させるために言い回しや同意語を追加してください。

**集計**: total、sum、amount、number、quantity、count、average、most、least、fewest、largest、smallest、highest、biggest、maximum、max、greatest、lowest、littlest、minimum、min

**冠詞**: a、an、the

**空白とブール値**: blank、empty、null、"non" または "non-" のプレフィックス付きの語句、empty string、empty text、true、t、false、f

**比較**: vs、versus、compared to、compared with

**接続詞**: and、or、each of、with、versus、&、and、but、nor、along with、in addition to

**短縮系**: Q&A ではほぼあらゆる短縮形が認識されます。試してみてください。例: didn’t、haven’t、he’d、he’s、isn’t、it’s、she’ll、they’d、weren’t、where’ll、who’s、won’t、wouldn’t

**日付**: Power BI では、ほとんどの日付の用語 (day、week、month、year、quarter、decade など) と、さまざまな形式 (下記参照) で記述された日付が認識されます。 また、MonthName、Days 1-31、decade のキーワードも認識されます。

例: January 3rd of 1995、January 3rd 1995、jan 03 1995、3 Jan 1995、the 3rd of January、January 1995、1995 January、1995-01、01/1995、月の名前

**相対日付**: today、right now、current time、yesterday、tomorrow、the current、next、the coming、last、previous、ago、before now、sooner than、after、later than、from、at、on、from now、after now、in the future、past、last、previous、within、in、over、N days ago、N days from now、next、once、twice

例: count of orders in the past 6 days (過去 6 日間の注文数)

**等しさ (範囲)**: in、equal to、=、after、is more than、in、between、before

例: Order year is before 2012? (注文した年が 2012 年より前であるか?)  Price equals between 10 and 20? (価格が 10 と 20 の間に等しいか?)  Is the age of John greater than 40? (John の年齢は 40 より上か?)  Total sales in 200-300? (売上合計が 200-300 の範囲か?)

**等しさ (値)**:  is、equal、equal to、in、of、for、within、is in、is on

例: Which products are green? (どの商品が緑か?)  Order date equals 2012. (注文日が 2012 に等しい) Is the age of John 40? (John の年齢は 40 か?)  Total sales that is not equal to 200? (200 に等しくない売上合計は?) Order date of 1/1/2016. (注文日が 1/1/2016)  10 in price? (価格が 10?) Green for color? (色は緑?) 10 in price? (価格が 10?)

**名前**: データセット内の列に "name" (名) という語が含まれている場合 (EmployeeName (社員名) など)、Q&A ではその列の値が名前であると理解されるため、"which employees are named robert" (robert という名前の社員はどれか) のような質問をすることができます。

**代名詞**: he、him、himself、his、she、herself、her、hers、it、itself、its、they、their、them、themselves、theirs、this、these、that、those

**クエリ コマンド**: sorted、sort by、direction、group、group by、by、show、list、display、give me、name、just、only、arrange、rank、compare、to、with、against、alphabetically、ascending、descending、order

**範囲**: greater、more、larger、above、over、>、less、smaller、fewer、below、under、<、at least、no less than、>=、at most、no more than、<=、in、between、in the range of、from、later、earlier、sooner、after、on、at、later than、after、since、starting with、starting from、ending with

**時刻**: am、pm、o'clock、noon、midnight、hour、minute、second、hh:mm:ss

例: 10 pm、10:35 pm、10:35:15 pm、10 oclock、noon、midnight、hour、minute、second

**上位 N** (順序、順位付け): top、bottom、highest、lowest、first、last、next、earliest、newest、oldest、latest、most recent、next

**ビジュアルの種類**: すべてのビジュアルの種類は Power BI に固有です。  [視覚化] ウィンドウのオプションである場合は質問に含めることができます。  この例外は、[視覚化] ウィンドウに手動で追加した[カスタム ビジュアル](power-bi-custom-visuals.md)です。

例: show districts by month and sales total as bar chart (地区を月別および売上合計別に棒グラフとして示す)

**Wh (関係、限定)**: when、where、which、who、whom、how many、how much、how many times、how often、how frequently、amount、number、quantity、how long、what

## <a name="qa-helps-you-phrase-the-question"></a>Q&A は質問の言い回しの作成を手助けする
Q&A は、質問の内容を正確に反映した回答を返すために、できる限りのことを行います。 これは、いくつかの方法で実行されます。 どのアクションについても、全部を採用するか、一部を採用するかは自由です。まったく採用しなくても構いません。 質問を入力する過程で、Q&A は次のようなアクションをとります。

* 語句や質問をオートコンプリートします。 認識可能な単語のオートコンプリート機能、基になるブックでよくたずねられる質問、以前に適切な回答が返された質問など、さまざまな方法を使用します。 複数のオートコンプリート オプションが使用可能な場合は、ドロップダウン リストとして表示されます。
* スペル チェックによる修正を加えます。
* 回答のプレビューを視覚化して提供します。 質問を入力および編集するにつれて、視覚化が更新されます (Enter キーが押されるまで待機しません)。
* カーソルを質問ボックスに戻すと、基になるデータセットから用語の置換が自動的に提案されます。
* 基になるデータセット内のデータに基づいて質問を言い換えます。 このとき、Q&A はユーザーが使用した語を基になるデータセットからの同意語に置き換えるため、Q&A が質問を適切に理解する助けになります。
* 理解できない語は灰色表示になります。

## <a name="dont-stop-now"></a>これで終わりではありません
Q&A の結果が表示された後も、対話を続けてください。 視覚化と Q&A の対話型の機能を使用して、さらに洞察を得られます。

## <a name="next-steps"></a>次の手順
「[Power BI での Q&A](power-bi-q-and-a.md)」に戻る  

[Power BI - 基本的な概念](service-basic-concepts.md)  

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

