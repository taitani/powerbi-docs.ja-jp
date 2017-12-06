---
title: "Power BI Desktop で Impala データベースに接続する"
description: "Power BI Desktop で Impala データベースに簡単に接続して使用する"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 80460bbcf8fb61bc8149304b3be359cd744c1b75
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2017
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Power BI Desktop で Impala データベースに接続する
Power BI Desktop では、**Impala** データベースに接続し、Power BI Desktop の他のデータ ソースの場合と同様に基になっているデータを使用できます。

## <a name="connect-to-an-impala-database"></a>Impala データベースに接続する
**Impala** データベースに接続するには、Power BI Desktop の **[ホーム]** リボンで **[データの取得]** を選択します。 左側のカテゴリから **[データベース]** を選択します。**[Impala]** が表示されます。

![](media/desktop-connect-impala/connect_impala_2.png)

表示された **[Impala]** ウィンドウ内のボックスに Impala サーバーの名前を入力するか、貼り付けます。**[OK]** をクリックします。 Power BI にデータを直接**インポート**したり、**DirectQuery** を使用したりできます。 詳しくは、「[Power BI Desktop の DirectQuery](desktop-use-directquery.md)」をご覧ください。

![](media/desktop-connect-impala/connect_impala_3a.png)

プロンプトが表示されたら、ユーザー名とパスワードを入力するか、または匿名で接続します (どちらもサポートされています)。

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> 特定の **Impala** サーバーのユーザー名とパスワードを入力した場合、Power BI Desktop は以降もその同じ資格情報を使用して接続を試みます。 これらの資格情報を変更するには、**[ファイル]、[オプションと設定]、[データ ソース設定]** の順に移動します。
> 
> 

接続が正常に行われたら、**[ナビゲーター]** ウィンドウが開き、サーバー上で使用可能なデータが表示されます。その中から 1 つまたは複数の要素を選択し、**Power BI Desktop** にインポートして使用することができます。

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>考慮事項と制限事項
**Impala** コネクタにはいくつかの制限事項と考慮事項があるので注意してください。

* 今後の計画には、**Power BI Gateway** の使用に関するサポートの更新などが予定されています。

## <a name="next-steps"></a>次の手順
Power BI Desktop を使用して接続できるデータの種類は他にもあります。 データ ソースの詳細については、次のリソースを参照してください。

* [Power BI Desktop の概要](desktop-getting-started.md)
* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop で Excel ブックに接続する](desktop-connect-excel.md)   
* [Power BI Desktop にデータを直接入力する](desktop-enter-data-directly-into-desktop.md)   

