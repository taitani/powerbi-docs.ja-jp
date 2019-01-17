---
title: Power BI でのテンプレート コンテンツ パックのエクスペリエンス
description: テンプレート コンテンツ パックのエクスペリエンス
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: f1010557bdd781fac9542c2636424e7e2bef2c26
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "54288269"
---
# <a name="template-content-pack-experiences-in-power-bi"></a>Power BI でのテンプレート コンテンツ パックのエクスペリエンス
このセクションでは、ISV [コンテンツ パック](service-connect-to-services.md)に接続するユーザーの標準的なエクスペリエンスに注目します。

https://app.powerbi.com/getdata/servicesでリリースされたコンテンツ パック (以下に説明されている [GitHub コンテンツ パック](https://app.powerbi.com/getdata/services/github)など) に接続して、自分で接続エクスペリエンスを試してみることができます。

## <a name="connect"></a>接続
使い始めるには、ユーザーはコンテンツ パック ギャラリーを参照し、接続するコンテンツ パックを選択します。 コンテンツ パック エントリは、名前、アイコン、およびユーザーに詳細を提供する説明テキストを提供します。

![接続](media/template-content-pack-experience/github_data.png)

![接続](media/template-content-pack-experience/github_connect.png)

## <a name="parameters"></a>パラメーター
選択した後、ユーザーはパラメーターを提供するように求められます (必要な場合)。 パラメーター ダイアログは、コンテンツ パックの作成中、作成者によって宣言を使用して提供されます。

現在パラメーターの UI は非常に基本的なものです。ドロップダウン リストを列挙する方法はありません。データ入力の検証は regex に制限されます。

![パラメーター](media/template-content-pack-experience/github_params.png)

## <a name="credentials"></a>資格情報
パラメーターの後、ユーザーはログインするよう求められます。  ソースが複数の種類の認証をサポートしている場合、ユーザーは適切なオプションを選択します。 ソースが OAuth を要求する場合、ユーザーが [サインイン] をクリックするときに、サービスのログイン UI がポップアップで表示されます。  それ以外の場合、ユーザーは、表示されたダイアログで資格情報を入力することができます。

![資格情報](media/template-content-pack-experience/github_login.png)

![接続](media/template-content-pack-experience/github_creds2.png)

## <a name="instantiation"></a>インスタンス化
ログインに成功した場合、モデル、レポート、およびダッシュボードといった、コンテンツ パックに含まれる成果物はナビゲーション バーで表示されます。  これらの成果物は、各ユーザーのアカウントに追加されます。  データは非同期的に読み込まれ、データセット (モデル) が作成されます。  この後、ユーザーは、ダッシュボード、レポート、およびモデルを使用することができます。

既定では、日ごとの更新スケジュールはユーザー用に構成され、モデルのクエリを再評価します。  ユーザーに提供された資格情報は、ユーザーがその場にいなくてもデータを更新することを許可する必要があります。

![インスタンス化](media/template-content-pack-experience/github_dashboard.png)

## <a name="exploration-and-monitoring"></a>探索と監視
コンテンツ パックがユーザーのアカウントにハイドレートされた後、データや情報を探索したり監視することができます。

通常、以下が含まれます。

* ダッシュボードの表示とカスタマイズ。
* レポートの表示とカスタマイズ。
* 自然言語を使用してデータに関する質問をする
* 探索キャンバスを使用してデータ モデル内のデータを探索する

探索エクスペリエンスを改善できるようにするため、自然言語モデリング (シノニム) と理解しやすいモデル スキーマの提供を考慮する必要があります。

