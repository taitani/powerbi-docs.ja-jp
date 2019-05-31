---
title: レポートへのフィルターの追加 (編集ビュー)
description: Power BI でレポートにページ フィルター、視覚化フィルター、またはレポート フィルターを追加する
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 3666335394222d32bc13ce86d8d0a4ed421b5f73
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187628"
---
# <a name="add-a-filter-to-a-report-in-editing-view"></a>レポートへのフィルターの追加 (編集ビュー)

この記事では、Power BI でレポートにページ フィルター、視覚エフェクト フィルター、レポート フィルター、ドリルスルー フィルターを追加する方法を説明します。 この記事の例は、Power BI サービスのものです。 Power BI Desktop でも手順はほとんど同じです。

**ご存知でしたか?** Power BI には新しいフィルター エクスペリエンスがあります (現在プレビュー段階)。 詳細については、[Power BI レポートの新しいフィルター エクスペリエンス](power-bi-report-filter-preview.md)に関する記事をご覧ください。

![新しいフィルター エクスペリエンス](media/power-bi-report-add-filter/power-bi-filter-reading.png)

## <a name="filters-in-editing-view-or-reading-view"></a>編集ビューまたは読み取りビューでのフィルター
レポートの操作は 2 種類のビューで行うことができます。読み取りビューと編集ビューです。 使用できるフィルター処理機能は、どのビューを使用しているかによって異なります。 詳しくは、「[Power BI レポートのフィルターと強調表示について](power-bi-reports-filters-and-highlighting.md)」をご覧ください。

この記事では、レポートの**編集ビュー**でフィルターを作成する方法について説明します。  読み取りビューでのフィルターについて詳しくは、[レポートの読み取りビューのフィルターとの対話](consumer/end-user-report-filter.md)に関する記事をご覧ください。

## <a name="filter-types-in-the-filters-pane"></a>[フィルター] ウィンドウでのフィルターの種類
Desktop と Power BI サービスのどちらを使用しているかに関係なく、フィルター ウィンドウはレポート キャンバスの右側に表示されます。 フィルター ウィンドウが表示されない場合は、右上隅にある ">" アイコンを選択して展開してください。

フィルターには、**ページ フィルター**、**ビジュアル フィルター**、**ドリルスルー フィルター**、**レポート フィルター**の 4 つの種類があります。

![読み取りビューのフィルター ウィンドウ](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

フィルターは "*永続的*" であるため、ユーザーがレポートから離れても、Power BI によってフィルター、スライサー、ユーザーが行ったその他のデータ ビューの変更は保持されます。 そのため、レポートに戻ったとき、前回終了したところから再開できます。 フィルターの変更を残さない場合は、上部のメニュー バーから **[既定値にリセット]** を選択します。

![永続的フィルター ボタン](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="add-a-filter-to-a-visual"></a>ビジュアルにフィルターを追加する
2 つの方法で、特定のビジュアルにビジュアル レベル フィルターを追加できます。 

* 視覚エフェクトによって既に使われているフィールドにフィルターを追加します。
* 視覚エフェクトによってまだ使われていないフィールドを識別し、そのフィールドを**ビジュアル レベル フィルター** バケットに直接追加します。

ところで、この手順では小売りの分析サンプルを使用するので、よろしければダウンロードして同じように操作してみてください。 [小売りの分析のサンプル](sample-retail-analysis.md)はこちらからダウンロードできます。

### <a name="filter-the-fields-in-the-visual"></a>ビジュアルでフィールドをフィルター処理する


1. 選択**レポートの編集**編集ビューで、レポートを開きます。
   
   ![レポートの編集ボタン](media/power-bi-report-add-filter/power-bi-edit-view.png)

2. 視覚化およびフィルター ウィンドウとフィールド ウィンドウがまだ開いていない場合は開きます。
   
   ![ビジュアル化、フィルター、およびフィールド ペイン](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. ビジュアルを選んでアクティブにします。 ビジュアルで使用されているすべてのフィールドが **[フィールド]** ウィンドウに表示され、 **[フィルター]** ウィンドウの **[ビジュアル レベル フィルター]** の見出しにも一覧表示されます。
   
   ![ビジュアル レベル フィルターを選択します。](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. この時点で、視覚化によって既に使われているフィールドにフィルターを追加します。 
   
    **[ビジュアル レベル フィルター]** 領域まで下にスクロールし、矢印を選んでフィルター処理するフィールドを展開します。 この例では **StoreNumberName** をフィルター処理します。
     
    ![矢印は、フィルターを拡張します。](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
    
    フィルター処理コントロールとして**基本**、**高度**、または**上位 N** を設定します。 この例では、基本フィルターで **cha** を検索し、これら 5 つのストアを選択します。
     
    ![基本フィルターで検索します。](media/power-bi-report-add-filter/power-bi-search-filter.png) 
   
    ビジュアルに新しいフィルターが反映されます。 レポートをフィルターとともに保存すると、レポート閲覧者は、フィルター処理されたビジュアルが最初に表示され、読み取りビューでフィルターと対話して、値を選んだりクリアしたりすることができます。
     
    ![フィルター選択されたビジュアル](media/power-bi-report-add-filter/power-bi-search-visual-filter-results.png)

### <a name="filter-with-a-field-thats-not-in-the-visual"></a>ビジュアルに含まれていないフィールドでフィルター処理する

次に、新しいフィールドをビジュアル レベル フィルターとして視覚エフェクトに追加します。
   
1. [フィールド] ウィンドウで新しいビジュアル レベル フィルターとして追加するフィールドを選び、 **[ビジュアル レベル フィルター]** 領域までドラッグします。  この例では、**District Manager** を **[ビジュアル レベル フィルター]** バケットにドラッグし、「**an**」を検索して、それらの 3 人のマネージャーを選択します。 
     
    ![フィルター ペインにフィールドを追加します。](media/power-bi-report-add-filter/power-bi-search-add-visual-filter.png)

    **District Manager** は視覚エフェクト自体に追加されるのでは "*ない*" ことに注意してください。 視覚化はまだ **[StoreNumberName]** を軸とし、 **[This Year Sales (今年の売上)]** を値として構成されています。  
     
    ![ビジュアルにフィールドがないです。](media/power-bi-report-add-filter/power-bi-visualization.png)

    また、視覚エフェクト自体は、指定した店舗でのこれらのマネージャーの今年の売上だけを表示するようにフィルター処理されます。
     
    ![フィルター選択されたビジュアル](media/power-bi-report-add-filter/power-bi-search-visual-filter-results-2.png)

    レポートをフィルターとともに保存すると、レポート閲覧者は読み取りビューで **District Manager** フィルターを操作して、値を選んだりクリアしたりすることができます。

## <a name="add-a-filter-to-an-entire-page"></a>ページ全体にフィルターを追加する

追加することも、ページ レベル フィルターをフィルター処理ページ全体。

1. 選択**レポートの編集**編集ビューで、レポートを開きます。
   
   ![レポートの編集ボタン](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. 視覚化およびフィルター ウィンドウとフィールド ウィンドウがまだ開いていない場合は開きます。
3. [フィールド] ウィンドウで新しいページ レベル フィルターとして追加するフィールドを選び、 **[ページ レベル フィルター]** 領域までドラッグします。  
4. フィルターを適用する値を選び、フィルター処理コントロールとして**基本**または**高度**を設定します。
   
   変更を反映するように、ページ上のすべての視覚化が再描画されます。
   
   ![フィルターを追加し、値を選択します。](media/power-bi-report-add-filter/filterpage.gif)

    レポートをフィルターとともに保存すると、レポート閲覧者が読み取りビューでフィルターと対話でき、値を選んだりクリアしたりすることができます。

## <a name="add-a-drillthrough-filter"></a>ドリルスルー フィルターを追加する
Power BI サービスと Power BI Desktop のドリルスルーでは、サプライヤー、顧客、メーカーなど、特定のエンティティに注目した "*ドリルスルー先*" レポート ページを作成できます。 ユーザーは、他のレポート ページでそのエンティティのデータ ポイントを右クリックして、フォーカスされたページにドリルスルーできます。

### <a name="create-a-drillthrough-filter"></a>ドリルスルー フィルターを作成する
作業を進めるには、ダウンロード、[お客様の収益性サンプル](sample-customer-profitability.md)します。 Executive ビジネス領域に注目したページを作成します。

1. **[レポートの編集]** を選んで、編集ビューでレポートを開きます。
   
   ![レポートの編集ボタン](media/power-bi-report-add-filter/power-bi-edit-view.png)

1. レポートに新しいページを追加し、「**Team Executive**」という名前を付けます。 このページが "*ドリルスルー先*" になります。
2. チーム エグゼクティブ ビジネス分野の主要指標を追跡するための視覚化を追加します。    
3. [ドリル スルー フィルター] ウェルに **[Executive] > [Executive Name]** を追加します。    
   
    ![ドリルスルー フィルターに値を追加します。](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    レポート ページに戻る矢印が追加されることに注意してください。  戻る矢印を選ぶと、"*ドリルスルー元*" のレポート ページ (ドリルスルーを選んだときのページ) に戻ります。 戻る矢印は、読み取りビューでのみ機能します。
   
     ![戻る矢印](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>ドリルスルー フィルターを使う
ドリルスルー フィルターのしくみを見てみましょう。

1. **[Team Scorecard]** レポート ページから始めます。    
2. Andrew Ma が自分のデータだけにフィルター処理された [Team Executive] レポート ページを見たいものとします。  左上の面グラフで任意の緑のデータ ポイントを右クリックして、[ドリルスルー] メニュー オプションを開きます。
   
    ![ドリルスルー アクションを開始します。](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. **[ドリルスルー] > [Team Executive]** を選んで、 **[Team Executive]** という名前のレポート ページにドリルスルーします。 このページは、右クリックしたデータ ポイント (この場合は Andrew Ma) に関する情報を表示するようにフィルター処理されています。 ドリルスルー フィルターにあるフィールドのみが、ドリルスルー レポート ページに渡されます。  
   
    ![ドリルスルー アクションを選択します。](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-report-level-filter-to-filter-an-entire-report"></a>レポート レベル フィルターをフィルター処理全体のレポートを追加します。

1. **[レポートの編集]** を選んで、編集ビューでレポートを開きます。
   
   ![レポートの編集ボタン](media/power-bi-report-add-filter/power-bi-edit-view.png)

2. まだ開いていない場合は、視覚エフェクトとフィルター ウィンドウとフィールド ウィンドウを開きます。
3. [フィールド] ウィンドウで新しいレポート レベル フィルターとして追加するフィールドを選び、 **[レポート レベル フィルター]** 領域までドラッグします。  
4. フィルターする値を選択します。

    アクティブ ページおよびレポート内のすべてのページ上のビジュアルに、新しいフィルターが反映されます。 レポートをフィルターとともに保存すると、レポート閲覧者が読み取りビューでフィルターと対話でき、値を選んだりクリアしたりすることができます。

1. 戻る矢印を選んで、前のレポート ページに戻ります。

## <a name="considerations-and-troubleshooting"></a>考慮事項とトラブルシューティング

- ビジュアル レベル フィルターとページ レベル フィルターが異なる結果を返すことがあります。  たとえば、ビジュアル レベル フィルターを追加すると、Power BI は集計結果をフィルター処理します。  既定の集計は合計ですが、[集計の種類を変更](service-aggregates.md)することもできます。  

    その後、ページ レベル フィルターを追加すると、Power BI は集計せずにフィルター処理します。  集計しない理由は、それぞれが異なる集計の種類を利用するビジュアルが、多数ページに含まれている可能性があるためです。  そのため、フィルターは各データ行に適用されます。

- [フィールド] ウィンドウが表示されない場合は、レポートが[編集ビュー](service-interact-with-a-report-in-editing-view.md)になっていることを確認してください。    
- フィルターに多くの変更を加えた後で、レポート作成者の初期設定に戻す場合、一番上のメニュー バーから **[既定値にリセット]** を選択します。

## <a name="next-steps"></a>次の手順
[レポート フィルター ウィンドウの使用方法](consumer/end-user-report-filter.md)

[レポート内のフィルターと強調表示](power-bi-reports-filters-and-highlighting.md)

[レポートの読み取りビューでのフィルターとの対話と強調表示](consumer/end-user-reading-view.md)

[レポートのビジュアル相互間のクロスフィルター処理とクロス強調表示を変更する方法](consumer/end-user-interactions.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

