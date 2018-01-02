---
title: "Power BI Report Server の変更ログ"
description: "この変更ログは Power BI Report Server 用です。リリースされた各ビルドの新しい項目とバグの修正が一覧表示されます。"
services: powerbi
documentationcenter: 
author: jtarquino
manager: jonhp
backup: maggies
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/11/2017
ms.author: tankas
ms.openlocfilehash: ced415662c2dc39b6491cb79d121f3cd77719fe4
ms.sourcegitcommit: be55922d7f43f458aea0160ec8fdfb1a0b5a0c00
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2017
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI Report Server の変更ログ

この変更ログは Power BI Report Server 用です。リリースされた各ビルドの新しい項目とバグの修正が一覧表示されます。

新機能の詳細については、「[Power BI レポート サーバーの新機能](whats-new.md)」を参照してください。

## <a name="october-2017"></a>2017 年 10 月

- **Power BI Report Server**
    - *バージョン 1.1.6551.5155 (ビルド 14.0.600.438)、リリース日: 2017 年 12 月 11 日*
        - バグの修正
            - 特定の Power BI Desktop レポートの更新後のデータの保存に失敗しました。

    - *バージョン 1.1.6530.30789 (ビルド 14.0.600.437)、リリース日: 2017 年 11 月 17 日*
        - バグの修正
            - 基本認証シナリオの修正 
            - ポータルのサブスクリプション、キャッシュ更新計画、履歴スナップショットのスケジュール ページで平日が選択できなかった問題の修正
            - ページ分割されたレポート (RDL) で、テキストボックスに CanGrow プロパティが false に設定された式を含めると、値に色とフォントが正しく表示されない問題の修正
            - Power BI レポート (PBIX) で、凡例を折れ線グラフに追加すると空のビジュアルが描画される問題の修正

    - *バージョン 1.1.6514.9163 (ビルド 14.0.600.434)、リリース日: 2017 年 11 月 1 日*
        - バグの修正
            - 500 MB を超える PBIX レポートをアップロードする場合の信頼性の問題の修正
            - 1 GB を超える PBIX レポートのデータの読み込みに関する問題の修正

    - *バージョン 1.1.6513.3500 (ビルド 14.0.600.433)、リリース日: 2017 年 10 月 31 日*
        - 機能
            - 埋め込みデータ モデルのサポート
            - Excel ブックの表示 (Office Online Server の統合が有効になっている場合)
            - スケジュールされたデータ更新 (PBIX)
            - 直接クエリのサポート
            - 大きいファイルのサポート (最大 2 GB)
            - パブリック REST API
            - Power BI Desktop での共有データセットのサポート (oData を使用)
            - PBIX ファイルの URL パラメーターのサポート
            - アクセシビリティの機能強化

- **Power BI Desktop (Power BI Report Server 用に最適化)**
    - *バージョン: 2.51.4885.1423 (2017 年 10 月)、リリース: 2017 年 10 月 17 日*
        - バグの修正
            - 32 ビットの Power BI Desktop が x86 OS での実行に失敗する問題の修正
            - Power BI レポート (PBIX) での X 軸のグリッド線表示の修正
            - その他の軽微なバグの修正

    - *バージョン: 2.51.4885.1041 (2017 年 10 月)、リリース: 2017 年 10 月 31 日*
        - 機能
            - Power BI Report Server (2017 年 10 月) との接続に必要な変更が含まれます

## <a name="june-2017"></a>2017 年 6 月

- **Power BI Report Server**
    - *ビルド 14.0.600.305、リリース日: 2017 年 9 月 19 日*  
        - バグの修正
            - 最新の[Bing Maps Web コントロール](https://msdn.microsoft.com/library/mt712542.aspx)に更新

    - *ビルド 14.0.600.301、リリース日: 2017 年 7 月 11 日*
        - バグの修正
            - {{UserId}} タグが、Power BI レポートでレポートを実行しているユーザーではなく、保存されている資格情報に解決されます
            - 一部の画像を Power BI レポート サーバー レポートでレンダリングできません
            - Power BI レポート サーバーで Power BI レポートの名前を変更できません
            - Power BI モバイル アプリケーションでカスタム ビジュアルを読み込むことができません (モバイル アプリを再インストールしてローカル キャッシュをクリアする必要があります)

    - *ビルド 14.0.600.271、リリース日: 2017 年 6 月 12 日*
        - Power BI レポート サーバーの初回リリース

## <a name="next-steps"></a>次の手順

[ユーザー向けハンドブック](user-handbook-overview.md)  
[管理者向けハンドブック](admin-handbook-overview.md)  
[クイックスタート: Power BI レポート サーバーをインストールする](quickstart-install-report-server.md)  
[レポート ビルダーをインストールする](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[SQL Server Data Tools (SSDT) のダウンロード](http://go.microsoft.com/fwlink/?LinkID=616714)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。