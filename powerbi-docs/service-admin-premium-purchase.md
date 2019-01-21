---
title: Power BI Pro の購入方法
description: Power BI Premium を購入し、組織全体にコンテンツへのアクセスを可能する方法について説明します。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/14/2019
ms.author: mblythe
LocalizationGroup: Premium
ms.openlocfilehash: ebcf4a6467991bfc0d434302cd2c846ca4af1a5c
ms.sourcegitcommit: a20825ebd0ef4c2cb77232e3dd0e9f8260cacf71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "54323999"
---
# <a name="how-to-purchase-power-bi-premium"></a>Power BI Pro の購入方法

この記事では、組織に Power BI Premium の容量を購入する方法について説明します。 Power BI Premium 容量は Office 365 管理センターで購入でき、Power BI 管理ポータルで[容量を管理](service-admin-premium-manage.md)できます。

<iframe width="640" height="360" src="https://www.youtube.com/embed/NkvYs5Qp4iA?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

Power BI Premium の詳細については、「[Microsoft Power BI Premium とは何ですか?](service-premium.md)」を参照してください。 現在の価格と計画については、[Power BI の料金ページ](https://powerbi.microsoft.com/pricing/)および「[Power BI Premium 計算ツール](https://powerbi.microsoft.com/calculator/)」を参照してください。

> [!IMPORTANT]
> 組織が Power BI Premium を使用する場合でも、コンテンツの作成者には Power BI Pro のライセンスが引き続き必要です。 組織で Power BI Pro ライセンスを少なくとも 1 つ購入してください。
>
>Premium サブスクリプションの有効期限が切れてから 30 日間は、容量への完全なアクセス権があります。 その後、コンテンツは共有された容量に戻ります。 1 GB を超えるモデルは、共有された容量ではサポートされません。

## <a name="create-a-new-tenant-with-power-bi-premium-p1"></a>Power BI Premium P1 で新しいテナントを作成する

既存のテナントをお持ちでない場合は、テナントの作成と同時に Power BI Premium も購入することができます。 次のリンクをクリックすると、新しいテナントを作成するプロセスが案内され、Power BI Premium を購入することができます:[Power BI Premium P1 オファー](https://signup.microsoft.com/Signup?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1)。

![Power BI Premium P1](media/service-admin-premium-purchase/premium-purchase-with-tenant.png)

テナントを作成すると、そのテナントの Office 365 の全体管理者ロールに自動的に割り当てられます。

## <a name="purchase-a-power-bi-premium-capacity-for-an-existing-organization"></a>既存の組織用の Power BI Premium 容量を購入する

既存の組織をお持ちの場合、サブスクリプションとライセンスを購入するには、Office 365 の全体管理者ロールまたは課金管理者ロールである必要があります。 詳細については、「[Office 365 の管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)」を参照してください。

Premium 容量を購入するには、以下の手順に従います。

1. Power BI サービス内で、[Office 365 アプリ ピッカー]、**[管理者]** の順に選択します。

    ![Office 365 アプリ ピッカー](media/service-admin-premium-purchase/o365-app-picker.png)

    または、Office 365 管理センターを参照することができます。 管理センターにアクセスするには、 https://portal.office.com に移動して **[管理者]** を選択します。

1. **[請求]** > **[サービスを購入する]** を選択します。

1. **[その他のプラン]** で、Power BI Premium のオファーを探します。 これは P1 ～ P3、EM3、および P1 (月極め) として一覧表示されます。

1. 省略記号 (**. . .**) にポインターを合わせ、**[今すぐ購入する]** を選択します。

    ![今すぐ購入する](media/service-admin-premium-purchase/premium-purchase.png)

1. 以下の手順に従って、購入を完了します。

次のいずれかのリンクを選択して、その SKU の購入ページに直接移動することもできます。 これらの SKU の詳細については、「[Microsoft Power BI Premium とは何ですか?](service-premium.md#premium-capacity-nodes)」を参照してください。

> [!IMPORTANT]
> Office 365 の全体管理者ロールまたは課金管理者ロールでない場合、次のいずれかのリンクを選択すると、エラーが発生します。

| 直接発注リンク |
| --- |
| [EM3 (月極め) SKU](https://portal.office.com/commerce/completeorder.aspx?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |
| [P1 SKU](https://portal.office.com/commerce/completeorder.aspx?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |
| [P1 (月極め) SKU](https://portal.office.com/commerce/completeorder.aspx?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1) |
| [P2 SKU](https://portal.office.com/commerce/completeorder.aspx?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |
| [P3 SKU](https://portal.office.com/commerce/completeorder.aspx?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |

購入を完了すると、**[サービスを購入する]** ページに購入したアクティブな項目が表示されます。

![Power BI Premium を購入した場合](media/service-admin-premium-purchase/premium-purchased.png)

## <a name="purchase-additional-capacities"></a>追加の容量を購入する

これで容量を購入できたので、ニーズの高まりに合わせてさらに容量を追加できます。 組織内で Premium 容量 SKU の任意の組み合わせ (P1 から P3) を使用できます。 異なる SKU は異なるリソース機能を提供します。

1. Office 365 管理センターで、**[課金]** > **[サービスを購入する]** を選択します。

1. **[その他のプラン]** で、追加購入する Power BI Premium の項目を探します。

1. **省略記号 (...)** にポインターを合わせ、**[ライセンス数の変更]** を選択します。

    ![ライセンス数の変更](media/service-admin-premium-purchase/premium-purchase-more.png)

1. この項目に必要なインスタンス数を変更します。 完了したら **[送信]** を選択します。

   > [!IMPORTANT]
   > **[送信]** を選択すると、登録されているクレジット カードに課金されます。

**[サービスを購入する]** ページに、所有しているインスタンス数が表示されます。 Power BI 管理ポータルの **[容量の設定]** で、購入した新しい容量が利用可能な仮想コア数に反映されます。

![Power BI Premium 容量の利用可能な仮想コア数](media/service-admin-premium-purchase/premium-capacities.png)

## <a name="cancel-your-subscription"></a>サブスクリプションをキャンセルする

Office 365 管理センターから、サブスクリプションのキャンセルを行うことができます。 Premium サブスクリプションをキャンセルするには、次の操作を行います。

![サブスクリプションの取り消し](media/service-admin-premium-purchase/premium-cancel-subscription.png)

1. Office 365 管理センターを参照します。

1. **[請求]** > **[サブスクリプション]** の順に選択します。

1. 一覧から Power BI Premium サブスクリプションを選択します。

1. **[More actions]\(その他の操作)** ドロップダウンで、**[サブスクリプションのキャンセル]** を選択します。

    ![その他のアクション](media/service-admin-premium-purchase/o365-more-actions.png)

1. **[サブスクリプションのキャンセル]** ページに [中途解約料](https://support.office.com/article/early-termination-fees-6487d4de-401a-466f-8bc3-c0beb5cc40d3) を支払う必要があるかどうかが表示されます。 このページでは、サブスクリプションのデータが削除されるタイミングを確認することもできます。

1. 情報に目を通し、続行する場合は、**[サブスクリプションのキャンセル]** を選択します。

## <a name="next-steps"></a>次の手順

[Power BI の料金ぺージ](https://powerbi.microsoft.com/pricing/)
[Power BI Premium 計算ツール](https://powerbi.microsoft.com/calculator/)
[Microsoft Power BI Premium とは何ですか?](service-premium.md)
[Power BI Premium のよく寄せられる質問](service-premium-faq.md)
[Microsoft Power BI Premium のホワイトペーパー](https://aka.ms/pbipremiumwhitepaper)
[Power BI のエンタープライズ展開の計画に関するホワイト ペーパー](https://aka.ms/pbienterprisedeploy)

他にわからないことがある場合は、 [Power BI コミュニティで質問してみてください](http://community.powerbi.com/)。