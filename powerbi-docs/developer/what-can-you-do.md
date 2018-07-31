---
title: Power BI の開発者向け機能
description: Power BI には、開発者向けのさまざまなオプションがあります。 たとえば、埋め込み、カスタム ビジュアル、ストリーミング データセットなどです。
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 07fb8d365a6fe4a874b057a71a90a99fc8a9e5fa
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34564698"
---
# <a name="what-can-developers-do-with-power-bi"></a>Power BI の開発者向け機能

開発者は、さまざまな方法で、アプリケーションに Power BI コンテンツを含めることができます。 これらの方法には、**Power BI での埋め込み**、**カスタム ビジュアル**、および**Power BI へのデータのプッシュ**があります。

## <a name="embedding"></a>埋め込み
Power BI サービス (SaaS) と Azure (PaaS) の Power BI Embedded サービスには、ダッシュボードとレポートの埋め込み用の API があります。 これは、コンテンツを埋め込む際に、ダッシュボード、ゲートウェイ、アプリ ワークスペースなどの最新の Power BI 機能を用意してそれらにアクセスできることを意味します。

[オンボード エクスペリエンス ツール](https://aka.ms/embedsetup)に移動し、すばやく開始してサンプル アプリケーションをダウンロードすることができます。

適切なソリューションを選択します。
* [顧客向けの埋め込み](embedding.md#embedding-for-your-customers)では、Power BI のアカウントがないユーザーのためにダッシュボードとレポートを埋め込むことができます。 [顧客向けの埋め込み](https://aka.ms/embedsetup/AppOwnsData)ソリューションを実行します。
* [組織向けの埋め込み](embedding.md#embedding-for-your-organization)を使って、Power BI サービスを拡張することができます。 [組織向けの埋め込み](https://aka.ms/embedsetup/UserOwnsData)ソリューションを実行します。

![PBIE サンプル](media/what-can-you-do/what-can-you-do-02.png)

## <a name="develop-custom-visuals"></a>カスタム ビジュアルを作成する
カスタム ビジュアルを使うと、Power BI レポート内で使う独自のビジュアルを作成できます。 カスタム ビジュアルは、JavaScript のスーパーセットである TypeScript で記述されています。 TypeScript は、いくつかの高度な機能と ES6/ES7 機能への早期アクセスをサポートしています。 ビジュアルのスタイル設定は、カスケード スタイル シート (css) を使用して処理されます。 便宜を図るために、いくつかの高度な機能 (入れ子、変数、条件、ループなど) をサポートする Less プリコンパイラが使用されています。これらの機能を使用しない場合は、Less ファイル内にプレーンな css だけを記述します。

![CV サンプル](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Power BI にデータをプッシュする
Power BI API を使って、データセットにデータをプッシュできます。 これにより、データセット内のテーブルに行を追加できます。 ダッシュボードのタイルやレポートのビジュアルに新しいデータを反映できます。

![サンプル データ をプッシュする](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>次の手順
[Power BI で埋め込み](embedding.md)  
[カスタム ビジュアルを Office ストアに発行する](office-store.md)  
[ダッシュボードにデータをプッシュする](walkthrough-push-data.md)
