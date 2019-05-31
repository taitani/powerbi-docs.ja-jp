---
title: フィルターと Power BI レポートで強調表示
description: Power BI レポートのフィルターと強調表示について
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 8084b8dbbc27c856633d84c6628727dcd426964d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187554"
---
# <a name="filters-and-highlighting-in-power-bi-reports"></a>フィルターと Power BI レポートで強調表示
 この記事では、フィルター処理と、Power BI サービスで強調表示することについて説明します。 操作は Power BI Desktop の場合とほぼ同じです。 *フィルター処理*を実行すると、絞り込んだデータ以外のすべてのデータが削除されます。 *強調表示*フィルターはありません。 代わりに表示されるデータのサブセットが強調表示されますが、データが削除されません。強調表示されていないデータは、表示が淡色表示に残ります。

Power BI ではさまざまな方法でレポートをフィルター処理および強調表示できます。 すべての情報をまとめて説明すると混乱するので、以下のセクションに分けて説明します。

* フィルターと強調表示の概要、記事をご覧になっているようになりました。
* 方法[作成し、編集ビューでフィルターを使用して](power-bi-report-add-filter.md)で Power BI Desktop と Power BI サービスでのレポート。 レポートの編集アクセス許可がある場合、レポートでフィルターを作成、変更、削除できます。
* どのビジュアル[をフィルター処理し、共有したレポートで強調表示](consumer/end-user-interactions.md)で、レポートの Power BI サービスでの読み取りビュー。 できることには限りがありますが、それでもさまざまなフィルター処理と強調表示のオプションを使用できます。  
* 詳細なツアー、[フィルターと編集ビューで使用できるコントロールを強調表示](power-bi-report-add-filter.md)Power BI Desktop と Power BI サービスでします。 記事では、日付と時刻、数値などのフィルターの種類の詳細およびテキストを受け取ります。 基本および詳細なオプションの違いについても説明します。
* フィルターと強調表示の既定の動作を理解した後は、[ページの視覚エフェクトが相互にフィルターおよび強調表示する方法を変更する](service-reports-visual-interactions.md)方法を学習してください

**ご存知でしたか?** Power BI には新しいフィルター エクスペリエンスがあります (現在プレビュー段階)。 詳細については、[Power BI レポートの新しいフィルター エクスペリエンス](power-bi-report-filter-preview.md)に関する記事をご覧ください。

![新しいフィルター エクスペリエンス](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading.png)


## <a name="intro-to-the-filters-pane"></a>フィルター ウィンドウの概要

**[フィルター]** ウィンドウで、またはレポート自体で直接[スライサーを使って選択する](visuals/power-bi-visualization-slicers.md)ことにより、フィルターを適用することができます。 フィルター ウィンドウには、レポートで使用されているテーブルとフィールド、および適用されているフィルター (ある場合) が表示されます。 

![フィルター ウィンドウ](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

フィルターには次の 4 つの種類があります。

- **ページ フィルター**は、レポート ページ上のすべてのビジュアルに適用されます。     
- **ビジュアル フィルター**は、レポート ページ上の単一のビジュアルに適用されます。 レポート キャンバスでビジュアルを選択した場合は、ビジュアル レベル フィルターだけが表示されます。    
- **レポート フィルター**は、レポート内のすべてのページに適用されます。    
- **ドリルスルー フィルター**は、レポート内の単一のエンティティーに適用されます。    

読み取りビューまたは編集ビューで、ページ フィルター、ビジュアル フィルター、レポート フィルターを使用して検索を行い、目的の値を探して選択できます。 

![フィルターで検索する](media/power-bi-reports-filters-and-highlighting/power-bi-search-filter.png)

フィルターに**すべて**と表示されている場合は、フィールドのすべての値がフィルターに含まれることを意味します。  たとえば、次のスクリーンショットの **[Chain(All)]\(Chain は (すべて) です\)** は、このレポート ページにすべてのストア チェーンに関するデータが含まれることを意味します。  一方、レポート レベル フィルターの **[FiscalYear is 2013 or 2014]\(FiscalYear が 2013 または 2014 である\)** は、レポートに 2013 年および 2014 年の会計年度のデータのみが含まれることを示します。

## <a name="filters-in-reading-or-editing-view"></a>読み取りビューまたは編集ビューでのフィルター
レポートとの対話には次の 2 つのモードがあります:[読み取りビュー](consumer/end-user-reading-view.md)と編集ビュー。 使用できるフィルター処理機能は、どのモードを使用しているかによって異なります。

* 編集ビューでは、レポート、ページ、ドリルスルー、ビジュアルの各フィルターを追加できます。 モバイル アプリで開く場合でも、レポートを保存すると、フィルターはレポートと共に保存されます。 読み取りビューでレポートを表示しているユーザーは、追加したフィルターと対話できますが、新しいフィルターを追加することはできません。
* 読み取りビューでは、レポートに既に存在するすべてのフィルターと対話して、行った選択の内容を保存することができます。 新しいフィルターを追加することはできません。

### <a name="filters-in-reading-view"></a>読み取りビューでのフィルター
読み取りビューでしかレポートにアクセスできない場合、フィルター ウィンドウは次のようになります。

![読み取りビューでのフィルター](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

レポートのこのページには、6 個のページ レベル フィルターと 1 個のレポート レベル フィルターがあります。

各ビジュアルではビジュアル内のすべてのフィールドにフィルターを設定でき、レポート作成者はさらに追加できます。 次の図では、バブル チャートに 6 個のフィルターがあります。

![ビジュアル レベル フィルター](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

読み取りビューでは、既存のフィルターを変更することによってデータを調べます。 モバイル アプリでレポートを開く場合でも、加えた変更の内容はレポートと共に保存されます。 方法については、「[レポート フィルター ウィンドウの使用方法](consumer/end-user-report-filter.md)」をご覧ください

レポートの終了時に、フィルターが保存されます。 フィルター処理を取り消し、レポート作成者が設定したフィルター処理、スライス、ドリル、並べ替えに戻すには、一番上のメニュー バーから **[既定値にリセット]** を選択します。

![既定のアイコンにリセットします。](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

### <a name="filters-in-editing-view"></a>編集ビューでのフィルター
レポートに対する所有者権限を持つユーザーが編集ビューでレポートを開くと、**フィルター**は使用可能な複数の編集ウィンドウの 1 つとして表示されます。

![編集ビューでフィルター ウィンドウ](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

読み取りビューと同じように、レポートのこのページには、6 個のページ レベル フィルターと 1 個のレポート レベル フィルターがあります。 また、バブル チャートを選択すると、6 個のビジュアル レベル フィルターが適用されていることがわかります。

編集ビューでは、フィルターと強調表示に関してさらに多くのことができます。 まず第一に、新しいフィルターを追加できます。 その方法と他の機能については、「[レポートにフィルターを追加する](power-bi-report-add-filter.md)」をご覧ください。

## <a name="ad-hoc-highlighting"></a>アドホックの強調表示
ビジュアル、ページ上の他のビジュアルを強調表示するには、値または軸のラベルを選択します。 強調表示を削除するには、値をもう一度選択するか、同じビジュアルの空いている領域を選択します。 楽しいを強調表示がデータの影響をすばやく探索する方法。 この種のクロス強調表示を微調整する場合は、「[Power BI レポートでの視覚化の相互作用](service-reports-visual-interactions.md)」をご覧ください。

![クロス強調表示](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)


## <a name="next-steps"></a>次の手順

[Power BI レポートで、新しいフィルター エクスペリエンス](power-bi-report-filter-preview.md)

[レポートへのフィルターの追加 (編集ビュー)](power-bi-report-add-filter.md)

[レポート フィルターの使用方法](consumer/end-user-report-filter.md)

[レポートのビジュアル相互間のクロスフィルター処理とクロス強調表示を変更する方法](consumer/end-user-interactions.md)

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

