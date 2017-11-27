---
title: "Power BI でのカスタム ビジュアル"
description: "Power BI でのカスタム ビジュアル"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 11/20/2017
ms.author: mihart
ms.openlocfilehash: c50b984cd8babc845dbe0223613e463a7a8ee76d
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="custom-visuals-in-power-bi"></a>Power BI でのカスタム ビジュアル
Power BI レポートを作成または編集するときには、さまざまな種類のビジュアルを使用できます。 このようなビジュアルは **[視覚化]** ウィンドウに表示されます。 Power BI Desktop をダウンロードしたり、Power BI サービス (app.powerbi.com) を開いたりすると、このビジュアルのセットが "事前にパッケージ化" されます。 

![](media/power-bi-custom-visuals/power-bi-visualizations.png)

ただし、このビジュアルのセットに制限されるわけではなく、省略記号を選択すると、別のレポート ビジュアルのソース (*カスタム ビジュアル*) が表示されます。

カスタム ビジュアルは、コミュニティのメンバーと Microsoft によって作成されたもので、[AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) でホストされています。 このようなビジュアルはダウンロードして、Power BI レポートに追加することができます。 Microsoft によって承認されたすべてのこれらのカスタム ビジュアルは、Power BI に含まれている事前にパッケージ化された視覚エフェクトと同様に動作し、フィルター処理、強調表示、編集、共有などを行うことができます。 

AppSource とは 簡単に言えば、Microsoft のソフトウェアのアプリ、アドイン、拡張機能を検索できる場所です。 [AppSource](https://appsource.microsoft.com) は、Office 365、Azure、Dynamics 365、Cortana、Power BI などの製品の何百万人もの Office 365 ユーザーを、これまでより効率よく、より洞察的で美しい仕事をするのに役立つソリューションに結び付けます。

## <a name="two-types-of-custom-visuals"></a>カスタム ビジュアルの 2 つの種類

AppSource から入手できる Power BI のカスタム ビジュアルは、**承認済み**と**認定済み**の 2 つのカテゴリに分類されます。 *AppSource 承認済み*ビジュアルは、ブラウザー、レポート、ダッシュボードで実行することができます。  *Power BI 認定済み*ビジュアルは、厳格なテストに合格し、[電子メール サブスクリプション](service-report-subscribe.md)や [PowerPoint へのエクスポート](service-publish-to-powerpoint.md)などの追加のシナリオに対応しています。

認定済みカスタム ビジュアルの一覧の表示またはカスタム ビジュアルの申請については、「[Certified custom visuals](power-bi-custom-visuals-certified.md)」 (認定済みカスタム ビジュアル) をご覧ください。

独自の視覚エフェクトを作成して AppSource に追加することに興味がある Web 開発者の方は、  「[開発者ツールの概要](service-custom-visuals-getting-started-with-developer-tools.md)」を参照し、[AppSource にカスタム ビジュアルを公開する](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)方法を学習してください。

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource からカスタム ビジュアルをダウンロードまたはインポートする
カスタム ビジュアルをダウンロードおよびインポートする場合、Power BI と AppSource Web サイトの 2 つのオプションを使用できます。 

###    <a name="import-custom-visuals-from-within-power-bi"></a>Power BI からカスタム ビジュアルをインポートする
1. [視覚化] ウィンドウの下部にある省略記号を選択します。 

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. ドロップダウンで **[ストアからインポート]** を選択します。

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-import.png)

3. 一覧をスクロールして、インポートするビジュアルを探します。 

    ![](media/power-bi-custom-visuals/power-bi-import-visual.png)

4.  各ビジュアルの詳細を確認するには、ビジュアルを強調表示して選択します。

    ![](media/power-bi-custom-visuals/power-bi-select.png)

5.  詳細ページでは、スクリーンショット、ビデオ、詳細な説明、その他を見ることができます。 

    ![](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. レビューを表示するには最下部までスクロールします。

    ![](media/power-bi-custom-visuals/power-bi-reviews.png)

7.    **[追加]** を選択して、カスタム ビジュアルをインポートします。 カスタム ビジュアルのアイコンが [視覚化] ウィンドウの下部に追加され、レポートで使用できるようになりました。

       ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)


###    <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource からカスタム ビジュアルをダウンロードおよびインポートする

1. [Microsoft AppSource](https://appsource.microsoft.com) から、**[アプリ]** のタブを選択します。 

    ![](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. このタブから[アプリの結果ページ](https://appsource.microsoft.com/en-us/marketplace/apps)に移動し、*[Power BI apps]* を含めた各カテゴリの上位アプリを確認できます。 今はカスタム ビジュアルを検索しているので、左側のナビゲーション リストから **[Power BI visuals]** を選択して結果を絞り込みます。

    ![](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource に、各カスタム ビジュアルのタイルが表示されます。  各タイルにはカスタム ビジュアルのスナップショットが含まれ、簡単な説明と、ダウンロードのリンクがあります。 詳細を表示するには、タイルを選択します。 

    ![](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. 詳細ページでは、スクリーンショット、ビデオ、詳細な説明、その他を見ることができます。 **[今すぐ入手する]** を選択し、使用条件に同意して、カスタム ビジュアルをダウンロードします。 

    ![](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. カスタム ビジュアルをダウンロードするリンクを選択します。

    ![](media/power-bi-custom-visuals/powerbi-custom-download.png)

    ダウンロードのページには、Power BI Desktop と Power BI サービスにカスタム ビジュアルをインポートする方法についての説明もあります。

    カスタム ビジュアルが含まれ、その機能を見ることができる、サンプル レポートをダウンロードすることもできます。

    ![](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. .pbiviz ファイルを保存し、Power BI を開きます。    
7. カスタム ビジュアルを追加するレポートを開き、**[視覚化]** ウィンドウの下部で省略記号を選択して、**[ファイルからインポートする]** を選択します。  

      ![](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

8. カスタム ビジュアルのファイルを選択してそのカスタム ビジュアルのアイコンを **[視覚化]** ウィンドウの下部に追加します。 これで、カスタム ビジュアルがレポートで使用できるようになりました。

    ![](media/power-bi-custom-visuals/power-bi-chord.png)
    
##    <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング


- カスタム ビジュアルをインポートすると、特定のレポートに追加されます。 ビジュアルを別のレポートで使用する場合は、そのレポートにもインポートする必要があります。 カスタム ビジュアルを含むレポートを **[名前を付けて保存]** オプションで保存すると、カスタム ビジュアルのコピーが新しいレポートと共に保存されます。

- **[視覚化]** ウィンドウが表示されない場合、レポートを編集するアクセス許可がないことを意味します。  カスタム ビジュアルは編集できるレポートにのみ追加でき、共有されているレポートには追加できません。


他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

