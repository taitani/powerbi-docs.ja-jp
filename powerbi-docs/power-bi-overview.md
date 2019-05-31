---
title: Power BI とは?
description: Power BI とさまざまな部分が一緒に適合させる方法の概要については Power BI Desktop、Power BI サービス、Power BI モバイルでレポート サーバー、および Power BI が埋め込まれます。
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: overview
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 7236caba1c7a8eb07e93c6f2af7068141b8ac3a7
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413039"
---
# <a name="what-is-power-bi"></a>Power BI とは?
**Power BI** はソフトウェア サービス、アプリ、コネクタのコレクションで、これらを組み合わせることで、関連性のないデータ ソースから、まとまりがあり、実体験的な対話型洞察を得ることができます。 Excel スプレッドシートや、クラウド ベースとオンプレミスのハイブリッド データ ウェアハウスのコレクションなど、さまざまなデータを使えます。 Power BI では、簡単に、データ ソースに接続、視覚化し、重要なことを確認し、なるすべてのユーザーまたはすべてのユーザーと共有できます。

![Power BI 用の入力ソースを示す図](media/power-bi-overview/power-bi-input-new.png)

Power BI は、Excel のスプレッドシートやローカル データベースからクイック分析情報を作成できる単純な高速にできます。 Power BI は堅牢なもとエンタープライズ グレードの広範なモデリング、リアルタイム分析とカスタム開発の準備ができています。 ある個人用レポートと視覚化ツール、およびグループ プロジェクト、部門、または会社全体の分析および意思決定エンジンとしても使用できます。

## <a name="the-parts-of-power-bi"></a>Power BI の構成要素
Power BI から成ります。 
- Windows デスクトップ アプリケーションと呼ばれる**Power BI Desktop**
- オンライン SaaS (*サービスとしてのソフトウェア*) と呼ばれるサービス、 **Power BI サービス** 
- Power BI**モバイルアプリ**Windows、iOS、および Android デバイス

![Power BI Desktop、サービス、モバイル](media/power-bi-overview/power-bi-blocks.png)

これら 3 つの要素&mdash;Power BI Desktop、サービス、およびモバイル アプリ&mdash;をユーザーの作成、共有、および、または各自のロールを最も効果的に機能するようにビジネスの洞察を利用できるように設計されています。

4 番目の要素である **Power BI Report Server** を使うと、Power BI Desktop で Power BI レポートを作成した後、それをオンプレミスのレポート サーバーに発行できます。 [Power BI レポート サーバー](#on-premises-reporting-with-power-bi-report-server)の詳細をお読みください。

## <a name="how-power-bi-matches-your-role"></a>Power BI とロールの対応
Power BI の使用方法は、プロジェクトまたはチームにおけるユーザーのロールによって異なる場合があります。 他のユーザー、他のロールで可能性がありますを使用して、Power BI が異なる。

たとえば、ご自分では **Power BI サービス**を主に使うかもしれません。 しかし、大量の計算を行ってビジネス レポートを作成する同僚は、レポートを作成し、そのレポートをあなたが確認できる Power BI サービスに発行するために、**Power BI Desktop** を重点的に使うかもしれません。 別の同僚で sales、主に使用して、その**Power BI 電話アプリ**その販売のクォータの進行状況を監視し、新しいセールス リード詳細にドリルダウンします。

開発者であれば、Power BI API を使用してデータをデータセットにプッシュしたり、ダッシュボードとレポートをカスタム アプリケーションに埋め込んだりする可能性があります。 新しいビジュアルのアイデアがあれば、 それを自分で作成して、他のユーザーと共有できます。  

Power BI の各要素を使用して、達成するためにしているか、指定されたプロジェクトに対して、ロールに応じて、異なるタイミングに可能性がありますも。

Power BI の使用方法は、Power BI のどの機能またはサービスがご自分の状況に対して最適なツールとなるかに基づいています。 たとえば、顧客契約統計に関するチームのレポートを作成する Power BI Desktop を使用することができ、在庫と製造 Power BI サービスでダッシュ ボードがリアルタイムで進行状況を表示することができます。 Power BI の各部分を利用できることが、その柔軟性と魅力の理由です。

ご自身のロールに関連するドキュメントについては、次をご覧ください。
- [***デザイナー***](desktop-what-is-desktop.md)向け Power BI
- [***利用者***](consumer/end-user-consumer.md)向け Power BI
- [***開発者***](developer/what-can-you-do.md)向け Power BI
- [***管理者***](service-admin-administering-power-bi-in-your-organization.md)向け Power BI

## <a name="the-flow-of-work-in-power-bi"></a>Power BI のワークフロー
Power BI での一般的なワークフローは、データ ソースに接続して、Power BI Desktop でレポートを作成して開始します。 Power BI Desktop から Power BI サービスに発行し、Power BI サービスとモバイル デバイスのエンドユーザーを表示およびレポートと対話できるようにそれを共有します。
このワークフローは一般的で、Power BI の 3 つの主な要素がお互いを補完するしくみを示しています。

こちらに詳細な [Power BI Desktop と Power BI サービスの比較](service-service-vs-desktop.md)があります。

でも、クラウドに移行する準備が整っていないため、企業のファイアウォールの背後にレポートを保持する場合はどうすればよいでしょうか。  読み続けてください。

## <a name="on-premises-reporting-with-power-bi-report-server"></a>オンプレミスで Power BI レポート サーバーでレポートの作成
作成、デプロイ、および Power BI モバイルやページ分割されたレポートをすぐに使用できるツールやサービスで Power BI Report Server のさまざまなオンプレミスの管理します。

![オンプレミス用の図](media/power-bi-overview/power-bi-report-server2.png)

Power BI Report Server は、ファイアウォールの背後に展開するソリューションであり、適切なユーザーにさまざまな方法でレポートを配信します。レポートは、Web ブラウザーでもモバイル デバイスでも表示でき、電子メールとして送信することもできます。 Power BI Report Server は、クラウドの Power BI に対応するため、準備ができたらクラウドに移行することができます。 

[Power BI レポート サーバー](report-server/get-started.md)の詳細をお読みください。

## <a name="next-steps"></a>次の手順
- [クイック スタート:Power BI サービスを使いこなす方法を説明します。](service-the-new-power-bi-experience.md)   
- [チュートリアル:Power BI サービスを概要します。](service-get-started.md)
- [クイック スタート:Power BI Desktop でデータに接続する](desktop-quickstart-connect-to-data.md)
