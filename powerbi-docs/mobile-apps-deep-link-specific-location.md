---
title: Power BI モバイル アプリの特定の場所へのリンクを作成する
description: URI (Uniform Resource Identifier) で Power BI モバイル アプリの特定のダッシュボード、タイル、またはレポートへのディープ リンクを作成する方法について説明します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/28/2018
ms.author: maggies
ms.openlocfilehash: e1df06c07f767936d861788c89205bce20cd5582
ms.sourcegitcommit: 60f637d8555fd59fd9a86de720b89b388fb85ac0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43695135"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Power BI モバイル アプリの特定の場所へのリンクを作成する
URI (Uniform Resource Identifier) を作成して使用することで、すべてのモバイル プラットフォーム (iOS、Android デバイス、Windows 10) で Power BI モバイル アプリ内の特定の場所にリンクすることができます (*ディープ リンク*)。

URI のリンクは、ダッシュボード、タイル、およびレポートを直接指し示すことができます。

ディープ リンクのリンク先により、URI の形式が決まります。 異なる場所へのディープ リンクを作成するには、次の手順のようにします。 

## <a name="open-the-power-bi-mobile-app"></a>Power BI モバイル アプリを開く
任意のデバイスの Power BI モバイル アプリを開くには、次の URI を使います。

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>特定のダッシュボードを開く
Power BI モバイル アプリの特定のダッシュボードを開くには、次の URI を使います。

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

ダッシュボードの 36 文字のオブジェクト ID を検索するには、Power BI サービス (https://powerbi.com) で特定のダッシュボードに移動します。 たとえば、次の URL の強調表示された部分を見てください。

`https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**`

ダッシュボードがマイ ワークスペース以外のグループにある場合は、ダッシュボード ID の前または後に `&GroupObjectId=<36-character-group-id>` を追加します。 次はその例です。 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

2 つの間のアンパサンド (&) に注意してください。

## <a name="open-to-a-specific-tile-in-focus"></a>特定のタイルにフォーカスを設定して開く
Power BI モバイル アプリの特定のタイルにフォーカスを設定して開くには、次の URI を使います。

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

ダッシュボードとタイルの 36 文字のオブジェクト ID を検索するには、Power BI サービス (https://powerbi.com) で特定のダッシュボードに移動し、フォーカス モードでタイルを開きます。 たとえば、次の URL の強調表示された部分を見てください。

`https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus`

このタイルの URI は次のようになります。

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

2 つの間のアンパサンド (&) に注意してください。

ダッシュボードがマイ ワークスペース以外のグループにある場合は、`&GroupObjectId=<36-character-group-id>` を追加します。

## <a name="open-to-a-specific-report"></a>特定のレポートを開く
Power BI モバイル アプリの特定のレポートを開くには、次の URI を使います。

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

レポートの 36 文字のオブジェクト ID を検索するには、Power BI サービス (https://powerbi.com) で特定のレポートに移動します。 たとえば、次の URL の強調表示された部分を見てください。

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300`

## <a name="open-to-a-specific-report-page"></a>特定のレポート ページを開く
Power BI モバイル アプリの特定のレポート ページを開くには、次の URI を使います。

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

レポート ページを呼び出すには、"ReportSection" に続けて番号を指定します。 ここでも、Power BI サービス (https://powerbi.com) でレポートを開き、特定のレポート ページに移動します。 

たとえば、次の URL の強調表示された部分を見てください。

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/ReportSection11`

## <a name="open-in-full-screen-mode"></a>全画面表示モードで開く
太字のパラメーターを追加して、全画面表示モードで特定のレポートを開きます。

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

例: 

mspbi://app/OpenReport?ReportObjectId = 500217de-50f0-4af1-b345-b81027224033 & openFullScreen = true

## <a name="add-context-optional"></a>コンテキストを追加する (省略可能)
文字列にコンテキストを追加することもできます。 Microsoft へお問い合わせになる場合は、Microsoft はそのコンテキストを使用して、お客様のアプリへのデータをフィルター処理することができます。 リンクに `&context=<app-name>` を追加する

たとえば、次の URL の強調表示された部分を見てください。 

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/&context=SlackDeepLink`

## <a name="next-steps"></a>次の手順
Power BI モバイル アプリで使用したいその他の機能にぜひ投票してください。お客様からのフィードバックは、将来実装する機能を決めるのに役立ちます。 

* [モバイル デバイス用の Power BI アプリ](mobile-apps-for-mobile-devices.md)
* Twitter で @MSPowerBI をフォローする
* [Power BI コミュニティの会話](http://community.powerbi.com/)に参加する
* [Power BI とは?](power-bi-overview.md)

