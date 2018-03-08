---
title: "モバイル アプリ向けの Power BI Desktop でバーコード フィールドにタグ付けする"
description: "Power BI Desktop でモデルのバーコード フィールドにタグ付けすると、iPhone の Power BI アプリでバーコードのデータを自動的にフィルター処理できます。"
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: acac005938eb5f97a4a745dd9be72540438ed6ed
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2018
---
# <a name="tag-barcodes-in-power-bi-desktop-for-the-mobile-apps"></a>モバイル アプリ向けの Power BI Desktop でバーコードにタグ付けする
Power BI Desktop で列の[データを分類](desktop-data-categorization.md)し、Power BI Desktop がレポートの表示での値の処理方法を認識できるようにすることができます。 列を**バーコード**として分類することもできます。 iPhone の [Power BI アプリで製品のバーコードをスキャン](mobile-apps-scan-barcode-iphone.md)すると、そのバーコードに含まれるレポートが表示されます。 モバイル アプリでレポートを開くと、Power BI によってレポートが自動的にフィルター処理されて、そのバーコードに関連するデータだけが表示されます。

1. Power BI Desktop でデータ ビューに切り替えます。
2. バーコード データがある列を選択します。 後の「[サポートされるバーコード形式](#supported-barcode-formats)」の一覧を参照してください。
3. **[モデリング]** タブで、**[データ カテゴリ]** の **[バーコード]** を選択します。
   
    ![データ カテゴリの一覧](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)
4. レポート ビューで、バーコードによってフィルター処理する表示にこのフィールドを追加します。
5. レポートを保存して、Power BI サービスに発行します。

[iPhone 用 Power BI アプリ](mobile-ios-ipad-iphone-apps.md)でスキャナーを開き、バーコードをスキャンすると、レポートの一覧にこのレポートが表示されます。 レポートを開くと、スキャンした製品のバーコードによって表示がフィルター処理されます。

## <a name="supported-barcode-formats"></a>サポートされるバーコード形式
Power BI レポートでタグを付けることができる場合、Power BI は次のバーコードを認識します。 

* UPCECode 
* Code39Code  
* A39Mod43Code 
* EAN13Code 
* EAN8Code  
* 93Code  
* 128Code 
* PDF417Code 
* Interleaved2of5Code 
* ITF14Code 

## <a name="next-steps"></a>次の手順
* [iPhone の Power BI アプリからバーコードをスキャンする](mobile-apps-scan-barcode-iphone.md)
* [iPhone でのバーコードのスキャンに関する問題](mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Power BI Desktop でのデータ分類](desktop-data-categorization.md)  
* わからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。

