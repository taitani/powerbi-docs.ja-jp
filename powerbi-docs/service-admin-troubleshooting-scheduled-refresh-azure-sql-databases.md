---
title: Azure SQL Database のスケジュール設定された更新に関するトラブルシューティング
description: Power BI における Azure SQL Database のスケジュール設定された更新に関するトラブルシューティング
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: d1cd68fbb995b7fac420a50f97a8930385086a10
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026065"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Power BI における Azure SQL Database のスケジュール設定された更新に関するトラブルシューティング
スケジュール設定された更新を設定するための手順の詳細については、「[Power BI でのデータの更新](refresh-data.md)」をご確認ください。

Azure SQL Database のスケジュール設定された更新を設定していて、資格情報の編集中にエラー (エラー コード 400) が発生した場合は、次の操作を実行して適切なファイアウォール規則を設定します。

1. Azure の管理ポータルにログインします
2. 更新を構成している対象の Azure SQL サーバーに移動します
3. 利用できるサービス セクションで 'Windows Azure サービス' をオンにします

![Azure で使用できるサービス](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

