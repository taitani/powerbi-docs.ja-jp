---
title: Oracle データベースへの接続
description: Oracle を Power BI Desktop に接続するために必要な手順とダウンロード
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6e79de6cb2d6b84d47bc878b8d7acae062e9d8e9
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2018
ms.locfileid: "39326811"
---
# <a name="connect-to-an-oracle-database"></a>Oracle データベースへの接続
**Power BI Desktop** を使用して Oracle データベースに接続するには、Power BI Desktop を実行しているコンピューター上に適切な Oracle クライアント ソフトウェアをインストールする必要があります。 使用する Oracle クライアント ソフトウェアは、インストールした Power BI Desktop のバージョン ( **32 ビット**バージョンか **64 ビット**バージョン) によって異なります。

**サポートされるバージョン**: Oracle 9 以降、Oracle クライアント ソフトウェア 8.1.7 以降。

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>インストールされている Power BI Desktop バージョンの特定
どのバージョンの Power BI Desktop がインストールされているかを特定するには、**[ファイル] > [ヘルプ] > [バージョン情報]** の順に選択し、次に **[バージョン]** 行を確認します。 次の図の場合、Power BI Desktop の 64 ビット バージョンがインストールされています。

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Oracle クライアントのインストール
Power BI Desktop の **32 ビット** バージョンの場合、次のリンクをクリックして **32 ビット** Oracle クライアントをダウンロードし、インストールします。

* [32-bit Oracle Data Access Components (ODAC) with Oracle Developer Tools for Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Power BI Desktop の **64 ビット** バージョンの場合、次のリンクをクリックして **64 ビット** Oracle クライアントをダウンロードし、インストールします。

* [64-bit ODAC 12c Release 4 (12.1.0.2.4) for Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Oracle データベースへの接続
一致する Oracle クライアント ドライバーがインストールされると、Oracle データベースに接続できます。 接続するには、次の手順を実行します。

1. [データの取得] ウィンドウから、**[データベース] > [Oracle データベース]** を選択します。
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. 表示される **[Oracle データベース]** ダイアログでサーバーの名前を指定し、**[接続]** を選択します。 SID が必要な場合、"*サーバー名/SID*" の形式で指定します。SID はデータベースの一意名です。 "*サーバー名/SID*" の形式でうまくいかない場合は、"*サーバー名/サービス名*" を試してください。サービス名は接続時に使用した別名です。
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. ネイティブ データベース クエリを使用してデータをインポートする場合、**[Oracle データベース]** ダイアログで **[詳細オプション]** セクションを展開して **[SQL ステートメント]** ボックスを開き、クエリを入力します。
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. [Oracle データベース] ダイアログに Oracle データベース情報 (SID やネイティブ データベース クエリといったオプションの情報を含む) を入力したら、**[OK]** を選択して接続します。
5. Oracle データベースがデータベース ユーザー資格情報を必要とする場合、ダイアログで指示が表示されたら資格情報を入力します。

