---
title: レポートのフィルター処理し、同僚の Power BI で共有
description: Power BI レポートをフィルター処理し、組織内の同僚と共有する方法を説明します。
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5f3808884e63521ec1dd775d876f1cf707bbe56b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770686"
---
# <a name="filter-a-power-bi-report-and-share-it-with-coworkers"></a>Power BI レポートをフィルター処理する同僚と共有
"*共有*" は、自分のダッシュボードおよびレポートに他のユーザーがアクセスできるようにするのによい方法です。 フィルター処理されたバージョンのレポートを共有したい場合は、どうすればよいでしょうか。 たとえば、特定の都市や販売員、または特定の年のデータだけを表示するレポートを共有したい場合があります。 お試しくださいレポートをフィルター処理し、共有、またはカスタム URL を作成します。 受信者が初めてレポートを開くと、フィルターが適用されます。 URL を変更することでフィルターを解除できます。 

Power BI では、[レポートを使って共同作業を行ったりレポートを配布したりする方法も他にいくつか](service-how-to-collaborate-distribute-dashboards-reports.md)用意されています。 共有する際、共有元と共有先の双方に [Power BI Pro ライセンス](service-features-license-type.md)が必要です。または、コンテンツを [Premium 容量](service-premium-what-is.md)に格納する必要があります。 

## <a name="two-ways-to-filter-a-report"></a>2 つの方法でレポートをフィルター処理

### <a name="set-a-filter"></a>フィルターを設定します。

[編集ビュー](consumer/end-user-reading-view.md)でレポートを開き、フィルターを適用して、レポートを保存します。
   
この例では、[小売の分析のサンプル](sample-tutorial-connect-to-the-samples.md)をフィルター処理して、**Territory** が **NC** の値のみを表示します。
   
![[レポート フィルター] ウィンドウ](media/service-share-reports/power-bi-filter-report2.png)

### <a name="create-a-filter-in-the-url"></a>URL にフィルターを作成します。

レポート ページの URL の末尾に以下を追加します:
   
?filter=*tablename*/*fieldname* eq *value*
   
フィールドの種類の番号、datetime、または文字列でなければなりません。 *tablename* 値または *fieldname* 値にはスペースを含めることができません。
   
この例では、テーブルの名前が **Store**、フィールドの名前が **Territory**、フィルター処理の対象の値が **NC** です。
   
?filter=Store/Territory eq 'NC'
   
![フィルター処理されたレポートの URL](media/service-share-reports/power-bi-filter-url3.png)
   
スラッシュ、スペース、およびアポストロフィを表すために、ブラウザーによって特殊文字が追加されるため、最終的に次のようになります。
   
app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

記事をご覧ください[を URL にクエリ文字列パラメーターを使用してレポートをフィルター処理](service-url-filters.md)の詳細な説明。

## <a name="share-the-filtered-report"></a>フィルター処理されたレポートを共有します。

1. ときにする[レポートを共有](service-share-dashboards.md)チェック ボックスをオフ、**受信者に電子メール通知を送信**チェック ボックスをオンします。

    ![[レポートの共有] ダイアログ ボックス](media/service-share-reports/power-bi-share-report-dialog.png)

4. 先ほど作成したフィルターを使用して、リンクを送信します。

## <a name="next-steps"></a>次の手順
* ご意見およびご提案がある場合は、 [Power BI コミュニティ サイト](https://community.powerbi.com/)をご利用ください。
* [ダッシュボードとレポートを共有する方法](service-how-to-collaborate-distribute-dashboards-reports.md)
* [ダッシュボードの共有](service-share-dashboards.md)
* 他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

