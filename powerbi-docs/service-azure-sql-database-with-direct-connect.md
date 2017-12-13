---
title: "Azure SQL Database と DirectQuery"
description: "Azure SQL Database と DirectQuery"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 83613f0ed915a03b65b90d4bf61e37568b922182
ms.sourcegitcommit: c2deaff54434da67698a14cc00172a2119ed1a56
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2017
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL Database と DirectQuery
Azure SQL Database に直接接続し、ライブ データを使用するレポートを作成する方法について説明します。 Power BI ではなくソースにデータを保持できます。

DirectQuery を使用すると、レポート ビューでデータを調べる際にクエリが Azure SQL Database に送り返されます。 この操作は、接続先のデータベースとエンティティに精通しているユーザーにお勧めします。

**注:**

* 接続するときに、完全修飾のサーバー名を指定します (詳細については後述します)。
* データベースのファイアウォール ルールが[「Azure サービスに対するアクセスを許可](https://msdn.microsoft.com/library/azure/ee621782.aspx)」するように構成されていることを確認してください。
* 列の選択、フィルターの追加など、どの操作によってもクエリがデータベースに送り返されます。
* タイルは、約 15 分ごとに更新されます (更新をスケジュール設定する必要はありません)。 この動作は、接続するときに [詳細] 設定で調整できます。
* DirectQuery データセットの Q&A は使用できません。
* スキーマ変更は自動選択されません。

これらの制限および注意事項については、エクスペリエンスの向上に伴い変更される可能性があります。 接続するための手順の詳細を以下に示します。 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop と DirectQuery
DirectQuery を使用して Azure SQL Database に接続するには、Power BI Desktop を使用する必要があります。 この方法はさらに柔軟性と機能が向上します。 Power BI Desktop を使用して作成したレポートを、Power BI サービスに発行できます。 Power BI Desktop で DirectQuery を使用して Azure SQL Database に接続する方法の詳細については、「[Power BI Desktop の DirectQuery](desktop-use-directquery.md)」をご覧ください。 

## <a name="connecting-through-power-bi"></a>Power BI 経由で接続する
現在は、Power BI サービスから直接 Azure SQL Database に接続することはできません。 [Azure SQL Database コネクタ](https://app.powerbi.com/getdata/bigdata/azure-sql-database-with-live-connect)を選択すると、Power BI Desktop 内で接続するように求められます。 接続した後は、Power BI Desktop レポートを Power BI サービスに公開できます。 

![](media/service-azure-sql-database-with-direct-connect/azure-sql-database-in-power-bi.png)

### <a name="finding-parameter-values"></a>パラメーターの値の見つけ方
完全修飾サーバー名とデータベース名は、Azure Portal に記されています。

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>次の手順
[Power BI Desktop で DirectQuery を使用する](desktop-use-directquery.md)  
[Power BI の概要](service-get-started.md)  
[Power BI のデータの取得](service-get-data.md)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

