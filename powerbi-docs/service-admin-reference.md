---
title: 管理者のための PowerShell コマンドレット、REST API、.NET SDK
description: スクリプトとプログラミング API を使って Power BI を管理する方法について説明します。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f4455fef5a2ed0e7ee23ff8ca3a0b626cd695838
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507993"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>Power BI 管理のための PowerShell コマンドレット、REST API、.NET SDK
Power BI では、管理者が PowerShell コマンドレットを使用して一般的なタスクのスクリプトを作成できます。 REST API も公開され、管理ソリューションを開発するための .NET SDK が提供されます。 このトピックでは、コマンドレットの一覧と、それに対応する SDK メソッドおよび REST API エンドポイントを示します。 詳細については、次のトピックを参照してください。

  - PowerShell の[ダウンロード](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/)と[ドキュメント](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
  - REST API の[ドキュメント](https://docs.microsoft.com/rest/api/power-bi/admin)
  - .NET SDK の[ダウンロード](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) 


| **コマンドレット名** | **SDK メソッド** | **REST API エンドポイント** | **説明** |
| --- | --- | --- | --- |
| **Get PowerBIDatasource** | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | 指定されたデータセットのデータ ソースを取得します。 |
| **Get PowerBIDataset** | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Power BI テナント内の、データセットの完全な一覧を取得します。 |
| **Get PowerBIWorkspace** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Power BI テナント内の、ワークスペースの完全な一覧を取得します。 |
| **Add-PowerBIWorkspaceUser** | Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | 指定されたワークスペースのメンバーとしてユーザーを追加します。 |
| **Remove-PowerBIWorkspaceUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | 指定されたワークスペースのメンバーシップ一覧からユーザーを削除します。 |
| **Restore-PowerBIWorkspace** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | 削除されたワークスペースを復元します。 |
| **Set-PowerBIWorkspace** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | 指定されたワークスペースのプロパティを更新します。 |
| **Get-PowerBIDataset -WorkspaceId** | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | 指定されたワークスペース内のデータセットを取得します。 |
| **Export-PowerBIReport** | Reports\_ExportReportAsAdmin | 該当なし | 指定されたレポートをローカル ファイルにエクスポートします。 |
| **Get-PowerBIReport** | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Power BI テナント内の、レポートの完全な一覧を取得します。 |
| **Get-PowerBIDashboard** | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Power BI テナント内の、ダッシュボードの完全な一覧を取得します。 |
| **Get-PowerBIDashboard -WorkspaceId** | Groups\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | 指定されたワークスペース内のダッシュボードを取得します。 |
| **Get-PowerBITile -DashboardId** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | 指定したダッシュボードのタイルを取得します。 |
| **Get-PowerBIReport -WorkspaceId** | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | 指定されたワークスペース内のレポートを取得します。 |
| **Get-PowerBIImport** | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Power BI テナント内の、インポートの完全な一覧を取得します。 |
| **Connect-PowerBIServiceAccount** | 該当なし | 該当なし | Power BI にログインし、セッションを開始します。 |
| **Disconnect-PowerBIServiceAccount** | 該当なし | 該当なし | Power BI からログアウトし、既存のセッションを終了します。 |
| **Invoke-PowerBIRestMethod** | 該当なし | 該当なし | Power BI に任意の REST API 呼び出しを送信します。 |
| **Get-PowerBIAccessToken** | 該当なし | 該当なし | セッションの Power BI のアクセス トークンを取得します。 |
| **Resolve-PowerBIError** | 該当なし | 該当なし | 失敗したコマンドレットの呼び出しの詳細なエラー情報を取得します。 |