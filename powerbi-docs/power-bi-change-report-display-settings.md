---
title: "レポート ページのサイズを変更する (チュートリアル)"
description: "チュートリアル: Power BI レポートのページの表示設定を変更する"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/25/2017
ms.author: mihart
ms.openlocfilehash: a5cc05e26012f88e889612788d4479a370063d4f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2017
---
# <a name="change-the-size-of-a-report-page-tutorial"></a>レポート ページのサイズを変更する (チュートリアル)
[前の記事とビデオ](power-bi-report-display-settings.md)では、Power BI レポートでページ表示を制御するための **[表示]** と **[ページ サイズ]** という 2 つの異なる方法について説明しました。 ここでは、ページの表示設定の変更を試してみましょう。

## <a name="first-lets-change-the-page-view-setting"></a>まずページの [表示] の設定を変更する
1. 読み取りビューまたは編集ビューでレポートを開きます。 この例では、[小売りの分析のサンプル](sample-retail-analysis.md)の [New Stores] ページを使用します。  このページは、**[ページに合わせる]** の設定を使って表示されます。  この場合、\[Fit to Page] \(ページに合わせる) ではレポート ページがスクロールバーなしで表示されますが、一部の詳細やタイトルは小さすぎて読めない場合があります。
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_page.png)
2. キャンバス上で視覚化が選択されていないことを確認します。 **[表示]** を選択して、各表示オプションを確認します。

* 読み取りビューでは次のように表示されます。
  
     ![](media/power-bi-change-report-display-settings/power-bi-page-view-menu-new.png)
* 編集ビューでは次のように表示されます。
  
    ![](media/power-bi-change-report-display-settings/power-bi-view-editing-view.png)

1. **[実際のサイズ]** 設定を使用して、ページの外観を確認してみましょう。
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)
   
   ダッシュボードのスクロール バーが二重になっていて、改善が必要です。
2. **[幅に合わせる]**に切り替えます。
   
   ![](media/power-bi-change-report-display-settings/pbi_fit_to_width.png)
   
   スクロールバーは表示されていますが、詳細は読みやすくなっており、外観は改善されています。

## <a name="change-the-default-view-for-a-report-page"></a>レポート ページの既定のビューを変更する
すべての Power BI レポートには、既定で **[ページに合わせる]** ビューが選択されています。 このレポートを常に **[実際のサイズ]** ビューで開くには、どのようにすればよいでしょうか。

1. レポートの **[New Stores]** ページで、**[実際のサイズ]** ビューに切り替えます。
   
   ![](media/power-bi-change-report-display-settings/power-bi-actual-size.png)
2. **[ファイル] > [名前を付けて保存]** を選択し、レポートを別名で保存します。 これで、このレポートの 2 つのコピーができました。元のレポートでは、**[New Stores]** は引き続き既定のビューで開かれますが、新しいレポートでは **[実際のサイズ]** ビューで表示されます。 確認してみましょう。
   
   ![](media/power-bi-change-report-display-settings/power-bi-save-as.png)
3. 上部ナビゲーション バーで現在のワークスペースの名前を選び、そのワークスペースに戻ります。  
   
   ![](media/power-bi-change-report-display-settings/power-bi-my-workspace.png)
4. **[レポート]** タブを選び、作成したばかりの新しいレポートを選びます (黄色のアスタリスクで示されます)。
   
    ![](media/power-bi-change-report-display-settings/power-bi-new-report2.png)
5. レポートが **[実際のサイズ]** ビューで開きます。
   
   ![](media/power-bi-change-report-display-settings/power-bi-actal-size2.png)

## <a name="now-lets-explore-the-page-size-setting"></a>次は*ページ サイズ*設定を変更する
ページ サイズの設定は、[編集ビュー](service-interact-with-a-report-in-editing-view.md)でのみ利用できます。 編集ビューでレポートを開くには、レポートに対する所有者アクセス許可が必要です。 いずれかの[サンプル](sample-datasets.md)に接続した場合は、そのレポートの所有者アクセス許可を持っています。

1. [小売りの分析のサンプル](sample-retail-analysis.md)の \[District Monthly Sales] \(地域の毎月の売上) ページを編集ビューで開きます。
2. キャンバス上で視覚化が選択されていないことを確認します。  **[視覚化]** ウィンドウで、ペイント ローラー アイコン ![](media/power-bi-change-report-display-settings/power-bi-paintroller.png) を選びます。
3. **[ページ サイズ]** &gt; **[タイプ]** の順に選択して、ページ サイズのオプションを表示します。
   
   ![](media/power-bi-change-report-display-settings/power-bi-page-size-menu-new.png)
4. **[レター]**を選択します。  キャンバス上で、816 x 1056 ピクセル (レター サイズ) 内に収まるコンテンツだけがキャンバスの白い部分に残ります。
   
   ![](media/power-bi-change-report-display-settings/power-bi-letter-new.png)
5. **[表示]** を [幅に合わせる] に変更すると、キャンバスにはレター サイズに収まるページ コンテンツしか表示されなくなります。
   
   ![](media/power-bi-change-report-display-settings/power-bi-fit-to-width-new.png)
6. **[ページ サイズ]** で **[16:9]** の比率を選びます。
   
   ![](media/power-bi-change-report-display-settings/power-bi-16-to-9-new.png)
   
   レポート ページは、横 16 : 縦 9 の比率を使用して表示されます。 使用される実際のピクセルのサイズを確認するには、灰色表示の [幅] フィールドと [高さ] フィールド (1280x720) を調べます。 レポート キャンバスの周囲には空の領域がかなりあります。これは、前に **[表示]** を [幅に合わせる] に設定したためです。
7. **[ページ サイズ]** のオプションをさらにいろいろ試してみてください。

## <a name="using-page-view-and-page-size-together"></a>ページの [表示] と [ページ サイズ] をともに使用する
ページの [表示] と [ページ サイズ] をともに使用して、別のアプリケーションに埋め込んだときに適切に表示されるレポートを作成します。

この演習では、幅 500 ピクセル、高さ 750 ピクセルの領域があるアプリケーションに表示されるレポート ページを作成します。

前の手順で見たように、現在のレポート ページは幅 1280 ピクセル、高さ 720 ピクセルで表示されます。 すべてのビジュアルをその領域に合わせるには、サイズ変更と再配置を何度も実行する必要があります。

1. ビジュアルが現在のキャンバス領域の半分より少ない領域に収まるように、ビジュアルのサイズ変更と移動を行います。
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-view.gif)
2. **[ページ サイズ]** &gt; **[カスタム]** を選択します。
3. [幅] を 500、[高さ] を 750 に設定します。
   
    ![](media/power-bi-change-report-display-settings/power-bi-custom-new.png)
4. 表示が最良の状態になるように、レポート ページを調整します。 **[表示] > [実際のサイズ]** と **[表示] > [ページに合わせる]** を切り替えて調整します。
   
    ![](media/power-bi-change-report-display-settings/power-bi-final-new.png)

## <a name="next-steps"></a>次の手順
[Cortana 用レポートの作成](service-cortana-answer-cards.md)

「[Power BI レポートのページ表示設定](power-bi-report-display-settings.md)」に戻る

[Power BI のレポート](service-reports.md)について詳細を確認する

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

