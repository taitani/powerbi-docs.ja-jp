---
title: Power BI Desktop で SAP HANA を使用する
description: Power BI Desktop で SAP HANA を使用する
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 6e10c7d7d93fb3c7ec3b27726065a852e4a4a190
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54278241"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Power BI Desktop で SAP HANA を使用する
Power BI Desktop を利用し、 **SAP HANA** データベースにアクセスできるようになりました。 **SAP HANA**を使用するには、Power BI Desktop **SAP HANA** データ接続が機能するように、SAP HANA ODBC ドライバーをローカルのクライアント コンピューターにインストールする必要があります。 SAP HANA ODBC ドライバーは、[SAP Software Download Center](https://support.sap.com/swdc) からダウンロードできます。 SAP Software Download Center で、Windows コンピューター用の SAP HANA CLIENT を検索します。 **SAP Software Download Center** は構成が頻繁に変更されるので、サイトのナビゲーションに関する具体的なガイダンスはありません。

**SAP HANA** データベースに接続するには、次の画像のように、**[データの取得]、[データベース]、[SAP HANA データベース]** の順に選択します。

![](media/desktop-sap-hana/sap-hana-1.png)

SAP HANA データベースに接続するとき、*server:port* の形式でサーバー名とポートを指定します。次の画像の例では、*ServerXYZ* という名前のサーバーと *30015* ポートが使用されています。

![](media/desktop-sap-hana/sap-hana-2.png)

このリリースで、[DirectQuery](desktop-directquery-sap-hana.md) モードの **SAP HANA** が Power BI Desktop と Power BI サービスでサポートされるようになりました。DirectQuery モードの **SAP HANA** を使用するレポートを Power BI サービスに公開したり、アップロードしたりできます。 DirectQuery モードで **SAP HANA** を使用しないときも、Power BI サービスにレポートを公開したり、アップロードしたりできます。

## <a name="supported-features-for-sap-hana"></a>SAP HANA でサポートされる機能
このリリースでは、次の一覧に示すように **SAP HANA**向けに多くの機能が用意されています。

* **SAP HANA** 向け Power BI コネクタでは SAP ODBC ドライバーを使用し、最適なユーザー エクスペリエンスを提供
* **SAP HANA** では DirectQuery およびインポート オプションの両方をサポート
* Power BI では HANA 情報モデル (分析ビューや計算ビューなど) をサポートし、ナビゲーションを最適化
* **SAP HANA** では、ダイレクト SQL 機能を使用して行および列テーブルへの接続も可能
* HANA モデル向けに最適化されたナビゲーションを採用
* Power BI は、 **SAP HANA** の変数および入力パラメーターをサポート

## <a name="limitations-of-sap-hana"></a>SAP HANA の制限
**SAP HANA**を使用する場合、次に示すいくつかの制限があります。

* NVARCHAR 文字列は最大 4,000 文字の Unicode 文字に切り捨てられる
* SMALLDECIMAL はサポートされていない
* VARBINARY はサポートされていない
* 有効な日付は 1899/12/30 から 9999/12/31 まで


## <a name="next-steps"></a>次の手順
DirectQuery の詳細については、次のリソースを参照してください。

* [DirectQuery と SAP HANA](desktop-directquery-sap-hana.md)
* [Power BI の DirectQuery](desktop-directquery-about.md)
* [DirectQuery でサポートされるデータ ソース](desktop-directquery-data-sources.md)

