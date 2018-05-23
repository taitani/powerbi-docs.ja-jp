---
title: データセットにデータをプッシュする
description: Power BI データセットにデータをプッシュする
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 01/05/2017
ms.author: maghan
ms.openlocfilehash: 76d07c8384123a303c8801a45ecd05b9e6ed0321
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="push-data-into-a-power-bi-dataset"></a>Power BI データセットにデータをプッシュする
Power BI API を使うと、Power BI データセットにデータをプッシュできます。 たとえば、既存のビジネス ワークフローを拡張して、主要なデータをデータセットにプッシュできます。 ここでは、Product テーブルを含む Sales Marketing データセットをデータセットにプッシュします。

データセットへのデータのプッシュを始めるには、Azure Active Directory (Azure AD) と [Power BI アカウント](create-an-azure-active-directory-tenant.md)が必要です。

## <a name="steps-to-push-data-into-a-dataset"></a>データセットにデータをプッシュする手順
* 手順 1: [アプリを Azure AD に登録する](walkthrough-push-data-register-app-with-azure-ad.md)
* 手順 2: [認証アクセス トークンを取得する](walkthrough-push-data-get-token.md)
* 手順 3: [Power BI でデータセットを作成する](walkthrough-push-data-create-dataset.md)
* 手順 4: [Power BI テーブルに行を追加するためにデータセットを取得する](walkthrough-push-data-get-datasets.md)
* 手順 5: [Power BI テーブルに行を追加する](walkthrough-push-data-add-rows.md)

次のセクションでは、データをプッシュする Power BI API 操作の概要を説明します。

## <a name="power-bi-api-operations-to-push-data"></a>データをプッシュする Power BI API の操作
Power BI REST API を使うと、Power BI にデータ ソースをプッシュできます。 アプリがデータセットに行を追加すると、ダッシュボード上のタイルは自動的に最新データに更新されます。 データをプッシュするには、[データセットの作成](https://msdn.microsoft.com/library/mt203562.aspx)操作と[行の追加](https://msdn.microsoft.com/library/mt203561.aspx)操作を一緒に行います。 データセットを検索するには、[データセットの取得](https://msdn.microsoft.com/library/mt203567.aspx)操作を行います。 これらの操作のどれについても、グループ ID を渡すとグループを操作できます。 [グループの取得](https://msdn.microsoft.com/library/mt243842.aspx)操作を行うと、グループ ID の一覧を取得できます。

データセットにデータをプッシュするための操作を次に示します。

* [データセットの作成](https://msdn.microsoft.com/library/mt203562.aspx)
* [データセットの取得](https://msdn.microsoft.com/library/mt203567.aspx)
* [行の追加](https://msdn.microsoft.com/library/mt203561.aspx)
* [グループの取得](https://msdn.microsoft.com/library/mt243842.aspx)

Power BI でデータセットを作成するには、Power BI サービスに JavaScript Object Notation (JSON) 文字列を渡します。 JSON について詳しくは、「[JSON の紹介](http://json.org/)」をご覧ください。

データセットの JSON 文字列は、次のような形式です。

**Power BI のデータセット JSON オブジェクト**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

したがって、Sales Marketing データセットの例では、以下のような JSON 文字列を渡すことになります。 この例では **SalesMarketing** がデータセットの名前、 **Product** がテーブルの名前です。 テーブルを定義した後は、テーブル スキーマを定義します。 **SalesMarketing** データセットの場合、テーブル スキーマには、ProductID、Manufacturer、Category、Segment、Product、IsCompete の列が含まれています。

**データセット オブジェクト JSON の例**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Power BI のテーブル スキーマでは、次のデータ型を使うことができます。

## <a name="power-bi-table-data-types"></a>Power BI テーブルのデータ型
| **データ型** | **制限事項** |
| --- | --- |
| Int64 |Int64.MaxValue と Int64.MinValue が許可されまていせん。 |
| Double |Double.MaxValue と Double.MinValue 値が許可されていません。 NaN はサポートされていません。一部の関数では正の無限大と負の無限大がサポートされていません (例: Min、Max)。 |
| ブール値 |なし |
| DateTime |データの読み込み中に、日時分数の値を 1/300 秒 (3.33ms) の整数倍に量子化します。 |
| 文字列 |現在、最大 128 文字が許可されています。 |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Power BI へのデータのプッシュに関する詳細
データセットへのデータのプッシュを始める方法については、左側のナビゲーション ウィンドウにある「[手順 1: アプリを Azure AD に登録する](walkthrough-push-data-register-app-with-azure-ad.md)」をご覧ください。

[次の手順 >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>次の手順
[Power BI にサインアップする](create-an-azure-active-directory-tenant.md)  
[データセットの作成](https://msdn.microsoft.com/library/mt203562.aspx)  
[データセットの取得](https://msdn.microsoft.com/library/mt203567.aspx)  
[行の追加](https://msdn.microsoft.com/library/mt203561.aspx)  
[グループの取得](https://msdn.microsoft.com/library/mt243842.aspx)  
[JSON の紹介](http://json.org/)  
[Power BI REST API の概要](overview-of-power-bi-rest-api.md)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

