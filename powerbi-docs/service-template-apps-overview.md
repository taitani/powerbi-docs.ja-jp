---
title: Power BI テンプレート アプリとは (プレビュー)
description: この記事では、Power BI テンプレート アプリ プログラムの概要を説明します。 ほとんどまたはまったくコーディングしないで Power BI アプリを作成し、Power BI ユーザーに展開する方法を説明します。
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: maggies
ms.openlocfilehash: 445f5f087bd9589b18f798e8db40a63b0ddceafe
ms.sourcegitcommit: 8207c9269363f0945d8d0332b81f1e78dc2414b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56249992"
---
# <a name="what-are-power-bi-template-apps-preview"></a>Power BI テンプレート アプリとは (プレビュー)

新しい Power BI *テンプレート アプリ*を利用すれば、Power BI パートナーはコードをほとんど、あるいはまったく記述せずに Power BI アプリを作成し、Power BI の顧客に配布できます。  この記事では、Power BI テンプレート アプリ プログラムの概要を説明します。

テンプレート アプリは、現在のサービス コンテンツ パックに代わるものです。 Power BI パートナーは、既製のコンテンツのセットを作成して自分で公開します。  

作成したテンプレート アプリに、顧客は自分のアカウントで接続してインスタンス化できます。 ドメインの専門家として、ビジネス ユーザーが簡単に利用できる方法でデータのロックを解除できます。  

パートナー構築テンプレート アプリを Cloud パートナー ポータルに送信します。 アプリは、Power BI App ギャラリー (app.powerbi.com/getdata/services) および Microsoft AppSource (appsource.microsoft.com) でパブリックに利用可能になります。 ここではパブリック テンプレート アプリのエクスペリエンスの例を示します。  

## <a name="overview"></a>概要
テンプレート アプリを開発して送信する一般的なプロセスには複数のステージが含まれ、その一部には同時に複数のアクティビティが含まれることがあります。


| ステージ | Power BI Desktop |  |Power BI サービス  |  |Cloud パートナー ポータル  |
|---|--------|--|---------|---------|---------|
| **1** | データ モデルとレポートを .pbix ファイルで作成します |  | ワークスペースを作成します。 .pbix ファイルをインポートします。 補完的なダッシュ ボードを作成します  |  | パートナーとして登録します |
| **2** |  |  | テスト パッケージを作成し、内部的な検証を実行します        |  | |
| **3** | |  | Power BI テナント外での検証のために運用前テスト パッケージをプロモートし、AppSource に送信します  |  | 運用前パッケージで、Power BI テンプレート アプリ オファーを作成し、検証プロセスを開始します |
| **4** | |  | 運用前パッケージを運用環境にプロモートします |  | ライブに移行します |

## <a name="requirements"></a>要件

テンプレート アプリを作成するには、作成するためのアクセス許可が必要です。 詳細については、Power BI 管理ポータルのテンプレート アプリの設定に関するセクションを参照してください。 

テンプレート アプリを Power BI サービスと AppSource に公開するには、「[クラウド マーケットプレース パブリッシャーになる](https://docs.microsoft.com/azure/marketplace/become-publisher)」の要件を満たす必要があります。
 
## <a name="high-level-steps"></a>概要手順

手順の概要を次に示します。 

1. [要件を見直し](#requirements)、満たしていることを確認します。 

1. Power BI Desktop でレポートを作成します。 他のユーザーが使用できるファイルとして保存できるようにパラメーターを使用します。 

1. Power BI サービス (app.powerbi.com) で、テナントにテンプレート アプリ用のワークスペースを作成します。 

1. .pbix ファイルをインポートし、ダッシュボードなどのコンテンツをアプリに追加します。 

1. テスト パッケージを作成し、組織内でテンプレート アプリをテストします。 

1. AppSource での検証と、テナント外でのテストのために、テスト アプリを運用前環境にプロモートしてアプリを送信します。 

1. 公開用に Cloud パートナー プラットフォームにコンテンツを送信します。 

1. AppSource でオファーを "ライブ" にし、アプリを Power BI の運用環境に移動します。
2. 運用前環境の同じワークスペースで次のバージョンの開発を開始できます。 

## <a name="requirements"></a>要件

テンプレート アプリを作成するには、作成するためのアクセス許可が必要です。 詳細については、Power BI [管理ポータルのテンプレート アプリの設定](service-admin-portal.md#template-apps-settings-preview)に関するセクションを参照してください。 

テンプレート アプリを Power BI サービスと AppSource に公開するには、「[クラウド マーケットプレース パブリッシャーになる](https://docs.microsoft.com/azure/marketplace/become-publisher)」の要件を満たす必要があります。

## <a name="tips"></a>ヒント 

- 誰でもクリックして開始できるようにアプリにサンプル データが含まれることを確認します。 
- 自分のテナントとセカンダリ テナントにインストールして、アプリケーションを慎重に調べます。 必要なものだけが顧客に表示されることを確認します。 
- オンライン ストアとして AppSource を使用して、アプリケーションをホストします。 これにより、Power BI を使用するすべてのユーザーがアプリを検索できます。 
- 独立した固有のシナリオのために複数のテンプレート アプリの提供を検討します。 
- カスタム接続や、インストーラーによるパラメーター構成のサポートなど、データをカスタマイズできるようにします。

他の推奨事項については、「[Power BI でのテンプレート アプリの作成に関するヒント (プレビュー)](service-template-apps-tips.md)」をご覧ください。

## <a name="support"></a>サポート
開発中のサポートのために、[https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support) を使用してください。 私たちは、このサイトを常に見守り、管理しています。 顧客のインシデントは、すみやかに該当するチームに伝わります。

## <a name="next-steps"></a>次の手順

[テンプレート アプリを作成する](service-template-apps-create.md)