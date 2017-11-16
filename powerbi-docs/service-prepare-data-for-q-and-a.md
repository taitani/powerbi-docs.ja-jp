---
title: "データを Power BI Q&A に適合させる方法"
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 499c3beca9046af9336de6dfec96994004050986
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="make-your-data-work-well-with-qa-in-power-bi"></a>データを Power BI Q&A に適合させる方法
データ モデルを作成する担当者、または Power BI とともに使用する Excel ブックを作成する担当者は、以下をお読みください。

Power BI の Q&A では、構造化データを検索でき、質問に適した視覚化を選択できることから、実に優れたツールだといえます。   

Q&A は、テーブル、範囲、PowerPivot モデルを含むアップロードされた Excel ファイルで使用できますが、最適化とデータのクリーニングを実行すればするほど、Q&A のパフォーマンスがより安定します。 

## <a name="how-qa-works"></a>Q&A のしくみ
Q&A には、データ間で機能する主要な自然言語認識機能のセットが組み込まれています。 Excel テーブル、列、および計算フィールド名のコンテキスト依存キーワード検索機能を備えています。 さらに、フィルター、並べ替え、集計、グループ、およびデータの表示方法についての組み込み知識を備えています。 

たとえば、「Sales」(売上) という名前の Excel テーブルに、「Product」(製品)、「Month」 (月)、「Units Sold」(販売単位)、「Gross Sales」 (総売り上げ)、および「Profit」(利益) という列があるとします。これらのエンティティについて尋ねる質問を入力します。  売上、月別利益合計、販売単位を基準とした製品の並べ替えなど、さまざまな質問を入力できます。 [尋ねる質問の種類](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx)、[質問テンプレートを使用した質問](service-q-and-a.md)、および [Q&A で指定できる視覚化の種類](power-bi-visualization-types-for-reports-and-q-and-a.md)を参照してください。

## <a name="prepare-a-workbook-for-qa"></a>Q&A のためのブックの準備
Q&A はテーブル、列、および計算フィールドの名前に依存して、データに固有の質問の回答を導き出します。つまり、ブック内のエンティティと呼ばれる要素が重要なのです。

ブックで Q&A を最大限活用するためのヒントをいくつか紹介します。

* データが Excel テーブル内にあることを確認してください。 ここでは、[Excel テーブルを作成する方法](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US)について説明します。
* テーブル、列、および計算フィールドの名前が英語として意味を成すことを確認します。
  
  たとえば、売上データを含むテーブルがある場合は、そのテーブルに「Sales」(売上) という名前を付けます。 「Year」(年)、「Product」(製品)、「Sales Rep」(営業担当者)、「Amount」(量) などの列名も、Q&A でうまく機能する名前です。

> [!NOTE]
> ブックに Power Pivot データ モデルが含まれている場合は、さらに強力な最適化を実行できます。 社内の自然言語専門家チームが提供する「[Demystifying Power BI Q&A part 2 (Power BI Q&A の詳しい解説、パート2)](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx)」を参照してください。
> 
> 

## <a name="next-steps"></a>次の手順
[Power BI での Q&A](service-q-and-a.md)  
[チュートリアル: Power BI Q&A の概要](power-bi-visualization-introduction-to-q-and-a.md)  
[Power BI のデータの取得](service-get-data.md)  
[Power BI - 基本的な概念](service-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

