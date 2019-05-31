---
title: 自動が組織に埋め込むときに、Power BI アプリをインストールします。
description: 組織向けのインストールの Power BI アプリの自動方法を説明します。
ms.subservice: powerbi-developer
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.topic: how-to
ms.service: powerbi
ms.custom: ''
ms.date: 04/16/2019
ms.openlocfilehash: bb9ba5531c2a23f15ccbf98261e246ab7080aecb
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "61376229"
---
# <a name="auto-install-power-bi-apps-when-embedding-for-your-organization"></a>組織に埋め込むときに自動-Power BI アプリをインストール.

アプリからのコンテンツを埋め込むには、埋め込みはユーザーがいる必要があります[、アプリへのアクセス](../service-create-distribute-apps.md)します。 ユーザーのアプリをインストールする場合は、円滑に動作し、埋め込み。 詳細については、次を参照してください。[アプリからダッシュ ボードまたはレポートを埋め込む](embed-from-apps.md)します。 すべてのアプリは、PowerBI.com で定義することは[自動的にインストールされている](https://powerbi.microsoft.com/blog/automatically-install-apps/)します。 ただし、この操作は、テナント レベルでは行われ、すべてのアプリに適用されます。

## <a name="auto-install-app-on-embedding"></a>埋め込みの自動インストール アプリ

ユーザーが、アプリへのアクセス、アプリがインストールされていない、し、埋め込みが失敗した場合。 このようなエラーを回避するには、アプリから埋め込むときに、ために埋め込みアプリの自動インストールを許可できます。 このアクションが自動的にインストール、ユーザーが、埋め込みしようとしています。 アプリがインストールされていない場合を意味します。 ようにコンテンツを取得埋め込まれた、すぐにその結果、ユーザーの滑らかなエクスペリエンス。

## <a name="embed-for-power-bi-users-user-owns-data"></a>Power BI のユーザー (ユーザー所有データ) 向けの埋め込み

ユーザー向けのアプリの自動インストールを許可するには、アプリケーションに 'コンテンツ作成' アクセス許可を付与する必要がありますと[アプリケーションを登録する](register-app.md#register-with-the-power-bi-application-registration-tool)、か、アプリが既に登録されている場合は、それを追加します。

![アプリの登録は、コンテンツを作成します。](media/embed-auto-install-app/register-app-create-content.png)

次に、埋め込み URL にアプリ ID を指定する必要があります。 アプリ ID を提供するアプリの作成者は、まず必要があります、アプリをインストールしてから、サポートされているのいずれかを使用して、 [Power BI Rest API](https://docs.microsoft.com/rest/api/power-bi/)呼び出し[レポートの取得](https://docs.microsoft.com/rest/api/power-bi/reports/getreports)または[ダッシュ ボードを取得](https://docs.microsoft.com/rest/api/power-bi/dashboards/getdashboards)します。 アプリ作成者の REST API の応答からに埋め込み Url を実行する必要があります。 アプリ ID は、アプリからのコンテンツがある場合に、URL に表示されます。  埋め込み URL がある場合は後、は、定期的に埋め込むには使用できます。

## <a name="secure-embed"></a>セキュリティで保護を埋め込む

アプリの自動インストールを使用するには、アプリの作成者は、まずする必要がアプリをインストールし、移動、PowerBI.com でアプリには、レポートに移動し、通常の方法で、リンクを取得します。 ある リンクを使用できるアプリへのアクセス権を持つその他のすべてのユーザーには、レポートを埋め込むことができます。

## <a name="considerations-and-limitations"></a>考慮事項と制限事項

* レポートとこのシナリオ用のダッシュ ボードを埋め込むことができますのみです。

* この機能は現在サポートされていませんアプリ所有データと、SharePoint の埋め込みシナリオ。