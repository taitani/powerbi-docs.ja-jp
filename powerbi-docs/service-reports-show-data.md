---
title: "Power BI ビジュアルの作成に使用されたデータを表示する"
description: "このドキュメントでは、Power BI でビジュアルを作成するために使用されたデータを表示する方法、およびそのデータを .csv ファイルにエクスポートする方法について説明します。"
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
ms.date: 10/25/2017
ms.author: mihart
ms.openlocfilehash: 5fcfd09e74f661a1cc5ab8fcda6cf4cd0525437a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="show-the-data-that-was-used-to-create-the-visualization"></a>ビジュアルの作成に使用されたデータを表示する
## <a name="show-data"></a>データの表示
Power BI のビジュアルは、データセットからのデータを使用して作成されます。 目に見えない部分を確認する場合は、ビジュアルの作成に使用されているデータを Power BI によって*表示*することができます。 **[データの表示]** を選択すると、ビジュアルの下 (または横に) データが表示されます。

また、ビジュアルの作成に使用されているデータを .xlsx ファイルまたは .csv ファイルとしてエクスポートして Excel で表示することもできます。 詳細については、「[Power BI ビジュアルからデータをエクスポートする](power-bi-visualization-export-data.md)」を参照してください。

> [!NOTE]
> [*データの表示*] と [*データのエクスポート*] は両方とも、Power BI サービスと Power BI Desktop で使用できます。 ただし、Power BI Desktop では、詳細を示すレイヤーが 1 つ追加されています。[[*レコードの表示*] にはデータセットからの実際の行が表示されます](desktop-see-data-see-records.md)。
> 
> 

## <a name="using-show-data-in-power-bi-service"></a>Power BI サービスでの [*データの表示*] の使用
1. Power BI サービスの[読み取りビュー](service-report-open-in-reading-view.md)または[編集ビュー](service-reading-view-and-editing-view.md)でレポートを開き、ビジュアルを選択します。  Power BI Desktop でレポート ビューを開きます。
2. ビジュアルの背後にあるデータを表示するには、**[探索]** > **[データの表示]** の順に選択します。
   
   ![](media/service-reports-show-data/power-bi-show-data.png)
3. 既定では、データはビジュアルの下に表示されます。
   
   ![](media/service-reports-show-data/power-bi-explore-show-data.png)
4. 向きを変更するには、ビジュアルの右上隅にある縦レイアウト ![](media/service-reports-show-data/power-bi-vertical-icon-new.png) を選びます。
   
   ![](media/service-reports-show-data/power-bi-explore-show-data2.png)
5. データを .csv ファイルにエクスポートするには、省略記号を選択し、**[データのエクスポート]** を選択します。
   
    ![](media/service-reports-show-data/power-bi-export-data-new.png)
   
    Excel へのデータのエクスポートの詳細については、「[Power BI ビジュアルからデータをエクスポートする](power-bi-visualization-export-data.md)」を参照してください。
6. データを非表示にするには、**[探索]** > **[データの表示]** の選択を解除します。

### <a name="next-steps"></a>次の手順
[Power BI ビジュアルからデータをエクスポートする](power-bi-visualization-export-data.md)    
[Power BI レポートでの視覚化](power-bi-report-visualizations.md)    
[Power BI レポート](service-reports.md)    
[Power BI - 基本的な概念](service-basic-concepts.md)    
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

