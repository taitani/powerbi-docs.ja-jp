---
title: 追加の診断情報のキャプチャ
description: 追加の診断情報のキャプチャ
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: b38e1e73b9829b4b86237f826b4245a6b95cfa36
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54292938"
---
# <a name="capturing-additional-diagnostic-information"></a>追加の診断情報のキャプチャ
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Power BI 用に追加の診断情報をキャプチャする
次の手順では、Power BI Web クライアントから追加の診断情報を手動で収集するために可能性のある 2 つのオプションを提供します。  いずれかのオプションを実行すれば十分です。

## <a name="network-capture---edge--internet-explorer"></a>ネットワーク キャプチャ - Edge および Internet Explorer
1. Edge または Internet Explorer で [Power BI](https://app.powerbi.com) を参照します。
2. F12 キーを押して Edge 開発者ツールを開きます。
3. 開発者ツール ウィンドウが表示されます。 
   
   ![開発者向けツール](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. [ネットワーク] タブに切り替えます。既ににキャプチャされたトラフィックが一覧表示されます。 
   
   ![Edge の [ネットワーク] タブ](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. ウィンドウを参照して、発生している可能性がある問題を再現できます。 セッション中にいつでも F12 キーを押して、開発者ツール ウィンドウの表示/非表示を切り替えることができます。
6. キャプチャを停止するには、開発者ツール領域の [ネットワーク] タブの赤い四角形を選択します。
   
   ![キャプチャの停止](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. **HAR としてエクスポート**するにはフロッピー ディスクのアイコンを選択します。
   
   ![ファイルのエクスポート](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. ファイル名を指定し、HAR ファイルを保存します。
   
    HAR ファイルには、ブラウザー ウィンドウと Power BI の間のネットワーク要求に関するすべての情報が含まれます。  それには、各要求のアクティビティ ID、各要求の正確なタイムスタンプ、クライアントに返されるエラー情報が含まれます。  このトレースには、画面に表示されるビジュアルを設定するのに使われるデータも含まれます。
9. サポートのレビュー用にも HAR ファイルを提供できます。

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

