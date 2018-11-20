---
title: Power BI Report Server と Power BI サービスの比較
description: この記事では、Power BI Report Server と Power BI サービスの機能を比較します。
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 11/06/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: a693eef85f7eafe7cfac2a02cbccc346201a6f13
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507694"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Power BI Report Server と Power BI サービスの比較

Power BI Report Server と Power BI サービスには、多くの類似点と重要な相違点があります。 次の表で、これらについて説明します。

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Power BI Report Server と Power BI サービスの機能

| 機能 | Power BI Report Server | Power BI サービス | 注
|---------|---------|---------|---------|
| デプロイ | オンプレミスまたはクラウドでホスト | クラウド | Power BI Report Server は、Power BI Premium を通じてライセンス供与された場合は、Azure VM にデプロイできます (クラウドでホストされます)
| ソース データ | クラウドとオンプレミスの両方またはいずれか | クラウドとオンプレミスの両方またはいずれか |  
| ライセンス | Power BI Premium または SA 付きの SQL Server EE | Power BI Pro と Power BI Premium の両方またはいずれか |  
| ライフサイクル | 最新のライフサイクル ポリシー | フル マネージドのサービス |  
| リリース サイクル | 4 か月ごと | 月に 1 回 | 最新の機能と修正プログラムは、Power BI サービスに先に提供されます。 ほとんどのコア機能は、数回後のリリースで Power BI Report Server に提供されます。一部の機能は Power BI サービスのみが対象です。
| Power BI Desktop での Power BI レポートの作成 | はい | はい |  
| ブラウザーでの Power BI レポートの作成 | いいえ | はい |  
| ゲートウェイが必要 | いいえ | オンプレミス データ ソースでは必要 |  
| リアルタイム ストリーミング | いいえ | はい | [Power BI のリアルタイム ストリーミング](../service-real-time-streaming.md)
| ダッシュボード | いいえ | はい | [Power BI サービスのダッシュボード](../consumer/end-user-dashboards.md) 
| アプリを使用した一群のレポートの配布 | いいえ | はい | [Power BI でダッシュボードとレポートを含むアプリを作成して発行する](../service-create-distribute-apps.md) 
| コンテンツ パック | いいえ | はい | [組織のコンテンツ パック: 概要](../service-organizational-content-pack-introduction.md) 
| Salesforce などのサービスへの接続 | いいえ | はい | Power BI サービスで[使用するサービスに接続する](../consumer/end-user-connect-to-services.md)
| Q&A | いいえ | はい | [Power BI サービスと Power BI Desktop の Q&A](../consumer/end-user-q-and-a.md) 
| クイック分析情報 | いいえ | はい | [Power BI を使用してデータ インサイトを自動的に生成する](../consumer/end-user-insights.md) 
| Excel で分析 | いいえ | はい | [Excel で分析](../service-analyze-in-excel.md) 
| ページ分割されたレポート | はい | はい | [Power BI サービスでページ分割されたレポートを使用する](../paginated-reports-report-builder-power-bi.md) (プレビュー)
| Power BI モバイル アプリ | はい | はい | [Power BI モバイル アプリの概要](../consumer/mobile/mobile-apps-for-mobile-devices.md) 
| ArcGIS マップ | いいえ | はい | [Esri が提供する Power BI サービスおよび Power BI Desktop の ArcGIS マップ](../power-bi-visualization-arcgis.md)
| Power BI レポートの電子メールのサブスクリプション | いいえ | はい | Power BI サービスで[レポートまたはダッシュボードをサブスクライブする](../consumer/end-user-subscribe.md) 
| ページ分割されたレポートの電子メールのサブスクリプション | はい | いいえ | [Reporting Services での電子メール配信](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| データ アラート | いいえ | はい | Power BI サービスで[データ アラート](../service-set-data-alerts.md)を設定する
| 行レベルのセキュリティ | DirectQuery モードのデータ ソースを通してのみ | DirectQuery (データ ソース) とインポート モードの両方で利用可能 | Power BI での[行レベルのセキュリティ (RLS)](../service-admin-rls.md) 
| 全画面表示モード | いいえ | はい | Power BI サービスの[全画面表示モード](../consumer/end-user-focus.md) 
| Office 365 の高度な共同作業 | いいえ | はい | Office 365 を使用した[アプリ ワークスペースでの共同作業](../service-collaborate-power-bi-workspace.md) 
| R ビジュアル | いいえ | はい | Power BI サービスで [R ビジュアルを作成する](../visuals/service-r-visuals.md)  
| プレビュー機能 | いいえ | はい | [Power BI サービスのプレビュー機能のオプトイン](../consumer/end-user-preview-features.md) 
| カスタム ビジュアル | はい | はい | [Power BI でのカスタム ビジュアル](../power-bi-custom-visuals.md) 
| Power BI Desktop | Report Server 用に最適化されたバージョン。Report Server と一緒にダウンロード可能 | Power BI サービス用に最適化されたバージョン。Windows ストアから入手可能 | [Report Server 用の Power BI Desktop](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI サービス用の Power BI Desktop](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>次の手順
[Power BI レポート サーバーのインストール](install-report-server.md)  



