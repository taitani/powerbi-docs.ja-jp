---
title: Power BI でレポートを表示する
description: Power BI のレポート
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 5/10/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 02652bd027d7dab8a40d77fb92c5aae8f09d8820
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607904"
---
# <a name="reports-in-power-bi"></a>Power BI のレポート
## <a name="what-is-a-power-bi-report"></a>Power BI レポートとは
Power BI***レポート***がデータセットにそのデータセットからさまざまな発見や洞察を表すビジュアルを表示します。  レポートには、1 つのビジュアルやページのビジュアルの完全なを持つことができます。 、職務に応じて、ユーザーをする可能性がありますユーザー*設計*レポートがだれかがありますユーザー*消費*またはレポートを使用します。

![レポート ページ](./media/end-user-reports/power-bi-report.png)

このレポートには 6 つのページ (またはタブ) と、センチメント ページを現在表示していること。 このページには 6 つの異なる視覚エフェクトとページ タイトルです。  

Power BI を初めて使うときは、「[Power BI - 基本的な概念](end-user-basic-concepts.md)」を読むと基礎がよくわかります。

レポートは、表示、共有、およびモバイル デバイスで注釈を付けることができます。 詳細については、次を参照してください。[モバイル レポートを Power BI](mobile/mobile-reports-in-the-mobile-apps.md)します。

## <a name="advantages-of-reports"></a>レポートの利点
レポートは、単一のデータセットに基づいています。 レポートでのビジュアルがレポートで作成された*デザイナー*をひとかたまりの情報を表します。 ビジュアルは静的です。洞察し、答えを探すにデータを掘り下げていくと、ビジュアル フィルターと対話できます。 ダッシュ ボードのような対話性の高い、高度にカスタマイズ可能なレポートよりこれにより、し、ビジュアルの基になるデータの変化に応じて更新します。

### <a name="safely-interact-with-content"></a>コンテンツを安全に操作する
調査して、コンテンツ、フィルター処理、スライス、サブスクライブ、およびエクスポート、安心; との対話職場では、基になるデータセットまたは元の共有コンテンツ (ダッシュ ボード、レポート、およびアプリ) には影響しません。
 
> [!NOTE]
> ただし、データが低下することはできません。 Power BI は、探索および「を破損する」何も心配することがなく実験するための優れた場所です。

### <a name="save-your-changes-or-revert-to-the-default-settings"></a>変更を保存または既定の設定に戻す
しないわけでは、変更を保存することはできません。できますが、それらの変更は、コンテンツの表示のみに影響します。 元の既定のビューに戻すことは、既定のボタンを選択することだけです。

## <a name="dashboards-versus-reports"></a>ダッシュボードとレポート
[ダッシュ ボード](end-user-dashboards.md)は、表示されたビジュアル キャンバスがあるために多くの場合、レポートと混同します。 しかし、大きな違いがいくつかあります。  

| **機能** | **ダッシュボード** | **レポート** |
| --- | --- | --- |
| ページ |1 ページ |1 ページ以上 |
| データ ソース |ダッシュボードごとに、1 つ以上のレポートおよび 1 つ以上のデータセット |レポートごとに 1 つのデータセット |
| フィルター処理 |フィルター処理またはスライスはできません |さまざまな方法でフィルター処理、強調表示、スライスできます |
| 通知の設定 |特定の条件が満たされたときにユーザーにメールを送る通知を作成できます |いいえ |
| おすすめ |1 つのダッシュボードを "おすすめの" ダッシュボードとして設定できます |おすすめのレポートを作成することはできません |
| 基になっているデータセットのテーブルとフィールドの表示 |いいえ。 データをエクスポートすることができますが、データセットのテーブルとダッシュ ボード自体のフィールドを表示することはできません。 |はい。 データセットのテーブルとフィールドを表示するアクセス許可を持つ値を確認できます。 |
| カスタマイズ |いいえ  |できますをフィルター処理、エクスポート、関連するコンテンツを表示、ブックマークを追加、QR コードの生成、excel などの分析します。   |

<!--| Available in Power BI Desktop |No |Yes, can create and view reports in Desktop |
| Pinning |Can pin existing visuals (tiles) only from current dashboard to your other dashboards |Can pin visuals (as tiles) to any of your dashboards. Can pin entire report pages to any of your dashboards. | -->

## <a name="report-creators-and-report-consumers"></a>レポート***作成者***とレポート ***コンシューマー***
によって、ロールができます、*デザイナー*、自分の使用や同僚と共有するレポートを作成します。 レポートを作成して共有する方法を覚えておく必要があります。 また、他のユーザーからレポートを受け取る場合もあるため、 レポートを理解し、処理する方法を知る必要があります。 レポートをする場合は**コンシューマー**、これらのリンクがするは。 

* まず、[Power BI サービスのツアー](end-user-basic-concepts.md)を利用して、レポートとレポート ツールをどこで探せばよいかを理解します。
* [レポートを開く](end-user-report-open.md)方法と、[読み取りビュー](end-user-reading-view.md)で実行できるすべての対話的操作について学習します。
* いずれかの[サンプル](../sample-tutorial-connect-to-the-samples.md)のツアーを利用してレポートに慣れます。  
<!--* Don't need the report any more? You can [remove it](../service-delete.md).-->
* レポートでどのデータセットが使われているか、また、どのダッシュボードにレポートからタイルがピン留めされているかを確認するには、[関連するコンテンツを表示](end-user-related.md)します。

> [!TIP]
> 知りたいことがここで見つからない場合は、左側の目次を使用して、*レポート*に関するすべてのトピックから探してください。
> 
> 

## <a name="next-steps"></a>次の手順
[Power BI とは?](../power-bi-overview.md) 

[Power BI - 基本的な概念](end-user-basic-concepts.md)

