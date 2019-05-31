---
title: Power BI Report Server の Power BI レポートの作成
description: Power BI レポート サーバーの Power BI レポートをいくつかの簡単な手順で作成する方法について説明します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: maggies
ms.openlocfilehash: 2401064f1f7f3be63c23d72e79987784e1ec7049
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187500"
---
# <a name="create-a-power-bi-report-for-power-bi-report-server"></a>Power BI Report Server の Power BI レポートの作成
Power BI サービス (https://powerbi.com)) のクラウドで Power BI レポートを格納する場合と同じように、Power BI Report Server の Web ポータルでも Power BI レポートをオンプレミスで格納して管理することができます。 Power BI Desktop でレポートを作成および編集することができ、レポートを Web ポータルに公開することもできます。 その後、組織内のレポート閲覧者が、ブラウザーや、モバイル デバイスの Power BI モバイル アプリでレポートを表示できるようになります。

![Web ポータル上の Power BI レポート](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

作業を開始するには、次の 4 つの簡単な手順を実行します。

## <a name="step-1-install-power-bi-desktop-optimized-for-power-bi-report-server"></a>手順 1:Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール

Power BI Desktop で Power BI レポートを既に作成している場合は、Power BI Report Server の Power BI レポートを作成する準備がほぼできています。 サーバーとアプリを常に同期させるため、Power BI レポート サーバー向けに最適化された Power BI Desktop のバージョンをインストールすることをお勧めします。同じコンピューターに Power BI Desktop の両方のバージョンを共存させることができます。

1. レポート サーバーの Web ポータルで、**ダウンロード**の矢印、 **[Power BI Desktop]** の順に選択します。

    ![Web ポータルから Power BI Desktop をダウンロードする](media/quickstart-create-powerbi-report/report-server-download-web-portal.png)

    直接移動または[Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) (最適化の Power BI Report Server - 月 2019年)、Microsoft ダウンロード センター。

2. ダウンロード センター ページで、 **[ダウンロード]** を選択します。

3. 使用しているコンピューターに適したものを以下から選択します。

    - **PBIDesktopRS.msi** (32 ビット バージョン)

    - **PBIDesktopRS_x64.msi** (64 ビット バージョン)

4. インストーラーをダウンロードした後は、Power BI Desktop (月 2019) セットアップ ウィザードを実行します。

2. インストールの最後に、 **[Start Power BI Desktop now]** \(今すぐ Power BI Desktop を起動する\) をオンにします。
   
    Power BI Desktop が自動的に起動し、すぐに使えます。 "Power BI Desktop (月 2019)"がタイトル バーのために、適切なバージョンを作成するを指定できます。

    ![Power BI Desktop が 2019年バージョン](media/quickstart-create-powerbi-report/power-bi-report-server-desktop-may-2019.png)

3. Power BI Desktop に慣れていない場合は、[ようこそ] 画面のビデオをご覧になることをお勧めします。
   
    ![Power BI Desktop のスタート画面](media/quickstart-create-powerbi-report/report-server-powerbi-desktop-start.png)

## <a name="step-2-select-a-data-source"></a>手順 2:データ ソースを選択する
広範なデータ ソースに接続することができます。 データ ソースへの接続の詳細については、[こちら](connect-data-sources.md)をご覧ください。

1. [ようこそ] 画面で、 **[データの取得]** を選択します。
   
    または **[ホーム]** タブで **[データの取得]** を選択します。
2. データ ソースを選びます (この例では **Analysis Services**)。
   
    ![データ ソースの選択](media/quickstart-create-powerbi-report/report-server-get-data-ssas.png)
3. **[サーバー]** を入力し、必要に応じて **[データベース]** も入力します。 **[ライブ接続]** が選択されていることを確認し、 **[OK]** をクリックします。
   
    ![サーバー名](media/quickstart-create-powerbi-report/report-server-ssas-server-name.png)
4. レポートを保存するレポート サーバーを選択します。
   
    ![レポート サーバーの選択](media/quickstart-create-powerbi-report/report-server-select-server.png)

## <a name="step-3-design-your-report"></a>手順 3:レポートをデザインする
これは楽しい作業です。データを表示するビジュアルを作成します。

たとえば、年収による顧客とグループの値のじょうごグラフを作成できます。

![レポートのデザイン](media/quickstart-create-powerbi-report/report-server-create-funnel.png)

1. **[視覚エフェクト]** で **[じょうごグラフ]** を選択します。
2. カウントするフィールドを **[値]** にドラッグします。 それが数値フィールドでない場合、Power BI Desktop はそれを自動的に値の*カウント*にします。
3. フィールドを **[グループ]** のグループにドラッグします。

詳細については、[Power BI レポートのデザイン](../desktop-report-view.md)に関する記事を参照してください。

## <a name="step-4-save-your-report-to-the-report-server"></a>手順 4:レポート サーバーにレポートを保存する
レポートの準備ができたら、それを手順 2 で選択した Power BI Report Server に保存します。

1. **[ファイル]** メニューで、 **[名前を付けて保存]**  >  **[Power BI レポート サーバー]** を選択します。
   
    ![レポート サーバーに保存](media/quickstart-create-powerbi-report/report-server-save-as-powerbi-report-server.png)
2. これで、レポートを Web ポータルで表示できます。
   
    ![Web ポータルで Power BI レポートを表示](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

## <a name="next-steps"></a>次の手順
### <a name="power-bi-desktop"></a>Power BI Desktop
Power BI Desktop でのレポートを作成するために役立つ多くの優れたリソースがあります。 このリンクを出発点にすることをお勧めします。

* [Power BI Desktop の概要](../desktop-getting-started.md)
* ガイド付き学習:[Power BI Desktop の概要](../guided-learning/gettingdata.yml?tutorial-step=2)

### <a name="power-bi-report-server"></a>Power BI Report Server
* [Power BI レポート サーバー向けに最適化された Power BI Desktop のインストール](install-powerbi-desktop.md)  
* [Power BI Report Server とは](get-started.md)  

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](https://community.powerbi.com/)。
