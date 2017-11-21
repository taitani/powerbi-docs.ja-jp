---
title: "Power BI Desktop でメジャーを使用する"
description: "Power BI Desktop のメジャー"
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: 205f31e74b339b9aa0c84183d5e10765d63c82a8
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="measures-in-power-bi-desktop"></a>Power BI Desktop のメジャー
**Power BI Desktop** では、わずか数クリックで、データに対する洞察を作成できます。 しかし、場合によっては、最も重要な質問に答えるために必要なものが、データに含まれていないことがあります。 メジャーは、それを入手するために役立ちます。

メジャーは、最も一般的なデータ分析に使用します。たとえば、合計、平均、最小値または最大値、カウント数を計算したり、DAX の数式を使用して自分で作成したより高度な計算を実行したりできます。 メジャーの計算結果は、ユーザーがレポートを操作するたびに変化するため、アドホック データ探索を高速で、また動的に実行できます。 詳しく見てみましょう。

## <a name="understanding-measures"></a>メジャーについて
**Power BI Desktop** では、**レポート ビュー**または**データ ビュー**でメジャーを作成し、使用します。 ユーザーが自分で作成したメジャーは、フィールド リストに、計算機のアイコン付きで表示されます。 メジャーには任意の名前を付け、他のフィールドと同じように、新規または既存の視覚エフェクトを追加することができます。

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> ダイアログ ボックスから選ぶことができる既製の**クイック メジャー**もあります。 メジャーをすばやく作成することができ、自動的に作成される DAX 式を確認できるため DAX 構文の勉強にも適しています。 詳しくは、[クイック メジャー](desktop-quick-measures.md)に関する記事をご覧ください。
> 
> 

## <a name="data-analysis-expressions"></a>Data Analysis Expressions (DAX)
メジャーは、数式の結果を計算します。 独自のメジャーを作成するときは、[Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) 数式言語を使用します。 DAX は 200 以上の関数、演算子、およびコンストラクトを含むライブラリを提供しているため、メジャーを作成する際の柔軟性が非常に高く、データ分析に必要なほとんどすべての計算結果を得ることができます。

DAX の数式は、Excel の数式とよく似ています。 DAX には、DATE、SUM、LEFT など、Excel と同じ関数が多く含まれています。 ただし、DAX の関数は、Power BI Desktop で取り扱っているようなリレーショナル データを操作することを意図しています。

## <a name="lets-look-at-an-example"></a>例を見てみましょう
Jan は、Contoso 社の営業マネージャーです。 彼女は、次の会計年度の販売店売上予測を提供するように依頼されました。 そこで、昨年度の売上高に基づき、今後 6 か月間に予定されている各種のプロモーションの成果として年率 6% の売上増加を見込んで予測を立てることにしました。

推定値を報告するため、Power BI Desktop に昨年度の売上データをインポートします。 "Reseller Sales" テーブルに、"SalesAmount" フィールドがあることを確認します。 インポートしたデータには昨年度の売上高だけが含まれているので、"SalesAmount" フィールドの名前を "Last Years Sales" に変更します。 "Last Years Sales" をレポート キャンバスにドラッグします。 昨年度のすべての販売店の売上合計を示す単一の値として、グラフによる視覚エフェクトが表示されます。

ここで、自分で指定しなくても、数式が 1 つ自動的に用意されたことに気付きます。 Power BI Desktop により、"Last Years Sales" に含まれるすべての値の合計を計算する独自のメジャーが作成されました。

しかし、次の会計年度の売上予測を計算するメジャーが必要です。このメジャーでは、事業に 6% の増加を見込んで、昨年度の売上に 1.06 を乗算して計算します。 この計算については、自分で独自のメジャーを作成します。 新しいメジャーを作成する機能を使用して、新しいメジャーを作成し、次のような DAX 式を入力します。

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

この後、新しい Projected Sales メジャーをグラフにドラッグします。

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

このように、とても迅速に、最小限の労力で、売上予測を計算するメジャーを作成できました。 このあとは、特定の販売店をフィルター処理したり、レポートに他のフィールドを追加したりして、予測データをさらに分析することができます。

## <a name="learn-more"></a>詳細情報
この記事では、メジャーについてごく簡単に説明しました。独自のメジャーを作成する方法の詳細については、他の記事を参照してください。 「[チュートリアル: Power BI Desktop で独自のメジャーを作成する](desktop-tutorial-create-measures.md)」を必ず参照して、サンプル ファイルをダウンロードし、さまざまなメジャーを作成する方法についてステップ バイ ステップの説明をお読みください。  

DAX についてもう少し詳しく知るには、「[Power BI Desktop における DAX の基本事項](desktop-quickstart-learn-dax-basics.md)」をご覧ください。 「[Data Analysis Expressions (DAX) リファレンス](https://msdn.microsoft.com/library/gg413422.aspx)」では、関数、構文、演算子、名前付け規則のそれぞれに関する詳しい記事を紹介しています。 Power Pivot in Excel および SQL Server Analysis Services で DAX が利用されるようになって数年が経ち、その他にも多くのリソースが利用可能になりました。 「[DAX リソース センター Wiki](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)」をぜひご確認ください。ここでは、BI コミュニティで影響力を持つメンバーが DAX の知識を公開しています。



