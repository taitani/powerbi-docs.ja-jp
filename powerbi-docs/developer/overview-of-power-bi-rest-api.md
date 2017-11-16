---
title: "Power BI API の機能"
description: "Power BI API の機能"
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/20/2017
ms.author: asaxton
ms.openlocfilehash: 23a77e2b8ac8754b122888e3d0d64f2c3886b61b
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="what-can-developers-do-with-power-bi"></a>Power BI の開発者向け機能
Power BI には、対話型で、さまざまなデータ ソースからリアルタイムで作成、更新できるダッシュボードが表示されます。 REST 呼び出しをサポートするプログラミング言語を使って、リアルタイムで Power BI ダッシュボードと統合するアプリを作成できます。 アプリに、Power BI のタイルとレポートを統合することもできます。

開発者は、対話型のレポートやダッシュ ボードで使用できる独自のデータ表示を作成することもできます。 

Power BI API を使って行うことのできる例は以下のとおりです。

| **操作の内容** | **参照先** |
| --- | --- |
| Power BI ユーザーと Power BI 以外のユーザーのためにダッシュボード、レポート、タイルを埋め込む (アプリ所有データ) |[Power BI ダッシュボード、レポート、およびタイルを埋め込む方法](embedding-content.md) |
| 既存のビジネス ワークフローを拡張して、主要なデータを Power BI ダッシュボードにプッシュします。 |[ダッシュボードにデータをプッシュする](walkthrough-push-data.md) |
| Power BI Desktop ファイルをインポートする |[PBIX ファイルをインポートする](https://msdn.microsoft.com/library/mt243837.aspx) |
| Power BI に対して認証を行う |[Power BI に対して認証を行う](get-azuread-access-token.md) |
| カスタム ビジュアルを作成します。 |[開発者ツールを使ってカスタム ビジュアルを作成する](../service-custom-visuals-getting-started-with-developer-tools.md) |

> [!NOTE]
> Power BI API では引き続き、アプリ ワークスペースをグループと呼びます。 したがって、グループと記述されている場合はすべて、アプリ ワークスペースを使用していることを意味します。
> 
> 

## <a name="power-bi-developer-samples"></a>Power BI の開発者向けサンプル
Power BI 開発者向けのサンプルには、ダッシュ ボード、レポート、タイルの埋め込み項目が含まれます。

[Power BI の開発者向けサンプル](https://github.com/Microsoft/PowerBI-Developer-Samples)

* **App Owns Data** 内のサンプルは Power BI 以外のユーザーでの埋め込み用です。
* **User Owns Data** 内のサンプルは Power BI ユーザーでの埋め込み用です。

## <a name="github-repositories"></a>GitHub リポジトリ
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)
* [カスタム ビジュアル](https://github.com/Microsoft/PowerBI-visuals)

## <a name="developer-tools"></a>開発者向けツール
次は、Power BI 項目の開発を支援するツールです。

* [Apiari 対話型 API コンソール](http://docs.powerbi.apiary.io/)
* [JavaScript 埋め込みサンプル](https://microsoft.github.io/PowerBI-JavaScript/demo)

## <a name="next-steps"></a>次の手順
[データセットにデータをプッシュする](walkthrough-push-data.md)  
[カスタム ビジュアル開発者ツールの概要](../service-custom-visuals-getting-started-with-developer-tools.md) 
[Power BI REST API リファレンス](https://msdn.microsoft.com/library/mt147898.aspx)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

