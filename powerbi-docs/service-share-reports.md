---
title: "Power BI のレポートを同僚と共有する"
description: "Power BI レポートおよびフィルター処理されたレポートを組織内の同僚と共有する方法を説明します。"
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: complete
qualitydate: 06/22/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/14/2017
ms.author: maggies
ms.openlocfilehash: 022f085d12d7dc872052ca9205deca264b1c0418
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="share-power-bi-reports-with-your-coworkers"></a>Power BI のレポートを同僚と共有する
"*共有*" は、自分のダッシュボードおよびレポートに他のユーザーがアクセスできるようにするのによい方法です。 Power BI には、[レポートを使って共同作業を行ったりレポートを配布したりする方法が複数用意されており](service-how-to-collaborate-distribute-dashboards-reports.md)、共有はその 1 つにすぎません。

共有する際、共有元と共有先の双方に [Power BI Pro ライセンス](service-free-vs-pro.md)が必要です。または、コンテンツを [Premium 容量](service-premium.md)に格納する必要があります。 Power BI チームへのご提案は、 [Power BI コミュニティ サイト](https://community.powerbi.com/)でフィードバックをお送りください。

共有元のユーザーは、自分のマイ ワークスペースまたはアプリ ワークスペースから、自分と同じメール ドメインの同僚とレポートを共有できます。 同僚とレポートを共有した場合、共有先のユーザーはレポートを表示して操作することはできますが、レポートを編集することはできません。 [行レベル セキュリティ (RLS)](service-admin-rls.md) が適用されていない限り、自分のレポートに表示されるものと同じデータが同僚にも表示されます。 

## <a name="share-a-power-bi-report"></a>Power BI レポートを共有する
1. Power BI サービスで、共有するレポートにリンクする少なくとも 1 つのタイルを使用して[ダッシュボードを作成します](service-dashboard-create.md)。 
   
    レポートだけを共有したい場合でも、最初に、レポートにリンクするダッシュボードを作成して共有する必要があります。 

1. ダッシュボードの右上で、**[共有]** を選択します。

     ![[共有] を選択します。](media/service-share-reports/power-bi-share-upper-right.png)
  
2. 目的の受信者のアドレスを指定します。 ダッシュボードについてメールを送信しない場合は、**[電子メール通知を受信者に送信する]**チェック ボックスをオフにします。

     ![[電子メール通知の送信] チェック ボックスをオフにする](media/service-share-reports/power-bi-share-dont-send-mail.png)

4. **[共有]**を選択します。

      ダッシュボードを共有されたユーザーは、基になるレポートを表示するアクセス許可を持つようになります。 

1. Power BI サービスでレポートを開き、レポート ページの URL をコピーして同僚に送信します。 
   
    同僚がリンクを選ぶと、Power BI で読み取り専用バージョンのレポートが開きます。

## <a name="share-a-filtered-version-of-a-report"></a>フィルター処理されたバージョンのレポートを共有する
フィルター処理されたバージョンのレポートを共有したい場合は、どうすればよいでしょうか。 たとえば、特定の都市や販売員、または特定の年のデータだけを表示するレポートを共有したい場合があります。 そのような場合はカスタム URL を作成します。

1. [編集ビュー](service-reading-view-and-editing-view.md)でレポートを開き、フィルターを適用して、レポートを保存します。
   
   この例では、[小売の分析のサンプル](sample-tutorial-connect-to-the-samples.md)をフィルター処理して、**Territory** が **NC** の値のみを表示します。
   
   ![[レポート フィルター] ウィンドウ](media/service-share-reports/power-bi-filter-report2.png)
2. レポート ページの URL の末尾に以下を追加します:
   
   ?filter=*tablename*/*fieldname* eq *value*
   
    フィールドは **string** 型である必要があり、*tablename* または *fieldname* にスペースを含めることはできません。
   
   この例では、テーブルの名前が **Store**、フィールドの名前が **Territory**、フィルター処理の対象の値が **NC** です。
   
    ?filter=Store/Territory eq NC
   
   ![フィルター処理されたレポートの URL](media/service-share-reports/power-bi-filter-url3.png)
   
   スラッシュとスペースを正しく表すために、ブラウザーによって特殊文字が追加されるため、最終的に次のようになります。
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-10a61f70f2f5/ReportSection2?filter=Store%252FTerritory%20eq%20NC
3. この URL を同僚に送信します。 
   
   同僚がリンクを選ぶと、Power BI で読み取り専用バージョンのフィルター処理されたレポートが開きます。

## <a name="next-steps"></a>次の手順
* ご意見およびご提案がある場合は、 [Power BI コミュニティ サイト](https://community.powerbi.com/)をご利用ください。
* [ダッシュボードとレポートを共有する方法](service-how-to-collaborate-distribute-dashboards-reports.md)
* [ダッシュボードの共有](service-share-dashboards.md)
* 他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

