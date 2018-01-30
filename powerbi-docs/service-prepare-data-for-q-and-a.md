---
title: "Excel のデータを Power BI Q&A に適合させる方法"
description: "データを Power BI Q&A に適合させる方法"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 01/18/2018
ms.author: mihart
ms.openlocfilehash: 92d75bc3df3a3403f77fb350b4acfe1325e707d2
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-make-your-excel-data-work-well-with-qa-in-power-bi"></a>Excel のデータを Power BI Q&A に適合させる方法
データ モデルを作成する担当者、または Power BI とともに使用する Excel ブックを作成する担当者は、以下をお読みください。

Power BI の Q&A では、構造化データを検索でき、質問に適した視覚化を選択できることから、実に優れたツールだといえます。   

Q&A は、テーブル、範囲、PowerPivot モデルを含むアップロードされた Excel ファイルで使用できますが、最適化とデータのクリーニングを実行すればするほど、Q&A のパフォーマンスがより安定します。  データセットに基づいてレポートとダッシュボードを共有する場合は、同僚が簡単に質問して適切な回答を得られるようにする必要があります。

### <a name="how-qa-works-with-excel"></a>Excel での Q&A の動作方法
Q&A には、データ間で機能する主要な自然言語認識機能のセットが組み込まれています。 Excel テーブル、列、および計算フィールド名のコンテキスト依存キーワード検索機能を備えています。 また、フィルター、並べ替え、集計、グループ、およびデータの表示方法についての組み込み知識を備えています。 

たとえば、「Sales」(売上) という名前の Excel テーブルに、「Product」(製品)、「Month」 (月)、「Units Sold」(販売単位)、「Gross Sales」 (総売り上げ)、および「Profit」(利益) という列があるとします。これらのエンティティについて尋ねる質問を入力します。  売上、月別利益合計、販売単位を基準とした製品の並べ替えなど、さまざまな質問を入力できます。 詳しくは、[たずねる質問の種類](power-bi-q-and-a.md)および [Q&A で指定できる視覚エフェクトの種類](power-bi-visualization-types-for-reports-and-q-and-a.md)に関する情報をご覧ください。

### <a name="prepare-an-excel-dataset-for-qa"></a>Q&A のための Excel データセットの準備
Q&A はテーブル、列、および計算フィールドの名前に依存して、データに固有の質問の回答を導き出します。つまり、ブック内のエンティティと呼ばれる要素が重要なのです。

ブックで Q&A を最大限活用するためのヒントをいくつか紹介します。

* データが Excel テーブル内にあることを確認してください。 ここでは、[Excel テーブルを作成する方法](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US)について説明します。
* テーブル、列、および計算フィールドの名前が自然音声として意味を成すことを確認します。
  
  たとえば、売上データを含むテーブルがある場合は、そのテーブルに「Sales」(売上) という名前を付けます。 「Year」(年)、「Product」(製品)、「Sales Rep」(営業担当者)、「Amount」(量) などの列名も、Q&A でうまく機能する名前です。

* ブックに Power Pivot データ モデルが含まれている場合は、さらに強力な最適化を実行できます。 社内の自然言語専門家チームが提供する「[Demystifying Power BI Q&A part 2 (Power BI Q&A の詳しい解説、パート2)](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx)」を参照してください。

* Power BI Desktop でデータセットを開き、新しい列の作成、計算メジャーの作成、複数フィールドの連結による一意値の作成、種類 (日付、文字列、地理、画像、URL など) によるデータの分類などを行います。

## <a name="next-steps"></a>次の手順
「[Power BI での Q&A](power-bi-q-and-a.md)」に戻る  
[Q&A 用にオンプレミスのデータセットを準備する](service-q-and-a-direct-query.md)   
[Q&A のクイック スタート](power-bi-visualization-introduction-to-q-and-a.md)  
[Power BI のデータの取得](service-get-data.md)  

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

