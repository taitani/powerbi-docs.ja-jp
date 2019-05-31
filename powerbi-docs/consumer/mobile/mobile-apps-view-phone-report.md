---
title: 電話用に最適化された Power BI レポートを表示する
description: Power BI 電話アプリで表示するように最適化されたレポート ページとの対話について説明しています。
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/22/2019
ms.author: mshenhav
ms.openlocfilehash: 79ca47f83bb39ab9d6df141b5a26dcb54e00c72c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100988"
---
# <a name="view-power-bi-reports-optimized-for-your-phone"></a>電話用に最適化された Power BI レポートを表示する

適用対象:

| ![iPhone](./media/mobile-apps-view-phone-report/ios-logo-40-px.png) | ![Android フォン](./media/mobile-apps-view-phone-report/android-logo-40-px.png) |
|:--- |:--- |
| iPhone |Android フォン |

スマート フォンに Power BI レポートを表示すると、Power BI は、レポートが電話用に最適化されているかどうかを確認します。 場合は、Power BI は縦長ビューに最適化されたレポートを自動的に開きます。

![縦モードのレポート](./media/mobile-apps-view-phone-report/07-power-bi-phone-report-portrait.png)

電話用に最適化されたレポートが存在しない場合でもレポートは開きますが、最適化されていない横長ビューです。 電話用に最適化されたレポートでも、電話を横向きにすると、レポートが元のレポート レイアウトの最適化されていないビューで開きます。 一部のページのみを最適化している場合、縦長ビューに、レポートを横長で使用できることを示すメッセージが表示されます。

![最適化されていないレポート ページ](./media/mobile-apps-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Power BI レポートの他のすべての機能は、引き続き電話用に最適化されたレポートで機能します。 実行できることの詳細については、次を参照してください。

* [iPhone でのレポート](mobile-reports-in-the-mobile-apps.md)。 
* [Android フォンでのレポート](mobile-reports-in-the-mobile-apps.md)。

## <a name="filter-the-report-page-on-a-phone"></a>電話でレポート ページをフィルター処理する
電話用に最適化されたレポートにフィルターが定義されている場合、電話でレポートを表示するときに、これらのフィルターを使うことができます。 電話で、web 上のレポートでフィルター選択されている値をフィルター処理されたレポートを開きます。 ページにアクティブなフィルターがあることを示すメッセージが表示されます。 スマートフォンでフィルターを変更できます。

1. ページの下部にあるフィルター アイコン ![電話のフィルター アイコン](./media/mobile-apps-view-phone-report/power-bi-phone-filter-icon.png) をタップします。 
2. 基本的または詳細なフィルター処理を使って、関心がある結果を表示します。
   
    ![Power BI 電話レポートの詳細フィルター](./media/mobile-apps-view-phone-report/power-bi-iphone-advanced-filter-toronto.gif)

## <a name="cross-highlight-visuals"></a>ビジュアルをクロス強調表示する
クロス (縦向き) ビジュアルを強調表示ビューでは、横長ビューでのスマート フォンと、Power BI サービスでに行う方法が機能します。1 つのビジュアルでデータを選択すると、そのページの他のビジュアルの関連するデータが強調表示されます。

詳しくは、[Power BI のフィルターと強調表示について](../../power-bi-reports-filters-and-highlighting.md)のページを参照してください。

## <a name="select-visuals"></a>ビジュアルを選択する
電話レポートで、ビジュアルを選択すると、そのビジュアルが強調表示され、フォーカスされて、キャンバスのジェスチャが無効になります。

ビジュアルが選択されている場合、ビジュアル内でスクロールなどの操作を実行できます。 ビジュアルを選択解除するには、ビジュアル領域外の任意の場所に触れるだけです。

## <a name="open-visuals-in-focus-mode"></a>フォーカス モードでビジュアルを開く
電話レポートでは、フォーカス モードも提供します。拡大表示して、1 つのビジュアルを取得しより簡単に調査します。

* 電話レポートで、ビジュアルの右上隅にある省略記号 **[...]** をタップし、 **[フォーカス モードに展開]** をタップします。
  
    ![フォーカス モードに展開](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)

フォーカス モードで何が引き継がレポート キャンバスに、その逆です。 たとえば、ビジュアルで値を強調表示してレポート全体に戻る場合は、レポートのビジュアルで強調表示されている値にフィルターが。

画面サイズの制限により、フォーカス モードでは、一部の操作のみ実行できます。

* ビジュアルに表示される情報に**ドリルダウン**します。 詳しくは、電話レポートの[ドリルダウンとドリルアップ](mobile-apps-view-phone-report.md#drill-down-in-a-visual)に関するページを参照してください。
* ビジュアル内の値を**並べ替え**ます。
* **[元に戻す]** :ビジュアルで使用した探索手順をクリアし、レポートの作成時に設定された定義に戻します。
  
    ビジュアルからすべての探索をクリアするには、省略記号 **[...]** **[元に戻す]** の順にタップします。
  
    ![元に戻す](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)
  
    元に戻すは、すべてのビジュアルからの探索をオフにすると、レポート レベルで、またはオフにすると、選択したビジュアルからの探索、ビジュアルのレベルで使用します。   

## <a name="drill-down-in-a-visual"></a>ビジュアルをドリルダウンする
ビジュアルで階層レベルが定義されている場合、ビジュアルに表示されている詳細情報にドリルダウンした後、ドリルアップして戻ることができます。 [ビジュアルへのドリルダウンの追加](../end-user-drill.md)は、Power BI サービスまたは Power BI Desktop で行います。

ドリル ダウンのいくつかの種類があります。

### <a name="drill-down-on-a-value"></a>値にドリル ダウン
1. 時間の長いビジュアルでデータ ポイント (タップ アンド ホールド) をタップします。
2. ツールヒントが表示され、階層が定義されている場合は、そのツールヒントのフッターがドリルダウンとドリルアップの矢印が表示されます。
3. ドリルダウンの下向きの矢印をタップします

    ![Tap のドリルダウン](././media/mobile-apps-view-phone-report/report-drill-down.png)
    
4. ドリル アップの上向きの矢印をタップします。

### <a name="drill-to-next-level"></a>次のレベルにドリル ダウンします。
1. 電話のレポートでは、右上隅にある省略記号 **[...]** 、 **[フォーカス モードに展開]** の順にタップします。
   
    ![フォーカス モードに展開](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)
   
    この例では、バーには州の値が表示されています。
2. 左下の [探索] アイコン ![探索アイコン](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-icon.png) 左の下。
   
    ![探索モード](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-mode.png)
3. **[次のレベルを表示する]** または **[次のレベルに展開]** をタップします。
   
    ![次のレベルに展開](./media/mobile-apps-view-phone-report/power-bi-phone-report-expand-levels.png)
   
    今度は、バーに都市の値が表示されます。
   
    ![展開されたレベル](./media/mobile-apps-view-phone-report/power-bi-phone-report-expanded-levels.png)
4. 左上隅の矢印をタップすると、下位レベルの値がまだ展開された状態で、電話レポートに戻ります。
   
    ![下位レベルの値がまだ展開された状態](./media/mobile-apps-view-phone-report/power-bi-back-to-phone-report-expanded-levels.png)
5. 上位の元のレベルに戻るには、省略記号 **[...]** を再びタップし、 **[元に戻す]** をタップします。
   
    ![元に戻す](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)

## <a name="drill-through-from-a-value"></a>値からのドリルスルーします。
ドリルスルーは、1 つのレポート ページで、値を他のレポート ページに接続します。 別のレポート ページにデータ ポイントからドリルスルーする場合は、フィルター ページで、処理、ドリルするデータ ポイント値が使用されます。 または選択したデータのコンテキストになります。
レポート作成者は[ドリル スルーを定義する](https://docs.microsoft.com/power-bi/desktop-drillthrough)レポートを作成するとき。

1. 時間の長いビジュアルでデータ ポイント (タップ アンド ホールド) をタップします。
2. ツールヒントが表示され、ドリルスルーが定義されている場合は、ツールヒントのフッターが矢印のドリルスルーは表示します。
3. ドリルスルーの矢印をタップします

    ![ドリルスルーをタップします。](././media/mobile-apps-view-phone-report/report-drill-through1.png)

4. ドリルスルー レポート ページを選択します。

    ![レポート ページを選択します。](././media/mobile-apps-view-phone-report/report-drill-through2.png)

5. 開始したページに戻るにアプリのヘッダーで、[戻る] ボタンを使用します。


## <a name="next-steps"></a>次の手順
* [Power BI 電話アプリ用に最適化したレポートを作成する](../../desktop-create-phone-report.md)
* [Power BI でダッシュボードの Phone ビューを作成する](../../service-create-dashboard-mobile-phone-view.md)
* [任意のサイズに最適化されるレスポンシブ ビジュアルを作成する](../../visuals/desktop-create-responsive-visuals.md)
* 他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

