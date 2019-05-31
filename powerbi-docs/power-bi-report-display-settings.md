---
title: Power BI レポートのページ表示設定
description: レポートのページ表示設定
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 8a96371d6cb54d47d412165ef179df78a34b8e19
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412943"
---
# <a name="page-display-settings-in-a-power-bi-report"></a>Power BI レポートのページ表示設定
完全なレポートのレイアウトをピクセルを保持することが重要認識しています。 場合によっては、難しい場合も、ため、自分と同僚は、縦横比が異なると、サイズの画面で、それらのレポートを表示可能性があります。 

既定の表示レイアウトは **[ページに合わせる]** で、既定の表示サイズは **[16:9]** です。 異なる縦横比にロックしたり、別の方法でレポートの表示を調整したりするには、次の 2 つを利用できます:***ページ ビュー***設定と***ページ サイズ***設定します。


<iframe width="560" height="315" src="https://www.youtube.com/embed/5tg-OXzxe2g" frameborder="0" allowfullscreen></iframe>


## <a name="where-to-find-page-view-settings-in-the-power-bi-service-and-power-bi-desktop"></a>Power BI サービスと Power BI Desktop 内のページ表示設定を検索する場所
ページ ビュー設定は、Power BI サービスと Power BI Desktop の両方で使用できますが、インターフェイスは少し異なります。 次のセクションでは、各 Power BI ツールでビューの設定を見つけることができますを説明します。

### <a name="in-power-bi-desktop"></a>Power BI Desktop の場合
レポート ビューで、 **[表示]** タブを選んで [ページ表示] 設定と [電話レイアウト] 設定を開きます。

  ![デスクトップのページ ビュー設定](media/power-bi-report-display-settings/power-bi-desktop-view-settings.png)

### <a name="in-the-power-bi-service-apppowerbicom"></a>Power BI サービス (app.powerbi.com)
Power BI サービスで開き、レポートを**ビュー**上の左側のメニュー バーから。

![サービスのページ ビュー設定](media/power-bi-report-display-settings/power-bi-change-page-view.png)

ページ ビュー設定は両方で使用できる[読み取りビューと編集ビュー](consumer/end-user-reading-view.md)します。 編集ビューでは、レポート所有者が個々 のレポートのページにページ表示設定を割り当てることができ、これらの設定は、レポートと共に保存されます。 同僚が読み取りビューでそのレポートを開くと、所有者の設定を使用してレポート ページが表示されます。 読み取りビューでの仕事仲間を変更できます*一部*の**ページ表示**レポートを終了するときに、設定が、変更は保存されません。

## <a name="page-view-settings"></a>ページ表示の設定
ページ ビュー設定の最初のセットは、ブラウザー ウィンドウを基準にレポート ページの表示を制御します。 次の中から選びます。

* **ページに合わせる**(既定値)。内容が最適なページに合わせて拡大/縮小されます。
* **幅に合わせる**:内容は、ページの幅に収まるように拡大/縮小されます。
* **実際のサイズ**:フル サイズで内容が表示されます。

2 つ目は、レポート キャンバス上のオブジェクトの配置をページ ビュー設定のコントロールの設定。 次の中から選びます。

* **グリッド線の表示**:グリッド線を表示するレポート キャンバスにオブジェクトを配置します。
* **グリッドにスナップ**:使用して**グリッド線の表示**を正確に配置し、レポート キャンバスにオブジェクトを配置します。 
* **オブジェクトをロック**:キャンバス上のすべてのオブジェクトをロックし、移動またはサイズ変更できないようにします。
* **選択ウィンドウ**:**選択**ウィンドウには、キャンバス上のすべてのオブジェクトが一覧表示されます。 表示して非表示にすることができます。

    ![選択ウィンドウ](media/power-bi-report-display-settings/power-bi-selection-pane.png)



## <a name="page-size-settings"></a>ページ サイズの設定
![ページ サイズの設定を変更します。](media/power-bi-report-display-settings/power-bi-page-size.png)

**ページ サイズ**設定はレポートの所有者でのみ使用できます。 Power BI サービス (app.powerbi.com) では、これは意味でレポートを開けること[編集ビュー](consumer/end-user-reading-view.md)します。 **ページ サイズ**の設定は、**視覚化**ウィンドウとコントロールの表示比率と実際のサイズ (ピクセル単位)、レポート キャンバスの。   

* 4:3 の縦横比
* 16:9 の縦横比 (既定値)
* Cortana
* 文字
* カスタム (ピクセル単位の高さと幅)

## <a name="next-steps"></a>次の手順
[Power BI Desktop のレポート ビュー](desktop-report-view.md)

[ページ ビューと、独自の Power BI レポートのページ サイズの設定を変更します。](consumer/end-user-report-view.md)

[Power BI のレポート](consumer/end-user-reports.md)で詳細を確認する

[Power BI サービスのコンシューマー向けの基本的な概念](consumer/end-user-basic-concepts.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

