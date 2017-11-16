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
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: 27af387a6d789b00837e6bbf8c6be9aa219c7198
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="getting-a-custom-visual-certified"></a>カスタム ビジュアルの *認定* を受ける
## <a name="what-is-meant-by-certified"></a>*認定* とは
*認定済みカスタム ビジュアル*とは、一連のコードの要件を満たし、厳密なセキュリティ テストに合格したものです。  カスタム ビジュアルが認定されたら、[PowerPoint にエクスポートすることができ](service-publish-to-powerpoint.md)、ユーザーが[レポート ページをサブスクライブ](service-report-subscribe.md)したときに受け取るメールにそれが表示されます。

* 独自の視覚エフェクトを作成してストアに追加することに興味がある Web 開発者の方は、 「[開発者ツールの概要](service-custom-visuals-getting-started-with-developer-tools.md)」および [Office ストア](service-custom-visuals-office-store.md)で方法をご覧ください。
* 定期的に使用する Office ストアのビジュアルがある場合は、 ビジュアルの開発者に、ビジュアルに Microsoft の認定を受けるよう依頼してください。  開発者の連絡先情報は、ビジュアルの**詳細**ページに **[プロバイダー]** として示されています。

## <a name="certification-requirements"></a>認定要件
* Office ストアが承認されていること    
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
| Office ストアのリンク | 動画のリンク |
| --- | --- |
| [関連付けルール](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [アスター プロット](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar] 近日公開予定 | |
| [箱ひげ図](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [箇条書きのグラフ](https://store.office.com/en-us/app.aspx?assetid=WA104380755) |[ビデオ 1](https://youtu.be/AOlsFYkfkcw)   [ビデオ 2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz (OKViz による箇条書きグラフ)](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[ビデオ](https://youtu.be/mtvUNl9bMjA) |
| [OKViz の Card with States](https://store.office.com/card-with-states-by-okviz-WA104380967.aspx) |[ビデオ 1](https://youtu.be/myiX0BmZd8U)   [ビデオ 2](https://youtu.be/AOlsFYkfkcw) |
| [Chiclet slicer (Chiclet スライサー)](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[ビデオ](https://youtu.be/iYOkJ1APueY) |
| [MAQ Software による円形ゲージ](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [円柱ゲージ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | |
| [ダイヤル ゲージ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) |[ビデオ](https://youtu.be/AOlsFYkfkcw) |
| [MAQ Software によるドーナツ グラフ (リング グラフ)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[ビデオ](https://youtu.be/pDToHDFHnq8) |
| [ドリルダウン ドーナツ グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [デュアル KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[ビデオ](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| Fly Wheel (フライ ホイール) - 近日公開予定 | |
| [ガント](https://store.office.com/gantt-WA104380765.aspx) |[ビデオ](https://youtu.be/qJ7s_KrGiUU) |
| [ヒストグラム](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [水平じょうご](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) |[ビデオ](https://youtu.be/SudZei68PPo) |
| [イメージ タイムライン](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [KPI インジケーター](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| 液体注入ゲージ - 近日公開予定 |[ビデオ](https://youtu.be/wQ51TTqIZc4) |
| [MAQ Software による線形ゲージ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[ビデオ](https://youtu.be/AOlsFYkfkcw) |
| 長いテキスト ビューアー - 近日公開予定 | |
| [Play Axis (動的スライサー)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[ビデオ](https://youtu.be/IvfIP3E6-1Q) |
| [パルス グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006?src=office&tab=Overview) |[ビデオ](https://www.youtube.com/watch?v=DQWdcQtjDVw) |
| [Radar chart (レーダー チャート)](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Sankey グラフ](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[ビデオ](https://youtu.be/WWP9wVUHGaA) |
| [MAQ Software によるリング グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) |[ビデオ](https://youtu.be/pDToHDFHnq8) |
| [スクローラー](https://store.office.com/scroller-WA104381018.aspx) |[ビデオ](https://youtu.be/uhRFQF2cGSY) |
| [Smart Filter by OKViz (OKViz でのスマート フィルター)](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[ビデオ](https://youtu.be/gcJsDDRQq28) |
| [OKViz によるスパークライン](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[ビデオ](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [回転速度計](https://store.office.com/tachometer-WA104380937.aspx?) |[ビデオ](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [時系列分解](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380897) | |
| [テーブル ヒートマップ](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [テキスト ラッパー](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [タイムライン スライサー](https://store.office.com/timeline-slicer-WA104380786.aspx) |[ビデオ](https://youtu.be/ozMtZ4_NZ10) |
| [トルネード チャート](https://store.office.com/tornado-chart-WA104380768.aspx) |[ビデオ](https://youtu.be/AQvd2FhRyCI) |
| [Visio ビジュアル (プレビュー)](https://store.office.com/visio-visual-preview-WA104381132.aspx) |[ビデオ](https://www.youtube.com/watch?v=dCcd7rftjZA&list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x&index=2) |
| [ワッフル グラフ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[ビデオ](https://youtu.be/1vRqYUsm3Vk) |
| [ワード クラウド](https://store.office.com/word-cloud-WA104380752.aspx?) |[ビデオ](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>次の手順
[Office ストアからカスタム ビジュアルをダウンロードして使用する](service-custom-visuals-office-store.md)  
[カスタム ビジュアル開発者ツール (プレビュー) の概要](service-custom-visuals-getting-started-with-developer-tools.md)      
[YouTube の Microsoft カスタム ビジュアル プレイリスト](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI での視覚化](power-bi-report-visualizations.md)  
[Power BI でのカスタム ビジュアル](power-bi-custom-visuals.md)  
[カスタム ビジュアルをレポートに追加する (Desktop)](power-bi-custom-visuals-use.md)  
[カスタム ビジュアルを Office ストアに発行する](developer/office-store.md)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

