---
title: Power BI REST API の制限事項
description: Power BI REST API には、次のような制限があります
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: df17563d384359fe33123ed87743754bb33bf04d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277976"
---
# <a name="power-bi-rest-api-limitations"></a>Power BI REST API の制限事項  
  
**行を POST するには**  
  
* 列数の上限は 75
* テーブル数の上限は 75
* 1 つの「行の POST」要求の最大行数は 10,000 行  
* 1 つのデータセットの 1 時間あたりの追加行数は 1,000,000 行  
* 1 つのデータセットの保留の「行の POST」要求の数は 5 つまで  
* 1 つのデータセットの「行の POST」要求数は 1 分間あたり 120 個
* テーブルの行数が 250,000 以上の場合は、1 つのデータセットの「行の POST」要求数は 1 時間あたり 120 個    
* FIFO データセット内の 1 テーブルごとに保存される最大行数は 200,000 行  
* 「保持ポリシーなし」のデータセット内の 1 テーブルごとに保存される最大行数は 5,000,000 行  
* 行の POST 操作における文字列型の列の値 1 つあたりの最大文字数は 4,000 文字
  
## <a name="see-also"></a>参照

[Azure AD サービスの制限と制約](https://docs.microsoft.com/azure/active-directory/active-directory-service-limits-restrictions)   
[Power BI REST API の概要](https://docs.microsoft.com/rest/api/power-bi/)