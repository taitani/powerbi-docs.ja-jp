---
title: Azure SQL Database と DirectQuery
description: Azure SQL Database と DirectQuery
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/20/2018
LocalizationGroup: Data from databases
ms.openlocfilehash: 5365c076b75d0989df8db15c1dc16f4e11bc3f09
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448397"
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL Database と DirectQuery

Azure SQL Database に直接接続し、ライブ データを使用するレポートを作成する方法について説明します。 Power BI ではなくソースにデータを保持できます。

DirectQuery を使用すると、レポート ビューでデータを調べる際にクエリが Azure SQL Database に送り返されます。 この操作は、接続先のデータベースとエンティティに精通しているユーザーにお勧めします。

**注:**

* 接続するときに、完全修飾のサーバー名を指定します (詳細については後述します)。
* データベースのファイアウォール ルールが "[Azure サービスに対するアクセスを許可する](https://msdn.microsoft.com/library/azure/ee621782.aspx)" ように構成されていることを確認します。
* 列の選択、フィルターの追加など、どの操作によってもクエリがデータベースに送り返されます。
* タイルは、1 時間ごとに更新されます (更新をスケジュール設定する必要はありません)。 この動作は、接続するときに [詳細] 設定で調整できます。
* DirectQuery データセットの Q&A は使用できません。
* スキーマ変更は自動選択されません。

これらの制限および注意事項については、エクスペリエンスの向上に伴い変更される可能性があります。 接続するための手順の詳細を以下に示します。

> [!Important]
> Azure SQL Database への接続性を改善しました。  Azure SQL Database データ ソースに接続するための操作性を向上させるには、Power BI Desktop を使用します。  モデルとレポートをビルドしたら、Power BI サービスに発行できます。  Power BI サービス内の Azure SQL Database への直接接続は、非推奨になりました。

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop と DirectQuery

DirectQuery を使用して Azure SQL Database に接続するには、Power BI Desktop を使用する必要があります。 この方法でさらに柔軟性と機能が向上します。 Power BI Desktop を使用して作成したレポートを、Power BI サービスに発行できます。 Power BI Desktop で DirectQuery を使用して Azure SQL Database に接続する方法の詳細については、「[Power BI Desktop の DirectQuery](desktop-use-directquery.md)」をご覧ください。

## <a name="finding-parameter-values"></a>パラメーターの値の見つけ方

完全修飾サーバー名とデータベース名は、Azure portal に表示されています。

![新しい Azure ポートの更新](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Azure portal の更新](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](includes/direct-query-sso.md)]

## <a name="next-steps"></a>次の手順

* [Power BI Desktop で DirectQuery を使用する](desktop-use-directquery.md)  
* [Power BI とは?](power-bi-overview.md)  
* [Power BI のデータの取得](service-get-data.md)  

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。
