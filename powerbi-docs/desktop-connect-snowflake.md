---
title: Power BI Desktop で Snowflake Computing ウェアハウスに接続する
description: Power BI Desktop で Snowflake Computing ウェアハウスに簡単に接続して使用する
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: bd49252101df0009b2a25b5cdf3b77f79d86510e
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="connect-to-snowflake-in-power-bi-desktop"></a>Power BI Desktop で Snowflake に接続する
Power BI Desktop では、**Snowflake** Computing ウェアハウスに接続し、Power BI Desktop の他のデータ ソースの場合と同様に基になっているデータを使用できます。 

> [!NOTE]
> 32 ビットまたは 64 ビットのいずれかの **Power BI Desktop** のインストールに合致するアーキテクチャを使用して、**Snowflake** コネクタを使用するコンピューターに **Snowflake ODBC ドライバー**をインストールする*必要があります*。 次のリンクに従って、[適切な Snowflake ODBC ドライバーをダウンロード](http://go.microsoft.com/fwlink/?LinkID=823762)します。
> 
> 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Snowflake Computing ウェアハウスに接続する
**Snowflake** Computing ウェアハウスに接続するには、Power BI Desktop の **[ホーム]** リボンで **[データの取得]** を選択します。 左側のカテゴリから **[データベース]** を選ぶと、**[Snowflake]** が表示されます。

![](media/desktop-connect-snowflake/connect_snowflake_2b.png)

表示された **[Snowflake]** ウィンドウ内のボックスに Snowflake Computing ウェアハウスの名前を入力するか、貼り付け、**[OK]** をクリックします。 Power BI にデータを直接**インポート**したり、**DirectQuery** を使用したりできます。 詳しくは、「[Power BI Desktop の DirectQuery](desktop-use-directquery.md)」をご覧ください。

![](media/desktop-connect-snowflake/connect_snowflake_3.png)

プロンプトが表示されたら、ユーザー名とパスワードを入力します。

![](media/desktop-connect-snowflake/connect_snowflake_4.png)

> [!NOTE]
> 特定の **Snowflake** サーバーのユーザー名とパスワードを入力した場合、Power BI Desktop は以降もその資格情報を使用して接続を試みます。 これらの資格情報を変更するには、**[ファイル]、[オプションと設定]、[データ ソース設定]** の順に移動します。
> 
> 

接続が正常に行われたら、**[ナビゲーター]** ウィンドウが開き、サーバー上で使用可能なデータが表示されます。その中から 1 つまたは複数の要素を選択し、**Power BI Desktop** にインポートして使用することができます。

![](media/desktop-connect-snowflake/connect_snowflake_5.png)

選択したテーブルを**読み込んで**、テーブル全体を **Power BI Desktop** に取り込むことができます。またはクエリを**編集**して**クエリ エディター**を開き、使用するデータのセットをフィルターし、絞り込んでから、その絞り込んだデータのセットを **Power BI Desktop** に取り込むこともできます。

## <a name="next-steps"></a>次の手順
Power BI Desktop を使用して接続できるデータの種類は他にもあります。 データ ソースの詳細については、次のリソースを参照してください。

* [Power BI Desktop の概要](desktop-getting-started.md)
* [Power BI Desktop のデータ ソース](desktop-data-sources.md)
* [Power BI Desktop でのデータの整形と結合](desktop-shape-and-combine-data.md)
* [Power BI Desktop で Excel ブックに接続する](desktop-connect-excel.md)   
* [Power BI Desktop にデータを直接入力する](desktop-enter-data-directly-into-desktop.md)   

