---
title: Performance Analyzer を使用して、Power BI Desktop でレポート要素のパフォーマンスを確認するには
description: リソース使用率と応答性の観点からビジュアルとレポート要素の実行状況を調べる
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1851e0a55bf01073a6591f64de43830a72eca89b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65854415"
---
# <a name="use-performance-analyzer-to-examine-report-element-performance"></a>レポート要素のパフォーマンスを確認するのに Performance Analyzer を使用します。

**Power BI Desktop**見つかりますビジュアルや DAX の数式など、レポートの要素ごとの実行状況を出力します。 使用して、 **Performance Analyzer**を確認し、レコードのログが、それらをユーザーが対話するときをレポート要素の各実行する方法を測定し、パフォーマンスのどの側面がほとんど (またはそれ以降) のリソースを消費します。

![パフォーマンス アナライザー](media/desktop-performance-analyzer/performance-analyzer-01.png)

Performance Analyzer は、検査し更新、またはすべてのビジュアルを更新するために必要な期間の開始、そのユーザーの操作を表示し、表示、ドリルダウン、または結果をエクスポートするための情報を表示します。 Performance Analyzer は、レポートのパフォーマンスに影響を与えるビジュアルを特定し、影響の原因を特定できます。

## <a name="displaying-the-performance-analyzer-pane"></a>Performance Analyzer ウィンドウの表示

**Power BI Desktop**選択、**ビュー**リボンです。 **表示**の領域、**ビュー**リボンの横にチェック ボックスを選択することができます**Performance Analyzer** Performance Analyzer ウィンドウを表示します。

![[表示] リボンでパフォーマンス アナライザーを選択します。](media/desktop-performance-analyzer/performance-analyzer-02.png)

選択すると、レポート キャンバスの右側に、独自のウィンドウで、パフォーマンス アナライザーが表示されます。

## <a name="using-performance-analyzer"></a>Performance Analyzer を使用します。

クエリを実行して結果を任意のユーザー操作の結果が開始したレポート要素を更新するアナライザーのパフォーマンスの測定 (作成またはビジュアルを更新する時間を含む) の処理時間が必要です。 たとえば、スライサーを調整することは、視覚的要素の影響を受ける、新しい設定の結果として更新する必要がありますスライサーにビジュアルを変更、データ モデルに送信されるクエリが必要です。 

録画を開始します Performance Analyzer には、単に選択**の記録を開始**

![記録を開始します。](media/desktop-performance-analyzer/performance-analyzer-03.png)

レポートのアクションが表示され、Performance Analyzer ウィンドウで、Power BI でビジュアルが読み込まれている順序でログに記録します。 たとえば、おそらくレポートがあるユーザーでは、更新に時間がかかると言うべきです。 または、特定のビジュアルをレポートで、スライダーを調整するときに表示される時間がかかります。 処理する最も長い時間がかかって visual 原因、およびビジュアルの要素を識別するには、パフォーマンス アナライザーがわかります。 

記録を開始すると、**の記録を開始**ボタンは淡色表示にアウト (記録を開始済みであるためは非アクティブ)、**停止**ボタンがアクティブにします。 

パフォーマンス アナライザーは、収集し、リアルタイムでパフォーマンスの測定の情報が表示されます。 ビジュアルでクリックするたびに、スライサーを移動したり、他の方法で対話 Performance Analyzer はパフォーマンスの結果をすぐにペインに表示します。

ウィンドウに表示できるより多くの情報がある場合は、追加情報に移動するスクロール バーが表示されます。

各操作では、ログ エントリを開始したアクションを記述するウィンドウでセクション識別子があります。 次の図では、相互作用は、ユーザーがスライサーを変更することでした。

![対話型に基づいてセクション](media/desktop-performance-analyzer/performance-analyzer-04.png)

各ビジュアルのログ情報が含まれます (期間)、次のカテゴリのタスクを完了します。

* **DAX クエリ**-これは、クエリを送信して、ビジュアル間および結果を返すための Analysis Services で DAX クエリが必要な場合。
* **ビジュアル表示**-web 画像やジオコーディングの取得に必要な時間を含む、画面に描画するために、ビジュアルに必要な時間。 
* **その他の**-その他のバック グラウンド処理を実行するクエリを準備する、他のビジュアルを完了するを待つまたはビジュアルで必要な時間。

![ログ情報の要素](media/desktop-performance-analyzer/performance-analyzer-06.png)

アナライザーのパフォーマンスを測定するレポートの要素を対話して後、は、選択、**停止**ボタンをクリックします。 パフォーマンス情報は、選択した後、ウィンドウに残ります**停止**を分析するためです。

Performance Analyzer ウィンドウで情報をクリアするには、選択**オフ**します。 すべての情報が削除され、選択したときに保存されません**クリア**します。 ログに情報を保存する方法については、次のセクションを参照してください。 

## <a name="refreshing-visuals"></a>ビジュアルを更新します。

選択することができます**ビジュアルの更新**をすべてのビジュアル、レポートの現在のページを更新し、それによってこのようなすべてのビジュアルに関する情報を収集するパフォーマンス アナライザーがある Performance Analyzer ウィンドウにします。

個々 のビジュアルを更新することもできます。 アナライザーのパフォーマンスを記録すると、するときに選択できます**このビジュアルを更新**、そのビジュアルを更新する各ビジュアルの右上隅にあるし、そのパフォーマンス情報をキャプチャします。

![個々 のビジュアルを更新します。](media/desktop-performance-analyzer/performance-analyzer-07.png)

## <a name="saving-performance-information"></a>パフォーマンス情報の保存

レポートに関するパフォーマンス アナライザーを作成する情報を保存するには選択して、**エクスポート**ボタンをクリックします。 選択**エクスポート**Performance Analyzer ウィンドウからの情報を含む .json ファイルを作成します。 

![パフォーマンス アナライザーは、ログ ファイルを保存します。](media/desktop-performance-analyzer/performance-analyzer-05.png)


## <a name="next-steps"></a>次の手順
**Power BI Desktop** と作業の開始方法の詳細については、次の記事を確認してください。

* [Power BI Desktop とは何ですか?](desktop-what-is-desktop.md)
* [Power BI Desktop でのクエリの概要](desktop-query-overview.md)
* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop におけるデータへの接続](desktop-connect-to-data.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop での一般的なクエリ タスク](desktop-common-query-tasks.md)   

