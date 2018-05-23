---
title: Power BI モバイル アプリのレポートを調べる
description: スマートフォンまたはタブレット上の Power BI モバイル アプリでレポートを表示および操作する方法について説明します。 Power BI サービスまたは Power BI Desktop でレポートを作成し、モバイル アプリで操作します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 03/22/2018
ms.author: maggies
ms.openlocfilehash: 6d7ab55c3ecbb13b40354f67263d597f0e1179f7
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Power BI モバイル アプリのレポートを調べる
適用対象:

| ![iPhone](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Android フォン](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Android タブレット](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Windows 10 デバイス](media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |Android フォン |Android タブレット |Windows 10 デバイス |

Power BI レポートは、データの対話型表示で、データから得られるさまざまな発見と洞察を表す視覚化が付いています。 Power BI モバイル アプリでは、3 段階のプロセスの 3 つ目の手順でレポートを表示できます。

1. [Power BI Desktop でレポートを作成します](desktop-report-view.md)。 Power BI Desktop で[スマートフォン用にレポートを最適化](mobile-apps-view-phone-report.md)することもできます。 
2. そのレポートを Power BI サービス [(https://powerbi.com)](https://powerbi.com) または [Power BI Report Server](report-server/get-started.md) に公開します。  
3. 次に、Power BI モバイル アプリでこれらのレポートを操作します。

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>モバイル アプリで Power BI レポートを開く
Power BI レポートは、入手した場所に応じてモバイル アプリのそれぞれの場所に保存されます。 具体的には、アプリ、自分と共有、ワークスペース (マイ ワークスペースを含む)、またはレポート サーバーに保存されます。 関連するダッシュボードからレポートにアクセスしたり、一覧が表示されたりすることがあります。

* ダッシュボードで、タイルの右上にある省略記号 (...) をタップして **[レポートを開く]** をタップします。
  
  ![レポートを開く](media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  タイルによっては、レポートでは開けないオプションもあります。 たとえば、Q&A ボックスに質問して作成するタイルをタップしてもレポートは開きません。 
  
  スマートフォンでは、[スマートフォンでの表示に最適化](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones)されていない限り、横向きモードでレポートが開きます。
  
  ![横向きモードで開いている電話レポート](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>スマートフォン用に最適化されたレポートを表示する
Power BI レポート作成者は、スマートフォン用に最適化されたレポート レイアウトを作成することができます。 スマート フォン用に最適化されたレポート ページには機能が追加されました。たとえば、ドリルダウンしてビジュアルでの並べ替えを行ったり、[レポート ページに追加されたレポート作成者のフィルター処理](mobile-apps-view-phone-report.md#filter-the-report-page-on-a-phone)を行ったりできます。 スマートフォンで開かれるレポートは、Web 上のレポートでフィルター処理に使われているのと同じ値でフィルター処理され、ページにアクティブなフィルターがあることを示すメッセージが表示されます。 スマートフォンでフィルターを変更できます。

レポートの一覧では、最適化されているレポートに特別なアイコンが付きます。 ![電話レポート アイコン](media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![電話レポートを開く](media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

そのレポートをスマートフォンで表示すると、縦向き表示で開きます。

![縦向き表示のレポート](media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

 レポートには、スマートフォン用に最適化されたページと最適化されていないページが混在している可能性があります。 その場合、レポートのページをめくると、ページごとに表示が縦向きから横向きに切り替わります。

詳しくは、「[電話用に最適化されたレポートを表示して使用する](mobile-apps-view-phone-report.md)」をご覧ください。

## <a name="use-slicers-to-filter-a-report"></a>スライサーを使ったレポートのフィルター処理
Power BI Desktop または Power BI サービスでレポートをデザインする際に、[レポート ページにスライサーを追加](power-bi-visualization-slicers.md)することもできます。 自分と同僚とでスライサーを使って、ブラウザーおよびモバイル アプリでページをフィルター処理できます。 スマートフォンでレポートを表示する際は、横向きモードでもスマートフォンの縦向きモードに最適化されたページでもスライサーを使って表示および操作できます。 ブラウザーのスライサーまたはフィルターで値を選ぶと、モバイル アプリでページを表示するときもその値が選ばれます。 ページにアクティブなフィルターがあることを示すメッセージが表示されます。  

* レポート ページのスライサーで値を選択すると、ページ上の他のビジュアルがフィルターされます。
  
  ![レポートのスライサー](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  この図では、スライサーによって縦棒グラフがフィルターされ、7 月の値のみが表示されています。

## <a name="cross-filter-and-highlight-a-report"></a>レポートのクロス フィルター処理と強調表示
ビジュアルの値を選択しても、他のビジュアルはフィルターされません。 他のビジュアルに含まれる関連する値が強調表示されます。

* ビジュアルの値をタップします。
  
  ![ページのクロス フィルター処理](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  1 つのビジュアル内の [大] 列をタップすると、他のビジュアルで関連する値が強調表示されます。 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>iPad またはタブレットでビジュアルを並べ替える
* グラフをタップし、省略記号 (**...**) をタップして、フィールド名をタップします。
  
   ![ビジュアルの並べ替え](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* 並べ替え順序を逆にするには、省略記号 (**...**) をもう一度タップし、同じフィールド名をタップします。

## <a name="drill-down-on-an-ipad-or-a-tablet"></a>iPad またはタブレットでドリルダウンする
レポート作成者がドリルダウン機能をビジュアルに追加した場合、iPad またはタブレットでビジュアルをドリルダウンして、含まれる値を表示することができます。 [ビジュアルへのドリルダウンの追加](power-bi-visualization-drill-down.md)は、Power BI Desktop または Power BI サービスで行います。 

> [!NOTE]
> 現在、iPad またはタブレット内のマップではドリルダウンが機能しません。
> 
> 

* ビジュアルをタップします。 上の角に上矢印と下矢印がある場合は、 ![ドリルアップ、ドリルダウン アイコン](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-down.png)ドリルダウンすることができます。 1 つの値についてドリルダウンするには、右上の矢印をタップし、ビジュアルの値 (この例では濃い青色の FD-04 バブル) をタップします。
  
  ![ビジュアルをドリルダウンする](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-one.png)
* ドリルアップするには、左上隅にある上矢印をタップします。
  
  ![ドリル アップ](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up.png)

## <a name="go-back-to-my-workspace"></a>マイ ワークスペースに戻る
* レポート名の横の矢印をタップし、**[マイ ワークスペース]** をタップします。
  
  ![マイ ワークスペースに戻る](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-back.png)

## <a name="next-steps"></a>次の手順
* [電話用に最適化された Power BI レポートの表示と対話](mobile-apps-view-phone-report.md)
* [電話用に最適化されたバージョンのレポートの作成](desktop-create-phone-report.md)
* わからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

