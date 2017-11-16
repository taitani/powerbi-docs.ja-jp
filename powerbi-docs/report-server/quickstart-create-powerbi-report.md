---
title: "クイックスタート: Power BI レポート サーバーの Power BI レポートの作成"
description: "Power BI レポート サーバーの Power BI レポートをいくつかの簡単な手順で作成する方法について説明します。"
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: maggies
ms.openlocfilehash: e492d31a8e1ed57a769c9a36f515d99369f6d6dc
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="quickstart-create-a-power-bi-report-for-power-bi-report-server"></a>クイックスタート: Power BI レポート サーバーの Power BI レポートの作成
Power BI レポートは、Power BI サービス (https://powerbi.com) のクラウドに保存することができるほか、Power BI Report Server の Web ポータルでも Power BI レポートをオンプレミスで保存して管理できます。 Power BI Desktop でレポートを作成および編集することができ、レポートを Web ポータルに公開することもできます。 その後、組織内のレポート閲覧者が、ブラウザーや、モバイル デバイスの Power BI モバイル アプリでレポートを表示できるようになります。

![Web ポータル上の Power BI レポート](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

Power BI Desktop で Power BI レポートを既に作成している場合は、Power BI レポート サーバーの Power BI レポートを作成する準備ができています。 そうでない場合は、始めるために次の 4 つの簡単な手順を実行します。

## <a name="step-1-install-power-bi-desktop-report-server"></a>手順 1: Power BI Desktop をインストールする (Report Server)
Power BI サービスのレポートを作成するために Power BI Desktop を既にインストールしている場合があります。 サーバーとアプリを常に同期させるため、Power BI レポート サーバー向けに最適化された Power BI Desktop のバージョンをインストールすることをお勧めします。同じコンピューターに Power BI Desktop の両方のバージョンを共存させることができます。

1. Power BI Report Server の Web ポータルで **[新規]** > **[Power BI Report]\(Power BI レポート\)** の順に選択します。
   
    ![新規の Power BI レポート](media/quickstart-create-powerbi-report/report-server-web-portal-new-powerbi-report.png)
   
    Power BI Report Server へのアクセスがない場合は、Microsoft ダウンロード センターにアクセスし、[Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=837581) (Power BI Report Server 向けに最適化 - 2017 年 6 月 GA) をダウンロードします。
2. インストール プロセスの最後に、**[Start Power BI Desktop now]**\(今すぐ Power BI Desktop を起動始する\) をオンにします。
   
    Power BI Desktop が自動的に起動し、すぐに使えます。 適切なバージョンでは、タイトル バーに "Power BI Desktop (Report Server)" と表示されます。
3. Power BI Desktop に慣れていない場合は、[ようこそ] 画面のビデオをご覧になることをお勧めします。
   
    ![Power BI Desktop のスタート画面](media/quickstart-create-powerbi-report/report-server-powerbi-desktop-start.png)

## <a name="step-2-select-a-data-source"></a>手順 2: データ ソースを選択する
広範なデータ ソースに接続することができます。 データ ソースへの接続の詳細については、[こちら](connect-data-sources.md)をご覧ください。

1. [ようこそ] 画面で、**[データの取得]** を選択します。
   
    または **[ホーム]** タブで **[データの取得]** を選択します。
2. データ ソースを選びます (この例では **Analysis Services**)。
   
    ![データ ソースの選択](media/quickstart-create-powerbi-report/report-server-get-data-ssas.png)
3. **[サーバー]** を入力し、必要に応じて **[データベース]** も入力します。 **[ライブ接続]** が選択されていることを確認し、**[OK]** をクリックします。
   
    ![サーバー名](media/quickstart-create-powerbi-report/report-server-ssas-server-name.png)
4. レポートを保存するレポート サーバーを選択します。
   
    ![レポート サーバーの選択](media/quickstart-create-powerbi-report/report-server-select-server.png)

## <a name="step-3-design-your-report"></a>手順 3: レポートをデザインする
これは楽しい作業です。データを表示するビジュアルを作成します。

たとえば、年収による顧客とグループの値のじょうごグラフを作成できます。

![レポートのデザイン](media/quickstart-create-powerbi-report/report-server-create-funnel.png)

1. **[視覚エフェクト]** で **[じょうごグラフ]** を選択します。
2. カウントするフィールドを **[値]** にドラッグします。 それが数値フィールドでない場合、Power BI Desktop はそれを自動的に値の*カウント*にします。
3. フィールドを **[グループ]** のグループにドラッグします。

詳細については、[Power BI レポートのデザイン](../desktop-report-view.md)に関する記事を参照してください。

## <a name="step-4-save-your-report-to-the-report-server"></a>手順 4: レポート サーバーにレポートを保存する
レポートの準備ができたら、それを手順 2 で選択した Power BI Report Server に保存します。

1. **[ファイル]** メニューで、**[名前を付けて保存]** > **[Power BI レポート サーバー]** を選択します。
   
    ![レポート サーバーに保存](media/quickstart-create-powerbi-report/report-server-save-as-powerbi-report-server.png)
2. これで、レポートを Web ポータルで表示できます。
   
    ![Web ポータルで Power BI レポートを表示](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

## <a name="considerations-and-limitations"></a>考慮事項と制限事項
Power BI レポート サーバーと Power BI サービス (http://powerbi.com) のレポートは、ほぼ同じように機能しますが、いくつかの機能は異なります。

### <a name="in-a-browser"></a>ブラウザー
Power BI レポート サーバーのレポートは、次を含むすべての視覚エフェクトをサポートします。

* カスタム ビジュアル

Power BI レポート サーバーのレポートは、次をサポートしません。

* R ビジュアル
* ArcGIS マップ
* 階層リンク

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

## <a name="next-steps"></a>次の手順
### <a name="power-bi-desktop"></a>Power BI Desktop
Power BI Desktop でのレポートを作成するために役立つ多くの優れたリソースがあります。 次のリンクは、開始点として最適です。

* [Power BI Desktop の概要](../desktop-getting-started.md)
* ガイド付き学習: [Power BI Desktop の概要](../guided-learning/gettingdata.yml#step-2)

### <a name="power-bi-report-server"></a>Power BI Report Server
* [Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール](install-powerbi-desktop.md)  
* [Power BI レポート サーバーのユーザー ハンドブック](user-handbook-overview.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。