---
title: "Power BI サービスのレポートの読み取りビューと編集ビュー"
description: "Power BI サービスのレポートの読み取りビューと編集ビューの違いの概要について説明します"
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
ms.date: 12/21/2017
ms.author: mihart
ms.openlocfilehash: 7c0c09bd04eac31bac00e4562853c99befe9715f
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="reading-view-and-editing-view-in-power-bi-service-reports"></a>Power BI サービスのレポートの読み取りビューと編集ビュー
Power BI サービスには、レポートを表示および操作するためのモードとして、読み取りビューと編集ビューの 2 つがあります (Power BI Desktop にはありません)。  

読み取りビューはすべてのユーザーが利用できますが、編集ビューはレポートの作成者と所有者のみが利用できます。 読み取りビューは、アプリからレポートを開く同僚や、他のユーザーからレポートの共有を受けているユーザーなど、レポートの*コンシューマー*向けに設計されています。 読み取りビューでは、すべてのコンシューマーに対して、同じフィルターが適用された、同じ視覚エフェクトを含む、同じレポートが表示されます。  コンシューマーはレポートを操作できますが、変更を保存することはできません。

>**注**: 行レベルのセキュリティとデータ アクセス許可のため、特定の状況では、レポートのコンシューマーによってデータの表示が異なる場合があります。 

編集ビューは、レポートの作成者、またはアプリ ワークスペースのメンバーまたは管理者であるレポートの共同所有者のみが使用できます。

## <a name="reading-view"></a>読み取りビュー

読み取りビューを使用すると、データを楽しく安全に再生し、データをよく理解することができます。 読み取りビューは[編集ビュー](service-interact-with-a-report-in-editing-view.md)ほどインタラクティブではありませんが、それでもデータを探索する多くのオプションがあります。 たとえば、読み取りビューでのみ開くことができる、[他のユーザーから共有された](service-share-dashboards.md)レポートを表示するときに便利です。

詳しくは、[Power BI レポートの読み取りビュー](service-interact-with-a-report-in-reading-view.md)に関する記事をご覧ください。

## <a name="editing-view"></a>編集ビュー
Power BI の編集ビューでは ([読み取りビュー](service-interact-with-a-report-in-reading-view.md)と比較すると)、データをより詳しく調査できます。フィールドを追加、削除したり、視覚化の種類を変更したり、視覚化を新規作成したり、レポートから視覚化やページを追加、削除したりすることによって、詳しい調査を行います。

詳しくは、[Power BI レポートの編集ビュー](service-interact-with-a-report-in-editing-view.md)に関する記事をご覧ください。

## <a name="navigating-between-editing-view-and-reading-view"></a>編集ビューと読み取りビューの間の移動
編集ビューでレポートを開くことができるのはレポートの作成者と所有者のみであることに注意してください。

1. 通常、既定ではレポートは読み取りビューで開かれます。 **[レポートの編集]** オプションが表示されていれば、読み取りビューで開いていることになります。 **[レポートの編集]** が淡色表示の場合は、レポートを編集ビューで開くアクセス許可がありません。

   ![](media/service-reading-view-and-editing-view/power-bi-edit-report-grey.png)

2. **[レポートの編集]** が淡色表示になっていない場合は、それを選ぶとレポートが編集ビューで開きます。 
   
   ![](media/service-reading-view-and-editing-view/power-bi-edit-report.png)
   
   レポートが編集ビューに切り替わり、読み取りビューで最後に使っていた[表示設定](power-bi-report-display-settings.md)がそのまま使われます。

2. 読み取りビューに戻るには、上部のナビゲーション バーにある **[読み取りビュー]** を選びます。
   
    ![](media/service-reading-view-and-editing-view/power-bi-reading-view.png)

読み取りビューにはレポートを編集するさまざまな手段があり、データを細かく切り分けて洞察を発見し、質問に対する回答を得ることができます。  次のトピック「[Power BI の読み取りビューでレポートと対話する](service-interact-with-a-report-in-editing-view.md)」では、これらについて詳しく説明されています。

### <a name="next-steps"></a>次の手順
[Power BI の読み取りビューでレポートと対話する](service-interact-with-a-report-in-editing-view.md)    
「[Power BI のレポート](service-reports.md)」に戻る    
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。 

