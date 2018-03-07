---
title: "Power BI Desktop での行レベルのセキュリティ (RLS) を理解する"
description: "Power BI Desktop 内にインポートしたデータセットと DirectQuery の行レベルのセキュリティを構成する方法。"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maghan
LocalizationGroup: Create reports
ms.openlocfilehash: febe8cafb7be578be0dcf23a151f28deb544a4c8
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Power BI Desktop での行レベルのセキュリティ (RLS)
Power BI Desktop で行レベル セキュリティ (RLS) を使用すると、特定のユーザーのデータ アクセスを制限できます。 フィルターは、行レベルでデータを制限します。 役割内でフィルターを定義できます。

Power BI Desktop で Power BI にインポートされたデータ モデルの RLS を構成できます。 SQL Server などの DirectQuery を使用しているデータセットに RLS を構成することもできます。 これまで、RLS を実装できるのは、Power BI の外部にあるオンプレミスの Analysis Services モデル内だけでした。 Analysis Services のライブ接続では、オンプレミスのモデルに行レベルのセキュリティを構成します。 このセキュリティ オプションは、ライブ接続データセットには表示されません。

> [!IMPORTANT]
> Power BI サービス内で役割/ルールを定義した場合は、Power BI Desktop でこれらの役割を作成しなおし、サービスにレポートを公開する必要があります。
> 
> 

Power BI サービス内の RLS のオプションについては、[こちら](service-admin-rls.md)を参照してください。

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>次の手順
[Power BI サービスでの行レベルのセキュリティ (RLS)](service-admin-rls.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

