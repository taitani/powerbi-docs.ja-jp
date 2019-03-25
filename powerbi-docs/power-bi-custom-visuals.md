---
title: Power BI でのカスタム ビジュアル
description: Power BI でのカスタム ビジュアル
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/18/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: ed61d865756748ccd4e60f54de4a4b1b9adcef8d
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "57980337"
---
# <a name="custom-visuals-in-power-bi"></a>Power BI でのカスタム ビジュアル

Power BI レポートを作成または編集するときには、さまざまな種類のビジュアルを使用できます。 このようなビジュアルは **[視覚化]** ウィンドウに表示されます。 [Power BI Desktop](https://powerbi.microsoft.com/desktop/) をダウンロードしたり、[Power BI サービス](https://app.powerbi.com)を開いたりすると、このビジュアルのセットが "事前にパッケージ化" されます。

![視覚化](media/power-bi-custom-visuals/power-bi-visualizations.png)

ただし、このビジュアルのセットに制限されるわけではなく、省略記号を選択すると、別のレポート ビジュアルのソース (*カスタム ビジュアル*) が表示されます。

カスタム ビジュアルは開発者がカスタム ビジュアル SDK を利用して作成します。ビジネス ユーザーにとって、そのビジネスに最適な形式でデータが表示されるようにするのがその目的です。 作成後、レポート作成者はカスタム ビジュアル ファイルを自分のレポートにインポートし、他の Power BI ビジュアルと同様に利用できます。 カスタム ビジュアルは Power BI で最も重要視されており、フィルター処理、強調表示、編集、共有などの操作が可能になっています。

カスタム ビジュアルの展開チャネルには 3 つの形式があります。

* カスタム ビジュアル ファイル
* 組織のビジュアル
* Marketplace ビジュアル

## <a name="custom-visual-files"></a>カスタム ビジュアル ファイル

カスタム ビジュアルはパッケージであり、特定の目的を果たすデータをレンダリングするためのコードが含まれています。 カスタム ビジュアルは誰でも作成し、単一の `.pbiviz` ファイルとしてパッケージ化できます。このファイルは Power BI レポートにインポートできます。

> [!WARNING]
> カスタム ビジュアルには、セキュリティやプライバシー上のリスクを伴うコードが含まれている可能性があります。レポートにインポートする前に、カスタム ビジュアルの作成者とソースが信頼できることを確認してください。

## <a name="organizational-visuals"></a>組織のビジュアル

Power BI 管理者はカスタム ビジュアルを組織に展開できるので、管理者が組織内での使用を認めたカスタム ビジュアルをレポート作成者が簡単に見つけて、使用することができます。 管理者は組織内で展開するカスタム ビジュアルを選択できるようになります。また、ビジュアルの管理 (バージョン更新、無効化/有効化など) が簡単になります。 レポート作成者にとっては、組織に特有のビジュアルを簡単に見つけることができます。また、ビジュアルの更新がシームレスにサポートされます。

組織のカスタム ビジュアルについては、[詳細](power-bi-custom-visuals-organization.md)ページをご覧ください。

## <a name="marketplace-visuals"></a>Marketplace ビジュアル

コミュニティのメンバーと Microsoft はカスタム ビジュアルを公共の利益のために提供しており、[AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) マーケットプレースに公開しています。 このようなビジュアルはダウンロードして、Power BI レポートに追加することができます。 このようなカスタム ビジュアルはすべて、Microsoft が機能と品質をテストし、承認しています。

[AppSource](developer/office-store.md) とは つまり、Microsoft のソフトウェアのアプリ、アドイン、拡張機能を検索できる場所です。 [AppSource](https://appsource.microsoft.com/) は、Office 365、Azure、Dynamics 365、Cortana、Power BI などの製品の何百万人もの Office 365 ユーザーを、これまでより効率よく、より洞察的で美しい仕事をするのに役立つソリューションに結び付けます。

### <a name="certified-visuals"></a>認定済みビジュアル

Power BI 認定済みビジュアルは品質に関する厳格な追加テストに合格したマーケットプレース ビジュアルであり、[電子メール サブスクリプション](https://docs.microsoft.com/power-bi/service-report-subscribe)や [PowerPoint へのエクスポート](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint)などの追加のシナリオに対応しています。
認定済みカスタム ビジュアルの一覧の表示またはカスタム ビジュアルの申請については、「[Certified custom visuals](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified)」 (認定済みカスタム ビジュアル) をご覧ください。

独自の視覚エフェクトを作成して AppSource に追加することに興味がある Web 開発者の方は、 「[Power BI カスタム ビジュアルの開発](developer/custom-visual-develop-tutorial.md)」を参照し、[AppSource にカスタム ビジュアルを公開する](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)方法を学習してください。

### <a name="import-a-custom-visual-from-a-file"></a>カスタム ビジュアルをファイルからインポートする

1. [視覚化] ウィンドウの下部にある省略記号を選択します。

    ![visualizations2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. ドロップダウンで **[ファイルからインポートする]** を選択します。

    ![ファイルからインポート](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. [ファイルを開く] メニューで、インポートする `.pbiviz` ファイルを選び、[開く] を選択します。 カスタム ビジュアルのアイコンが [視覚化] ウィンドウの下部に追加され、レポートで使用できるようになりました。

    ![cv imported](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>組織のビジュアルをインポートする

1. [視覚化] ウィンドウの下部にある省略記号を選択します。

    ![visual org 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. ドロップダウンで [Marketplace からインポートする] を選択します。

    ![visual org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. 一番上のタブ メニューから **[自分の所属組織]** を選択します。

    ![visual org 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. 一覧をスクロールして、インポートするビジュアルを探します。

    ![visual org 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. **[追加]** を選択して、カスタム ビジュアルをインポートします。 カスタム ビジュアルのアイコンが [視覚化] ウィンドウの下部に追加され、レポートで使用できるようになりました。

    ![visual org 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource からカスタム ビジュアルをダウンロードまたはインポートする

カスタム ビジュアルをダウンロードおよびインポートする場合、Power BI と AppSource Web サイトの 2 つのオプションを使用できます。

### <a name="import-custom-visuals-from-within-power-bi"></a>Power BI からカスタム ビジュアルをインポートする

1. [視覚化] ウィンドウの下部にある省略記号を選択します。

    ![visualizations 2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. ドロップダウンで **[Marketplace からインポートする]** を選択します。

    ![visual org 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. 一覧をスクロールして、インポートするビジュアルを探します。

    ![ビジュアルのインポート](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. 各ビジュアルの詳細を確認するには、ビジュアルを強調表示して選択します。

    ![選択](media/power-bi-custom-visuals/power-bi-select.png)

5. 詳細ページでは、スクリーンショット、ビデオ、詳細な説明、その他を見ることができます。

    ![要約](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. レビューを表示するには最下部までスクロールします。

    ![レビュー](media/power-bi-custom-visuals/power-bi-reviews.png)

7. [追加] を選択して、カスタム ビジュアルをインポートします。 カスタム ビジュアルのアイコンが [視覚化] ウィンドウの下部に追加され、レポートで使用できるようになりました。

    ![インポートされたビジュアル](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource からカスタム ビジュアルをダウンロードおよびインポートする

1. [Microsoft AppSource](https://appsource.microsoft.com) から、**[アプリ]** のタブを選択します。

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. [アプリの結果ページ](https://appsource.microsoft.com/marketplace/apps)に移動すると、*[Power BI apps]* を含めた各カテゴリの上位アプリを確認できます。 今はカスタム ビジュアルを検索しているので、左側のナビゲーション リストから **[Power BI visuals]** を選択して結果を絞り込みます。

    ![AppSource のビジュアル](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource に、各カスタム ビジュアルのタイルが表示されます。  各タイルにはカスタム ビジュアルのスナップショットが含まれ、簡単な説明と、ダウンロードのリンクがあります。 詳細を表示するには、タイルを選択します。

    ![ビジュアルのカスタム選択](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. 詳細ページでは、スクリーンショット、ビデオ、詳細な説明、その他を見ることができます。 **[今すぐ入手する]** を選択し、利用規約に同意して、カスタム ビジュアルをダウンロードします。

    ![AppSource の取得](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. カスタム ビジュアルをダウンロードするリンクを選択します。

    ![ダウンロード](media/power-bi-custom-visuals/powerbi-custom-download.png)

    ダウンロードのページには、Power BI Desktop と Power BI サービスにカスタム ビジュアルをインポートする方法についての説明もあります。

    カスタム ビジュアルが含まれ、その機能を見ることができる、サンプル レポートをダウンロードすることもできます。

    ![サンプルを試す](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. '.pbiviz' ファイルを保存し、Power BI を開きます。

7. ".pbiviz" ファイルをレポートにインポートします (上記の「[カスタム ビジュアルをファイルからインポートする](#import-a-custom-visual-from-a-file)」セクションを参照してください)。

## <a name="considerations-and-limitations"></a>考慮事項と制限事項

* カスタム ビジュアルをインポートすると、特定のレポートに追加されます。 ビジュアルを別のレポートで使用する場合は、そのレポートにもインポートする必要があります。 カスタム ビジュアルを含むレポートを **[名前を付けて保存]** オプションで保存すると、カスタム ビジュアルのコピーが新しいレポートと共に保存されます。

* **[視覚化]** ウィンドウが表示されない場合、レポートを編集するアクセス許可がないことを意味します。  カスタム ビジュアルは編集できるレポートにのみ追加でき、共有されているレポートには追加できません。

## <a name="troubleshoot"></a>トラブルシューティング

トラブルシューティングについては、[Power BI カスタム ビジュアルのトラブルシューティング](power-bi-custom-visuals-troubleshoot.md)に関する記事を参照してください。

## <a name="faq"></a>よく寄せられる質問

詳細情報と質問の回答については、[Power BI カスタム ビジュアルについてよく寄せられる質問](power-bi-custom-visuals-faq.md#organizational-custom-visuals)に関するページをご覧ください。

## <a name="next-steps"></a>次の手順

* [Power BI での視覚化](visuals/power-bi-report-visualizations.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。
