---
title: Power BI サービスでデータセット パラメーターの設定を表示および編集する
description: クエリ パラメーターは Power BI Desktop で作成されますが、Power BI サービスで確認および更新できます
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/26/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: ac271e8013bce5824931153351a651644a716a2f
ms.sourcegitcommit: 5eb8632f653b9ea4f33a780fd360e75bbdf53b13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965161"
---
# <a name="what-is-a-query-parameter"></a>クエリ パラメーターとは
クエリ パラメーターは、レポート作成者によって Power BI Desktop に追加されます。 パラメーターを使用すると、1 つまたは複数のパラメーターの*値*に応じてレポートの一部を作成することができます。 たとえば、レポート作成者は、1 つの国または地域に対してデータを制限するパラメーターや日付、時刻、テキストなどのフィールドに使用できる形式を定義するパラメーターを作成できます。

![Desktop で [パラメーターの管理] オプションを表示している [ホーム] タブ](media/service-parameters/power-bi-manage-parameters.png)


## <a name="review-and-edit-parameters-in-power-bi-service"></a>Power BI サービスでパラメーターを確認および編集する

パラメーターが Desktop で定義されると、[レポートが Power BI サービスに発行される](desktop-upload-desktop-files.md)ときに、パラメーターの設定と選択がレポートと共に移動されます。 一部のパラメーターの設定は、Power BI サービスで確認および編集できます。利用可能なデータを制限するパラメーターを操作することはできませんが、使用できる値を定義して説明するパラメーターは操作できます。

1. Power BI サービスで、![歯車アイコン](media/service-parameters/power-bi-cog.png) を選択して、**[設定]** を開きます。

2. **[データセット]** のタブを選択して、リスト内のデータセットを強調表示します。 
    
    ![[データセット] タブが選択されている [設定] ウィンドウ](media/service-parameters/power-bi-select-dataset2.png)

3. **[パラメーター]** を展開します。  選択したデータセットにパラメーターがない場合、クエリ パラメーターに関する詳細へのリンクを含むメッセージが表示されます。 ただし、データセットにパラメーターが存在する場合は、**[パラメーター]** 見出しを展開すると、そのパラメーターが表示されます。 

    ![[パラメーター] が展開されている [設定] ウィンドウ](media/service-parameters/power-bi-settings.png)

    必要に応じて、パラメーターの設定を確認し、変更します。 灰色表示のフィールドは編集できません。 


## <a name="next-steps"></a>次の手順
シンプルなパラメーターを追加する特別な方法として、[URL を変更します](service-url-filters.md)。