---
title: "Power BI で IntelliBoard に接続する"
description: "Power BI 用 IntelliBoard"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: e74b26c9d34b19607a0b38197c466f4eb3a06e2a
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Power BI で IntelliBoard に接続する
IntelliBoard を使用すると、レポート サービスを介して Moodle 学習管理システムのデータに簡単にアクセスできます。 Power BI 用 IntelliBoard コンテンツ パックは、コース、登録ユーザー、全体的な成績、および LMS アクティビティに関するメトリックを含む、追加の分析を提供します。

Power BI 用 [IntelliBoard コンテンツ パック](https://app.powerbi.com/getdata/services/intelliboard)に接続します。

## <a name="how-to-connect"></a>接続する方法
1. 左側のナビゲーション ウィンドウの下部にある **[データの取得]** を選択します。  
   
    ![](media/service-connect-to-intelliboard/getdata.png)
2. **[サービス]** ボックスで、 **[取得]**を選択します。  
   
    ![](media/service-connect-to-intelliboard/services.png)
3. **[IntelliBoard]**、**[取得]** の順に選択します。  
   
    ![](media/service-connect-to-intelliboard/intelliboard.png)
4. **[OAuth 2]** を選択し、**[サインイン]** をクリックします。 要求されたら、IntelliBoard 資格情報を入力します。
   
    ![](media/service-connect-to-intelliboard/creds.png)
   
    ![](media/service-connect-to-intelliboard/creds2.png)
5. 接続されると、ダッシュボード、レポート、およびデータセットが自動的に読み込まれます。 完了すると、タイルが IntelliBoard アカウントからのデータで更新されます。
   
    ![](media/service-connect-to-intelliboard/dashboard.png)

**実行できる操作**

* ダッシュボード上部にある [Q&A ボックスで質問](power-bi-q-and-a.md)してみてください。
* ダッシュボードで[タイルを変更](service-dashboard-edit-tile.md)できます。
* [タイルを選択](service-dashboard-tiles.md)して基になるレポートを開くことができます。
* データセットは毎日更新されるようにスケジュール設定されますが、更新のスケジュールは変更でき、また **[今すぐ更新]** を使えばいつでも必要なときに更新できます。

## <a name="whats-included"></a>含まれるもの
コンテンツ パックには、次のテーブルのデータが含まれています。  

    - アクティビティ  
    - Agents  
    - Auth  
    - Countries  
    - CoursesProgress  
    - Enrollments
    - Lang  
    - Platform  
    - Totals  
    - UsersProgress    

## <a name="system-requirements"></a>システム要件
このコンテンツ パックをインスタンス化するには、上記のテーブルへのアクセス許可を持つ IntelliBoard アカウントが必要です。

## <a name="next-steps"></a>次の手順
[Power BI の概要](service-get-started.md)

[Power BI - 基本的な概念](service-basic-concepts.md)

