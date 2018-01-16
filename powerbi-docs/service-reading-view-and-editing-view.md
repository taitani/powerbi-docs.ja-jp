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
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: e9fda17bd9560ac564cb6b3ae6c34b986a6bc2aa
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2018
---
# <a name="reading-view-and-editing-view-in-power-bi-service-reports"></a>Power BI サービスのレポートの読み取りビューと編集ビュー
Power BI サービスには、レポートを表示および操作するためのモードとして、読み取りビューと編集ビューの 2 つがあります (Power BI Desktop にはありません)。 読み取りビューはすべてのユーザーが利用でき、特にデータの*コンシューマー*向けに設計されていますが、編集ビューはレポートの*作成者*と所有者のみが利用できます。 

![](media/service-reading-view-and-editing-view/power-bi-creators-consumers.png)

## <a name="report-reading-view"></a>レポートの読み取りビュー

 読み取りビューではレポートを探索し、レポートと対話することができます。楽しく安全に、データについてさまざまなことを試したりよく理解したりすることができます。 読み取りビューは、アプリからレポートを開くユーザーや、レポートを[他のユーザーと共有](service-share-dashboards.md)しているユーザーなど、レポートの*コンシューマー*向けに設計されています。 読み取りビューでは、すべてのコンシューマーに対して、同じフィルターが適用された、同じ視覚エフェクトを含む、同じレポートが表示されます。  コンシューマーはレポートを操作できますが、変更を保存することはできません。

>**注**: 行レベルのセキュリティとデータ アクセス許可のため、特定の状況では、レポートのコンシューマーによってデータの表示が異なる場合があります。 

## <a name="report-editing-view"></a>レポートの編集ビュー

編集ビューは、レポートの作成者、または[アプリ ワークスペースのメンバーまたは管理者であるレポートの共同所有](service-create-distribute-apps.md)者のみが使用できます。

編集ビューはレポートの*作成者*向けに設計されています。 ここでは、作成者がデータセットのインポートや接続、データの探索、レポートとダッシュボードのビルドを行います。 編集ビューでは、*作成者*はデータをより詳しく調査できます。その場合、フィールドを追加/削除したり、視覚エフェクトの種類を変更したり、視覚エフェクトを新規作成したり、レポートから視覚エフェクトやページを追加/削除したりします。 その後、作成したレポートを同僚と共有することができます。

## <a name="reading-view-versus-editing-view"></a>読み取りビューと編集ビュー
このグラフには、Power BI サービスのすべてのレポート機能がリストされているわけではありません。 読み取りビューと編集ビューの**両方**では使用できないレポート タスクのみがリストされています。 


|タスク  | 読み取りビュー  | 編集ビュー |
|-------------------------|-------|-------|
|**レポート (全体として)**  |
||||
| [レポートの作成または編集](service-report-create-new.md) | いいえ  | はい |
| [レポートの共有](service-share-reports.md)| はい | はい。他のユーザーへの*所有者*アクセス許可の付与など、アクセス許可を管理することもできます。 |
| [フィルター ウィンドウからの永続的な (固定) ビジュアル レベル、ドリルスルー、ページ レベル、レポート レベルのフィルターの作成](power-bi-report-add-filter.md) | いいえ  | はい |
| [レポートのフィルター ウィンドウの使用](power-bi-how-to-report-filter.md) | はい、既存のフィルターを使用できます。ただし、変更はレポートには保存されません。 | はい |
| [レポートの分析ウィンドウの使用](service-analytics-pane.md) | いいえ | はい |
| [レポートの**表示**オプション](power-bi-report-display-settings.md) | はい。ただし、例外がいくつかあります。 | はい、グリッド線、スナップ、ロックを含むすべてを使用できます。 |
| [更新スケジュールの作成](refresh-data.md) | いいえ  | はい |
| [レポートへのサブスクライブ](service-report-subscribe.md) | はい | いいえ |
| [Q&A - レポートでの質問](service-q-and-a.md) | いいえ  | はい |
| [利用状況指標の表示](service-usage-metrics.md) | はい、レポート キャンバスで表示できます。 | はい、レポート リスト (コンテンツ ビュー) に表示できます。 |
| [関連の表示](service-related-content.md) | はい、レポート キャンバスで表示できます。 | はい、レポート リスト (コンテンツ ビュー) に表示できます。 |
| [レポートの保存](service-report-save.md) | はい。ただし、**[名前を付けて保存]** を使用する場合に限ります。 | はい |
| [レポートの削除](service-delete.md) | いいえ  | はい |
|**レポート ページ** |
||||
| [レポート ページの追加または名前変更](power-bi-report-add-page.md)  | いいえ  | はい  |
| [レポート ページの複製](power-bi-report-copy-paste-page.md) | いいえ  | はい |
| [レポート ページの削除](service-delete.md) | いいえ | はい |
|**レポートの視覚エフェクトの操作**|
||||
| [レポートへの視覚エフェクトの追加](power-bi-report-add-visualizations-i.md) | いいえ  | はい |
| [レポートへのテキスト ボックスと図形の追加](power-bi-reports-add-text-and-shapes.md) | いいえ  | はい |
| [レポートの書式設定ウィンドウの使用](service-the-report-editor-take-a-tour.md) | いいえ | はい |
| [ビジュアル対話の設定](service-reports-visual-interactions.md) | いいえ  | はい |
| [視覚エフェクトの作成に使用されたデータの表示](service-reports-show-data.md) | いいえ  | はい |
| [ドリルダウンの構成](power-bi-visualization-drill-down.md) | いいえ  | はい |
| [使用中の視覚エフェクトの変更](power-bi-report-change-visualization-type.md) | いいえ | はい|
| [視覚エフェクト、テキスト ボックス、または図形の削除](service-delete.md)| いいえ | はい |


## <a name="navigating-between-editing-view-and-reading-view"></a>編集ビューと読み取りビューの間の移動
編集ビューでレポートを開くことができるのはレポートの作成者と所有者 (複数可) のみであることに注意してください。

1. 通常、既定ではレポートは読み取りビューで開かれます。 **[レポートの編集]** オプションが表示されていれば、読み取りビューで開いていることになります。 **[レポートの編集]** が淡色表示の場合は、レポートを編集ビューで開くアクセス許可がありません。

   ![](media/service-reading-view-and-editing-view/power-bi-edit-report-grey.png)

2. **[レポートの編集]** が淡色表示になっていない場合は、それを選ぶとレポートが編集ビューで開きます。 
   
   ![](media/service-reading-view-and-editing-view/power-bi-edit-report.png)
   
   これでレポートが編集ビューに切り替わり、読み取りビューで最後に使用したものと同じ[表示設定](power-bi-report-display-settings.md)が使用されます。

2. 読み取りビューに戻るには、上部のナビゲーション バーにある **[読み取りビュー]** を選びます。
   
    ![](media/service-reading-view-and-editing-view/power-bi-reading-view.png)



### <a name="next-steps"></a>次の手順
読み取りビューにはレポートを編集するさまざまな手段があり、データを細かく切り分けて洞察を発見し、質問に対する回答を得ることができます。  次のトピックの「[Power BI の読み取りビューでレポートと対話する](service-interact-with-a-report-in-editing-view.md)」では、これらのいくつかについて詳しく説明されています。    
「[Power BI のレポート](service-reports.md)」に戻る    
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。 

