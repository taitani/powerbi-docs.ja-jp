---
title: Power BI Embedded のパフォーマンスのベスト プラクティス
description: この記事では、埋め込み分析のベスト プラクティスについて説明します
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: 50fbb175640e38431db62df34276417f1080e42a
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2019
ms.locfileid: "55430352"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Power BI Embedded のパフォーマンスのベスト プラクティス

この記事では、アプリケーションでレポート、ダッシュボード、タイルを短時間で表示するための推奨事項を紹介しています

## <a name="embed-parameters"></a>埋め込みパラメーター

Powerbi.embed() メソッドはレポート、ダッシュボード、タイルを埋め込む目的でいくつかのパラメーターを受け取ります。 そのようなパラメーターはパフォーマンスに関係してきます。

### <a name="embed-url"></a>埋め込み URL

埋め込み URL を自分で生成することは避けてください。 その代わりに、[レポートの取得](/rest/api/power-bi/reports/getreportsingroup)、[ダッシュボードの取得](/rest/api/power-bi/dashboards/getdashboardsingroup)、[タイルの取得](/rest/api/power-bi/dashboards/gettilesingroup) API を呼び出す方法で埋め込み URL を用意してください。 Microsoft は **_config_** という名称の新しいパラメーターを URL に追加しました。これはパフォーマンス改善に利用されます。

### <a name="permissions"></a>アクセス許可

**編集モード**でレポートを埋め込まないのであれば、**表示**アクセス許可を与えます。 この方法では、編集モードで使用されるコンポーネントが埋め込みコードによって初期化されることがありません。

### <a name="filters-bookmarks-and-slicers"></a>フィルター、ブックマーク、スライサー

通常、レポート ビジュアルはデータをキャッシュすることで保存されます。 データのキャッシュはパフォーマンスの改善を体感させます。 レポートでは、クエリが実行される間、キャッシュされたデータがレンダリングされます。 フィルター、ブックマーク、またはスライサーが与えられる場合、キャッシュされたデータは使われません。 ビジュアルは、ビジュアル クエリの実行後に初めてレンダリングされます。

同じフィルターを利用してレポートを埋め込む場合、読み込み構成でフィルターの一覧を渡さないよう、フィルターを既に適用している状態でレポートを保存します。

## <a name="preload"></a>事前読み込み

*事前読み込み* JavaScript API を使用し、エンドユーザー パフォーマンスを改善します。
Powerbi.preload() によって後でレポートに埋め込む javascript、css ファイル、その他の成果物がダウンロードされます。

レポートをすぐに埋め込まない場合、事前読み込みを呼び出します。 たとえば、ボタン クリックでレポートを埋め込む場合、前のページが読み込まれるときに事前読み込みを呼び出すことが推奨されます。 アプリケーションの利用者がボタンをクリックしたとき、レンダリングが速くなります。

## <a name="measure-performance"></a>パフォーマンスの計測

パフォーマンスを計測する目的で次が利用されます。

1. [Loaded]\(読み込み完了\): レポートが初期化される (待機カーソルの表示が消える) までの時間。
2. [Rendered]\(レンダリング完了\): 実際のデータを利用し、完全なレポートがレンダリングされるまでの時間。 レポートが再度レンダリングされるたびに (つまり、フィルターの適用後) レンダリング完了イベントが発生します。 最初にレポートを計測するには、最初に発生したイベントで計算を行います。

データがキャッシュされている場合、それがレンダリングされますが、キャッシュされたデータのイベントは現在のところありません。

## <a name="update-tools-and-sdk-packages"></a>ツールと SDK パッケージを更新する

ツールと SDK パッケージを最新の状態で維持します。

* 最新版の [Power BI Desktop](https://powerbi.microsoft.com/desktop/) を常に使用してください。

* 最新版の [Power BI クライアント SDK](https://github.com/Microsoft/PowerBI-JavaScript) をインストールします。 今後も拡張機能が追加リリースされます。折に触れて最新の状態に更新してください。

* インストールするパッケージ:
    * NPM パッケージ: powerbi-client
    * NuGet パッケージ:Microsoft.PowerBI.JavaScript

> [!Note]
> 読み込み時間は主に、レポートとデータ自体に関連する要素に依存することを思い出してください。 ビジュアルの数、データのサイズ、クエリと計算方法の複雑性などです。 [ベスト プラクティス](../power-bi-reports-performance.md)を実行し、レポートの読み込み時間を改善してください。

## <a name="next-steps"></a>次の手順

* [Power BI レポートのパフォーマンスのベスト プラクティス](../power-bi-reports-performance.md)
* [Power BI Embedded の問題を解決する方法](embedded-troubleshoot.md)
* [Power BI Embedded のよくあるご質問](embedded-faq.md)
