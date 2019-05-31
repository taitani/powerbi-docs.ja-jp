---
title: Power BI サービスでの改ページ調整されたレポートをサブスクライブするには
description: この記事では、Power BI サービスでの改ページ調整されたレポートのサブスクライブについて留意すべき点について説明します。
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: ccec6658808d94728f2a4f14de67c36da0f51def
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222194"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Power BI サービスでの改ページ調整されたレポートを自分や他のユーザーを購読します。 

Power BI サービスでの改ページ調整されたレポートの自分や他のユーザーの電子メール サブスクリプションを設定することができますようになりました。 一般に、プロセスは同じ[レポートと Power BI サービスでダッシュ ボードへのサブスクライブ](service-report-subscribe.md)します。 この記事では、違いと考慮事項について詳しく説明します。 

メールの受信するどのくらいの頻度を選択するサブスクリプションを設定: 毎日、毎週、または 1 時間ごと。 選択すると、毎日または毎週、時間を選択できるかどうかを実行するサブスクリプション。 すべてでは、すべてのレポートの 1 日あたりの最大 24 の異なるサブスクリプションを設定できます。 

## <a name="considerations-for-paginated-report-subscriptions"></a>改ページ調整されたレポートのサブスクリプションに関する考慮事項 

- ダッシュ ボードまたは Power BI レポートのサブスクリプションとは異なり、サブスクリプションには、レポート全体の出力の添付ファイルが含まれています。  次の添付ファイルの種類がサポートされています。PDF、PowerPoint プレゼンテーション (PPTX)、Excel ブック (XLSX)、Word 文書 (DOCX)、CSV ファイル、および XML。

- 電子メールの本文にレポートのプレビュー イメージはありません。  省略可能なアイテムとしてレポートの最初のページのイメージを用意する予定です。 

- レポートの最大添付ファイルのサイズは、25 MB です。 

- Azure Analysis Services または Power BI のデータセットを含む、現在サポートされているデータ ソースに接続する改ページ調整されたレポートの他のユーザーをサブスクライブすることができます。 SQL Server Reporting Services は現在と同様、レポートの添付ファイルが、アクセス許可に基づいて、データを反映するために留意してください。 

- レポートの名前には、レポート ページのサブスクリプションが関連付けられています。  

- メール サブスクリプションは、レポートの既定のパラメーター値で送信されます。 

- ない**データ更新の後に**オプションのページ分割されたレポートの頻度。 常に最新の値を基になるデータ ソースから取得します。 

## <a name="next-steps"></a>次の手順

[自分や他のユーザーをサブスクライブするレポートと Power BI サービスでダッシュ ボード](service-report-subscribe.md)

[Power BI Premium のページ分割されたレポートとは(プレビュー)](paginated-reports-report-builder-power-bi.md)
