---
title: オンプレミス データ ゲートウェイに関してよく寄せられる質問 (FAQ)
description: これはオンプレミス データ ゲートウェイに関してよく寄せられる質問 (FAQ) です。 ゲートウェイに関してよく寄せられる質問を 1 か所にまとめています。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: b4ecec3b2e53c2fea0fcbb7d78d1114da1a105ed
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="on-premises-data-gateway-faq"></a>オンプレミス データ ゲートウェイに関してよく寄せられる質問 (FAQ)
<!-- Shared FAQ shared Include -->
[!INCLUDE [gateway-onprem-faq-shared-include](./includes/gateway-onprem-faq-shared-include.md)]

## <a name="analysis-services"></a>Analysis Services
**質問:** Analysis Services では、msdmpump.dll を使用してカスタムの有効なユーザー名マッピングを作成できますか。  
**回答:** いいえ。 現時点ではサポートされていません。

**質問:** ゲートウェイを使用し、多次元 (OLAP) インスタンスに接続できますか。  
**回答:** もちろんです。 オンプレミス データ ゲートウェイでは、Analysis Services の表形式と多次元モデルへのライブ接続をサポートしています。

**質問:** Windows 認証を使用するオンプレミス サーバーとは異なるドメイン内のコンピューターにゲートウェイをインストールした場合、どうなりますか?  
**回答:** 結果は保証されません。 うまく機能するかどうかはすべて、2 つのドメイン間の信頼関係に応じて決まります。 2 つの異なるドメインが信頼されたドメイン モデルに含まれていれば、ゲートウェイは Analysis Services サーバーに接続し、有効なユーザー名を解決できる可能性があります。 含まれていない場合、ログインできないことがあります。

**質問:** オンプレミスの Analysis Services サーバーにどの有効なユーザー名が渡されているかを調べる方法がありますか。  
**回答:** これについては[トラブルシューティング記事](service-gateway-onprem-tshoot.md)で回答します。

**質問:** Analysis Services に 25 台のデータベースがあります。ゲートウェイに対してすべてを一度に有効にする方法はありますか。  
**回答:** いいえ。 これはロードマップにありますが、時間枠は用意していません。

## <a name="administration"></a>管理
**質問:** 1 つのゲートウェイに対して複数の管理者を指定できますか。  
**回答:** もちろんです。 ゲートウェイを管理するとき、管理者のタブに移動し、管理者を追加できます。

**質問:** ゲートウェイの管理者は、ゲートウェイがインストールされているコンピューターの管理者である必要がありますか。  
**回答:** いいえ。 ゲートウェイ管理者は、サービス内からゲートウェイを管理する際に使用されます。

**質問:** 自分の所属組織のユーザーにゲートウェイの構築を禁止できますか。  
**回答:** いいえ。 これはロードマップにありますが、時間枠は用意していません。

**質問:** 自分の所属組織でゲートウェイの使用状況と統計値を入手できますか。  
**回答:** いいえ。 これはロードマップにありますが、時間枠は用意していません。

## <a name="power-bi"></a>Power BI
**質問:** パーソナル ゲートウェイをアップグレードする必要はありますか。
**回答:** いいえ。Power BI のパーソナル ゲートウェイを引き続き使用できます。

**質問:** オンプレミス データ ゲートウェイを介して接続しているとき、Power BI のダッシュボードにタイルはどれくらいの頻度で更新されますか?  
**回答:** 約 10 分です。 DirectQuery ライブ接続はちょうどそのくらいです。 これは、10 分ごとにタイルがオンプレミス サーバーにクエリを発行し、新しいデータを表示するという意味ではありません。

**質問:** オンプレミスのデータ ソースに接続する Power Pivot データ モデルの入った Excel ブックをアップロードできますか。 このシナリオではゲートウェイは必要ですか。  
**回答:** はい、そのようなブックをアップロードできます。 ゲートウェイは必要ありません。 データが Excel データ モデルに存在するため、Excel ブックに基づく Power BI でのレポートはライブではなくなります。 Power BI のレポートを更新するには、更新されたブックを毎回、再アップロードする必要があります。 あるいは、更新をスケジュールし、ゲートウェイを使用します。

**質問:** ユーザーが DirectQuery 接続のあるダッシュボードを共有する場合、同じアクセス許可を持たない他のユーザーでもデータを表示できますか。  
**回答:** Analysis Services に接続されたダッシュボードの場合、ユーザーはアクセス権限を持つデータのみを表示できます。 ユーザーが同じアクセス許可を持たない場合、データを表示できません。 その他のデータ ソースの場合、すべてのユーザーはそのデータ ソースの管理者によって入力された資格情報を共有します。

**質問:** Oracle サーバーに接続できないのはなぜですか。  
**回答:** Oracle サーバーに接続するには、Oracle クライアントをインストールし、tnsnames.ora ファイルに適切なサーバー情報を構成することが必要な場合があります。 このインストールは、ゲートウェイとは別に行います。 詳細については、「[Oracle クライアントのインストール](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client)」をご覧ください。

**質問:** ゲートウェイは ExpressRoute と連携して動作しますか?  
**回答:** はい。 ExpressRoute と Power BI の詳細については、「[Power BI と ExpressRoute](service-admin-power-bi-expressroute.md)」を参照してください。

## <a name="next-steps"></a>次の手順
[オンプレミス データ ゲートウェイ](service-gateway-onprem.md)  
[オンプレミス データ ゲートウェイの詳細](service-gateway-onprem-indepth.md)  
[オンプレミス データ ゲートウェイのトラブルシューティング](service-gateway-onprem-tshoot.md)  
他にわからないことがある場合は、 [Power BI コミュニティを利用してください](http://community.powerbi.com/)。

