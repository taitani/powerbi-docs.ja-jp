---
title: "認定済みの Power BI カスタム ビジュアル"
description: "認定のためにカスタム ビジュアルを送信する場合の要件とプロセス。 認定済みのカスタム ビジュアルの一覧。"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/12/2018
ms.author: mihart
ms.openlocfilehash: 955435ee526c6acae8f478539641529515e2e0a8
ms.sourcegitcommit: 259d7689bcb1683d4d63a245a9b02becea072139
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="getting-a-custom-visual-certified"></a>カスタム ビジュアルの *認定* を受ける
## <a name="what-is-meant-by-certified"></a>*認定* とは
*認定済みカスタム ビジュアル*とは、一連のコードの要件を満たし、厳密なセキュリティ テストに合格したものです。  カスタム ビジュアルが認定されたら、[PowerPoint にエクスポートすることができ](service-publish-to-powerpoint.md)、ユーザーが[レポート ページをサブスクライブ](service-report-subscribe.md)したときに受け取るメールにそれが表示されます。 もちろん、[標準カスタム ビジュアル](power-bi-custom-visuals.md)として使用したり、Power BI サービスと Power BI Desktop レポートに追加したり、Power BI モバイルで表示したり、埋め込んだりすることもできます。

独自の視覚エフェクトを作成して [Microsoft AppSource](https://appsource.microsoft.com) に追加することに興味がある Web 開発者の方は、 「[開発者ツールの概要](service-custom-visuals-getting-started-with-developer-tools.md)」をご覧ください。


## <a name="certification-requirements"></a>認定要件
* Microsoft AppSource による承認済み    
* カスタム ビジュアルがバージョン管理された API 1.2 以降で記述されていること    
* レビュー用にコード リポジトリが使用可能なこと (たとえば、ビジュアル コードが GitHub を通じて利用できること)    
* 公開レビュー可能な OSS コンポーネントのみを使用すること    
* 外部のサービスまたはリソースにアクセスしないこと    

> **ヒント**: 送信する前に、EsLint と既定のセキュリティ ルールセットを使用して、コードを事前検証することをお勧めします。
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>認定のためにカスタム ビジュアルを送信するプロセス
認定のためにカスタム ビジュアルを送信するには、次の手順に従います。

1. Power BI カスタム ビジュアルのサポート (pbicvsupport@microsoft.com) に電子メールを送信します。 電子メールには、次の情報を含めます。    
   
   * 件名: ビジュアル認定の要求    
   * ビジュアルのソース コードがホストされている GitHub リポジトリへのリンク    
   * 要件 (上記参照) の遵守    
   * コードとセキュリティ レビューの提出    
2. カスタム ビジュアルが認定され、認定リスト (下記) に追加された場合、または修正する必要がある問題のレポートで拒否された場合は、マイクロソフトのカスタム ビジュアル チームによって通知されます。 マイクロソフトとの連絡手段を維持し、必要に応じて認定済みのビジュアルを更新するのは、開発者の責任です。

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Power BI の認定済みのカスタム ビジュアルの削除
マイクロソフトは独自の裁量で認定リストからビジュアルを削除できます。  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>認定されているカスタム ビジュアルの一覧
| AppSource へのリンク | 動画のリンク |
| --- | --- |
| [関連付けルール](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [アスター プロット](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar (Beyondsoft Calendar)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [MAQ Software による Bowtie chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[ビデオ](https://youtu.be/So5xKMSpVJI) |
| [箱ひげ図](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [MAQ Software によるブリック グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | |
| [Akvelon によるバブル グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340?src=office) | |
| [箇条書きのグラフ](https://store.office.com/app.aspx?assetid=WA104380755) |[ビデオ 1](https://youtu.be/AOlsFYkfkcw)   [ビデオ 2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz (OKViz による箇条書きグラフ)](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[ビデオ](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [OKViz によるローソク足](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | |
| [Chiclet slicer (Chiclet スライサー)](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[ビデオ](https://youtu.be/iYOkJ1APueY) |
| [コード チャート](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[ビデオ](https://youtu.be/AQvd2FhRyCI) |
| [MAQ Software による円形ゲージ](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [円柱ゲージ](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [ダイヤル ゲージ](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[ビデオ](https://youtu.be/AOlsFYkfkcw) |
| [MAQ Software によるドーナツ グラフ (リング グラフ)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[ビデオ](https://youtu.be/pDToHDFHnq8) |
| [MAQ ソフトウェアによるドット プロット](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381101) | |
| [Dot Plot by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[ビデオ](https://youtu.be/4lskRgcpFJY) |
| [Microsoft によるドット プロット](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760?src=office) | |
| [ZoomCharts によるドリルダウン ドーナツ グラフ](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [ドリルダウン カルトグラム](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045?src=office) | |
| [ドリルダウン コロプレス](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044?src=office) | |
| [ZoomCharts によるドリルダウン縦棒グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881?src=office) | |
| [ZoomCharts による時間基準データのドリルダウン縦棒グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | |
| [ZoomCharts によるドリルダウン ドーナツ グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [デュアル KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[ビデオ](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [強化された散布図](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| [Enlighten バブル スタック](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380868) | |
| [Enlighten スタック シャッフル](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten ワッフル グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Enlighten ワールド フラグ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380923) | |
| [フライホイール]() | |
| [予測 TBATS](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381326?src=office) | |
| [ガント](https://store.office.com/gantt-WA104380765.aspx) |[ビデオ](https://youtu.be/qJ7s_KrGiUU) |
| [Akvelon による階層グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333?src=office) | |
| [ヒストグラム](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [水平じょうご](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[ビデオ](https://youtu.be/SudZei68PPo) |
| [イメージ タイムライン](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [インフォグラフィック デザイナー](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898?src=office) | |
| [KPI インジケーター](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [MAQ Software による KPI ティッカー](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | |
| [LineDot グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766?src=office) | |
| [MAQ Software による線形ゲージ](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[ビデオ](https://youtu.be/AOlsFYkfkcw) |
| [Mekko chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [ビデオ](https://youtu.be/90FLCKpgicA)|
| [Play Axis (動的スライサー)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[ビデオ](https://youtu.be/IvfIP3E6-1Q) |
| [パルス グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | |
| [Radar chart (レーダー チャート)](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [MAQ Software によるリング グラフ (ドーナツ グラフ)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [ビデオ](https://youtu.be/pDToHDFHnq8)|
| [MAQ Software による回転グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007?src=office) |  |
| [Sankey グラフ](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[ビデオ](https://youtu.be/WWP9wVUHGaA) |
| [スクローラー](https://store.office.com/scroller-WA104381018.aspx) |[ビデオ](https://youtu.be/uhRFQF2cGSY) |
| [Smart Filter by OKViz](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[ビデオ](https://youtu.be/gcJsDDRQq28) |
| [OKViz によるスパークライン](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[ビデオ](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [テーブル ヒートマップ](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [回転速度計](https://store.office.com/tachometer-WA104380937.aspx?) |[ビデオ](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [テキスト ラッパー](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [温度計](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [ビデオ](https://youtu.be/SPX9mgrAdBc)|
| [時系列分解](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [タイムライン スライサー](https://store.office.com/timeline-slicer-WA104380786.aspx) |[ビデオ](https://youtu.be/ozMtZ4_NZ10) |
| [トルネード チャート](https://store.office.com/tornado-chart-WA104380768.aspx) |[ビデオ](https://youtu.be/AQvd2FhRyCI) |
| [Klaus Birringer による Ultimate Variance グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140?src=office) | |
| [Ultimate Waterfall (無料)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | |
| [MAQ Software による Venn ダイアグラム](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381231) | |
| [VitaraCharts - MicroChart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381165) | |
| [ワッフル グラフ](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[ビデオ](https://youtu.be/1vRqYUsm3Vk) |
| [ワード クラウド](https://store.office.com/word-cloud-WA104380752.aspx?) |[ビデオ](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>次の手順
[カスタム ビジュアル開発者ツール (プレビュー) の概要](service-custom-visuals-getting-started-with-developer-tools.md)      
[YouTube の Microsoft カスタム ビジュアル プレイリスト](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI での視覚化](power-bi-report-visualizations.md)  
[Power BI でのカスタム ビジュアル](power-bi-custom-visuals.md)  
[Microsoft AppSource へのカスタム ビジュアルの公開](developer/office-store.md)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

