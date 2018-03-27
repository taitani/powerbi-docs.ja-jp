---
title: Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール
description: Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール方法の詳細
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/19/2018
ms.author: maggies
ms.openlocfilehash: 9951137ac10752a39f0e4ad555a36e2935faf327
ms.sourcegitcommit: 93e7362fc47319959b6992dfd037effdf831d010
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2018
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール
Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール方法について説明します。

Power BI Report Server の Power BI レポートを作成するには、Power BI Report Server 向けに最適化された Power BI Desktop をダウンロードしてインストールする必要があります。 このリリースは、Power BI サービスで使用される Power BI Desktop とは別のものです。 たとえば、Power BI サービス用の Power BI Desktop のバージョンには、リリース後まで Power BI Report Server のバージョンでは使用できないプレビュー機能が含まれています。 このリリースを使用すると、レポート サーバーが、既知のバージョンのレポートおよびモデルと対話できることを確認できます。 

Power BI Desktop と、Power BI Report Server 向けに最適化された Power BI Desktop は、同じコンピューターにサイド バイ サイドでインストールできます。

## <a name="download-and-install-power-bi-desktop"></a>Power BI Desktop のダウンロードおよびインストール

Power BI Report Server 向けに最適化された Power BI Desktop のバージョンが最新のものであることを確認するための最も簡単な方法は、レポート サーバーの Web ポータルから起動することです。

1. レポート サーバーの Web ポータルで、**ダウンロード**の矢印、**[Power BI Desktop]** の順に選択します。

    ![Web ポータルから Power BI Desktop をダウンロードする](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Microsoft ダウンロード センターの (Power BI Report Server (2018 年 3 月) 向けに最適化された) [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) に直接移動することもできます。

2. ダウンロード センター ページで、**[ダウンロード]** を選択します。

3. 使用しているコンピューターに適したものを以下から選択します。 

    - **PBIDesktopRS.msi** (32 ビット バージョン)

    - **PBIDesktopRS_x64.msi** (64 ビット バージョン)

1. インストーラーをダウンロードしたら、Power BI Desktop (2017 年 10 月) のセットアップ ウィザードを実行します。
2. インストールの最後に、**[Start Power BI Desktop now]**\(今すぐ Power BI Desktop を起動する\) をオンにします。
   
    Power BI Desktop が自動的に起動し、すぐに使えます。

## <a name="verify-you-are-using-the-correct-version"></a>正しいバージョンを使用していることを確認する
Power BI Desktop の起動画面またはタイトル バーを見て、正しい Power BI Desktop を使用していることを確認できます。 タイトル バーには、リリースの月と年が示されます。

![Power BI Report Server 向けに最適化された Power BI Desktop のタイトル バー](media/quickstart-create-powerbi-report/report-server-desktop-october-2017-version.png)

Power BI サービスの Power BI Desktop バージョンの場合、タイトル バーに月と年は示されません。

## <a name="file-extension-association"></a>ファイル拡張子の関連付け
Power BI Desktop と Power BI レポート サーバー向けに最適化された Power BI Desktop を同じコンピューターにインストールした場合、最後にインストールした Power BI Desktop が .pbix ファイルと関連付けられます。 これは、pbix ファイルをダブルクリックすると、最後にインストールした Power BI Desktop が起動されることを意味します。

Power BI Desktop をインストールし、次に Power BI レポート サーバー向けに最適化された Power BI Desktop をインストールした場合、すべての pbix ファイルが既定で Power BI レポート サーバー向けに最適化された Power BI Desktop で開かれます。 pbix ファイルを開く際に既定で Power BI Desktop を起動する場合は、Power BI サービスから Power BI Desktop を再インストールします。

最初に使用したい Power BI Desktop のバージョンを常に開くことができます。 その後、Power BI Desktop からファイルを開きます。

Power BI レポート サーバー内で Power BI レポートを編集したり、Web ポータルから新しい Power BI レポートを作成すると、適切なバージョンの Power BI Destop が常に開きます。

## <a name="considerations-and-limitations"></a>考慮事項と制限事項
Power BI Report Server と Power BI サービス (http://powerbi.com)) のレポートは、ほぼ同じように機能しますが、いくつかの機能は異なります。

### <a name="in-a-browser"></a>ブラウザー
Power BI レポート サーバーのレポートは、次を含むすべての視覚エフェクトをサポートします。

* カスタム ビジュアル

Power BI レポート サーバーのレポートは、次をサポートしません。

* R ビジュアル
* ArcGIS マップ
* 階層リンク
* Power BI Desktop のプレビュー機能

### <a name="in-the-power-bi-mobile-apps"></a>Power BI モバイル アプリ
Power BI レポート サーバーのレポートは、次を含む [Power BI モバイル アプリ](../mobile-apps-for-mobile-devices.md)のすべての基本機能をサポートします。

* [電話のレポート レイアウト](../desktop-create-phone-report.md): Power BI モバイル アプリのレポートを最適化することができます。 携帯電話では、最適化されたレポートに特別なアイコン![電話レポート レイアウト アイコン](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-icon.png)、およびレイアウトが提供されます。
  
    ![電話用に最適化されたレポート](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-report.png)

Power BI レポート サーバーのレポートは、Power BI モバイル アプリの次の機能をサポートしません。

* R ビジュアル
* ArcGIS マップ
* カスタム ビジュアル
* 階層リンク
* 場所フィルターまたはバー コード

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>以前のバージョンの Power BI Report Server の Power BI Desktop

ご利用のレポート サーバーが以前のバージョンである場合、対応するバージョンの Power BI Desktop が必要です。 以前の 2 つのバージョンを以下に示します。

- Microsoft Power BI Desktop ([Power BI Report Server (2017 年 10 月) 向けに最適化](https://www.microsoft.com/download/details.aspx?id=56136))
- Microsoft Power BI Desktop ([Power BI Report Server (2017 年 6 月) 向けに最適化](https://www.microsoft.com/download/details.aspx?id=55330))

## <a name="next-steps"></a>次の手順
Power BI Desktop をインストールしたので、Power BI レポートの作成を開始できます。

[クイックスタート: Power BI レポート サーバーの Power BI レポートの作成](quickstart-create-powerbi-report.md)  
[Power BI Desktop の概要](../desktop-getting-started.md)  
ガイド付き学習: [Power BI Desktop の概要](../guided-learning/gettingdata.yml#step-2)  
[ユーザー ハンドブックの概要、Power BI レポート サーバー](user-handbook-overview.md)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。

