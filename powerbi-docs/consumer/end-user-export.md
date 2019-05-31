---
title: Power BI ビジュアルからデータをエクスポートする
description: レポートのビジュアルとダッシュ ボードのビジュアルからデータをエクスポートし、Excel で表示します。
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 4/9/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: d4384db8e05a69b138e76377e7c7b845867fa881
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "61063847"
---
# <a name="export-data-from-visual"></a>ビジュアルからデータをエクスポートします。
ビジュアルを作成するために使用するデータを表示したい場合[Power BI でデータを表示できる](end-user-show-data.md)またはそのデータを Excel にエクスポートします。 データをエクスポートするオプションは、特定の種類またはライセンスが必要ですし、コンテンツへのアクセス許可を編集します。 、エクスポートできない場合は、Power BI 管理者に確認します。 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Power BI のダッシュ ボードのビジュアルから

1. Power BI ダッシュ ボードを起動します。 ここからダッシュ ボードを使います、***マーケティングと売上のサンプル***アプリ。 できます[AppSource.com からこのアプリをダウンロード](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282)します。

    ![](media/end-user-export/power-bi-dashboard.png)

2. 省略記号 (...) を表示するビジュアルをポイントし、操作 メニューを表示する をクリックします。

    ![](media/end-user-export/power-bi-dashboard-export-visual.png)

3. 選択**を Excel にエクスポート**します。

4. 次の動作は、使用しているブラウザーによって異なります。 ファイルまたはことがありますを保存するよう指示することがあります、ブラウザーの下部にあるエクスポートされたファイルへのリンクを参照してください。 

    ![](media/end-user-export/power-bi-export-browser.png)

5. Excel でファイルを開きます。  

    ![](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>レポートのビジュアルから
レポートのビジュアルからデータをエクスポートする .csv ファイルまたは .xlsx (Excel) としてフォーマットします。 

1. ダッシュ ボードでは、基になるレポートを開く タイルを選択します。  この例では、選択同じビジュアル、上記と*合計ユニット YTD Var %* します。 

    ![](media/end-user-export/power-bi-export-report.png)

    このタイルがから作成されたため、*売上およびマーケティングのサンプル*レポート、レポートが開きます。 選択したタイルのビジュアルを含むページが開きます。 

2. レポートのタイルを選択します。 通知、**フィルター**右側のウィンドウ。 このビジュアルは、フィルターを適用します。 フィルターの詳細については、次を参照してください。[レポートにフィルターを使用して](end-user-report-filter.md)します。

    ![](media/end-user-export/power-bi-export-filters.png)


3. ビジュアルの右上隅にある省略記号を選択します。 選択**データ エクスポート**します。

    ![](media/end-user-export/power-bi-export-report2.png)

4. 要約されたデータ、または基になるデータをエクスポートするオプションが表示されます。 使用している場合、*売上およびマーケティングのサンプル*アプリ、**基になるデータ**は無効になります。 両方のオプションが有効になっているレポートが発生する可能性があります。 相違点の説明を次に示します。

    **集計データ**: ビジュアルに表示される内容のデータをエクスポートする場合は、このオプションを選択します。  この種類のエクスポートでは、ビジュアルの作成に使用されたデータのみを表示します。 ビジュアルに適用されるフィルターがある場合、エクスポートするデータはフィルターもいます。 たとえば、このビジュアルでは、エクスポートが 2014年用のデータと、中央の領域とのみデータのみ、製造元の 4 つの含めます。Vanarsdel 社、Natura、Aliqui、および Prirum します。
  

    **基になるデータ**: ビジュアルに表示される内容のデータをエクスポートする場合は、このオプションを選択**plus**基になるデータセットからデータを追加します。  データでは、データセットに含まれるが、ビジュアルで使用されていない場合があります。 

    ![](media/end-user-export/power-bi-export-report3.png)

5. 次の動作は、使用しているブラウザーによって異なります。 ファイルまたはことがありますを保存するよう指示することがあります、ブラウザーの下部にあるエクスポートされたファイルへのリンクを参照してください。 

    ![](media/end-user-export/power-bi-export-edge.png)


7. Excel でファイルを開きます。 データの同じダッシュ ボードのビジュアルからエクスポートするエクスポートされたデータの量を比較します。 違いは、このエクスポートが含まれている**基になるデータ**します。 

    ![](media/end-user-export/power-bi-underlying.png)

