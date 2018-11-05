---
title: アプリからレポートやダッシュボードを埋め込む
description: アプリ ワークスペースからではなく、Power BI アプリからレポートやダッシュボードを統合する (埋め込む) 方法について説明します。
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: how-to
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 53803c77dec8eb35c10db7f19a82f58144f88414
ms.sourcegitcommit: b45134887a452f816a97e384f4333db9e1d8b798
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47237987"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>アプリからレポートやダッシュボードを埋め込む

Power BI では、関連のあるダッシュボードやレポートをまとめて 1 つの場所に表示するアプリを作成できます。 その後、それらのアプリを組織内の多数のユーザーに発行します。 これらのアプリの使用は、ユーザーがすべて Power BI ユーザーである場合に関連します。 したがって、Power BI アプリを使用すれば、コンテンツをそれらのユーザーと共有することができます。 この記事では、発行済み Power BI アプリから、およびサード パーティ製アプリケーションへのコンテンツの埋め込むを行う簡単な手順をいくつか示します。

## <a name="grab-a-report-embedurl-for-embedding"></a>埋め込み用のレポート embedURL を取得する

1. ユーザー ワークスペース (**マイ ワークスペース**) でアプリケーションをインスタンス化します。 自分自身と共有するか、またはこのフローを完了するように別のユーザーを誘導します。

2. Power BI サービスで、目的のレポートを開きます。

3. **[ファイル]** > **[Embed In SharePoint Online]\(SharePoint Online に埋め込む\)** に移動し、そこからレポート embedURL を取得します。 この操作は次のスナップショットに示されています。 または、GetReports/GetReport REST API を呼び出し、応答から対応するレポート embedURL フィールドを抽出します。 ユーザーのワークスペースでアプリがインスタンス化されるため、REST 呼び出しでは URL の一部としてワークスペース識別子は使用できません。

4. JavaScript SDK で、手順 3 で取得した embedURL を使用します。

    ![アプリからの埋め込み](media/embed-from-apps/embed-from-app.png)

## <a name="grab-a-dashboard-embedurl-for-embedding"></a>埋め込み用のダッシュボード embedURL を取得する

1. ユーザー ワークスペース (**マイ ワークスペース**) でアプリケーションをインスタンス化します。 自分自身と共有するか、またはこのフローを完了するように別のユーザーを誘導します。

2. GetDashboards REST API を呼び出し、応答から対応するダッシュボード embedURL フィールドを抽出します。 ユーザーのワークスペースでアプリがインスタンス化されるため、REST 呼び出しでは URL の一部としてワークスペース識別子は使用できません。

3. JavaScript SDK で、手順 2 で取得した embedURL を使用します。

## <a name="next-steps"></a>次の手順

サード パーティの顧客と組織向けのアプリ ワークスペースから埋め込む方法を確認します。

> [!div class="nextstepaction"]
>[サード パーティの顧客向けの埋め込み](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[組織向けの埋め込み](embed-sample-for-your-organization.md)