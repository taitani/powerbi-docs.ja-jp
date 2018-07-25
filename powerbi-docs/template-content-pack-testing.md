---
title: Power BI 用のテンプレート コンテンツ パックをテストする
description: テンプレート コンテンツ パックのテスト
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: 4f461029ab3f698992128fa4f3f53714ee962b1e
ms.sourcegitcommit: 3a287ae4ab16d1e76caed651bd8ae1a1738831cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2018
ms.locfileid: "39157550"
---
# <a name="testing-template-content-packs-for-power-bi"></a>Power BI 用のテンプレート コンテンツ パックをテストする
送信して発行する前に、コンテンツ パックをテストするための複数の方法があります。  

> [!NOTE]
> コンテンツ パックで、自分で作成した独自の[データ コネクタ](https://aka.ms/DataConnectors)を使用する場合、以下のように、データ更新やテンプレート コンテンツ パックをテストできません。 その場合、コンテンツ パックの[送信](#submission)にお進みください。Power BI チームがコンテンツ パックのテストをお手伝いします。
> 
> 

## <a name="testing-scheduled-data-refresh"></a>スケジュールされたデータ更新をテストする
テンプレートのコンテンツ パックは PowerBI.com の更新を活用し、接続するときに顧客のデータを含めたコンテンツ パックをインスタンス化します。 コンテンツ パックが一般公開される前に、作成したデスクトップ ファイルを使用してこのフローをテストできます。

ファイルをアップロードした後、データセットの横にある [...] を選択し、[更新のスケジュール設定] を選択します。 ソースの資格情報を構成します。 データセットが正常に更新されていることを確認するために、[今すぐ更新] と [スケジュールされた更新] を試します。 更新時に失敗が検出された場合、エラー メッセージを確認し、クエリおよびエンド システムを検証します。

### <a name="additional-refresh-tips"></a>その他の更新のヒント
* 更新をスケジュールしようとする場合、検出されるデータ ソースは 1 つだけである必要があります。  
* テスト接続では、ユーザーがコンテンツ パックの読み込みができることを示す必要があります。 そうではない場合は、クエリが追加のエラー ケースを処理していることを確認します。  
* 通常、更新は 5 分程度で完了します。  

![設定](media/template-content-pack-testing/scheduledrefresh.png)

<a name="templates"></a>

## <a name="testing-templates"></a>テンプレートをテストする
テンプレート コンテンツ パックは既存のソリューションに似ていますが、データセット内の実際のデータは含まれていません。 代わりに、ユーザーがテンプレートを使用したりインスタンス化する場合、接続のためにパラメーターと資格情報を求められます。 接続されると、ダッシュボード、レポートおよびデータセットに自分のデータが表示されます。 

スケジュールされた更新を含むデータセット設定へのアクセスが与えられたコンテンツ パックをインスタンス化した後、データセットの RLS 設定はそのコンテンツ パックで**公開されません**。  

> [!NOTE]
> テンプレート コンテンツ パックに含めることができるのは 1 つのダッシュボード、1 つのレポートおよび 1 つのデータセットのみです。 [作成](template-content-pack-authoring.md#restrictions)ページから制限の一覧を参照してください。 
> 
> 

テナントのテンプレート作成を有効にするには、Power BI 管理者と協力し、下の機能の切り替えを有効にしてください。 

![機能の切り替え](media/template-content-pack-testing/featureswitch.png)

有効にすると、["コンテンツ パックの作成"](https://app.powerbi.com/groups/me/publish-content/) の下部にチェックボックスが表示されます。このチェックボックスで、テンプレート コンテンツ パックを組織に公開できます。 

![チェックボックス](media/template-content-pack-testing/checkbox.png)

### <a name="naming"></a>名前付け
ダッシュボード、レポートおよびデータセットを、コンテンツ パック全体で一貫して名前付けすることをお勧めします。 これらの名前はハードコードされ、すべてのユーザーについて同じになります。これにより、製品名およびシナリオ名を使用することで、顧客にとって検索しやすくなります。

### <a name="additional-template-tips"></a>その他のテンプレートのヒント
* クエリで指定したパラメーターがエンド ユーザーにとって意味のあるものであることを確認します
* スケジュールされた更新を完了するために、エンド ユーザーが待つ時間を考慮します

![作成](media/template-content-pack-testing/createtemplate.png)

<a name="submission"></a>

## <a name="submission"></a>送信
[Microsoft AppSource](https://appsource.microsoft.com/en-us/partners/list-an-app) 経由の送信プロセスでは、PowerBI.com のサービス コンテンツ パック ギャラリーにテンプレート コンテンツ パックを公開できます。また、[Microsoft AppSource](http://appsource.microsoft.com) にコンテンツ パックを一覧表示できます。

### <a name="before-submission"></a>送信の前に
* コンテンツ パック内の各成果物の作成ヒントを確認します
* さまざまなアカウントとデータ条件でテストし、接続します。 (独自の[データ コネクタ](https://aka.ms/DataConnectors)を開発した場合、この手順を省略してください)
* すべてのビジュアルを確認し、スペルが間違っている項目がないかどうか注意深く探します
* コンテンツ パックが Q&A に正しく応答していることを確認するため、データ モデルから少なくとも 30 の各種質問をテストすることをお勧めします。 (独自の[データ コネクタ](https://aka.ms/DataConnectors)を開発した場合、この手順を省略してください)

### <a name="submission"></a>送信
送信する準備ができたら、[AppSource でアプリ送信ページ](https://appsource.microsoft.com/en-us/partners/list-an-app)にアクセスし、情報を送信します。 必ず製品の一覧から Power BI を選択してください

Power BI チームは送信内容を確認し、すべての成果物が提出要件を満たしていることを確認するために連絡します。 完全である以外に、ダッシュボードおよび提供されているレポートの品質を検証し、アプリケーションで説明されているビジネス シナリオを満たしていることを確認します。

### <a name="updates"></a>更新プログラム
コンテンツ パックの更新は、元の送信と似たフローに従います。 

