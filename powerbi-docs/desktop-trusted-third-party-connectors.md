---
title: Power BI でのサード パーティ製のコネクタの信頼
description: Power BI で署名されたサードパーティ製コネクタの信頼する方法
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 30b7457c6149320c43f24b967a842382821b01b1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607774"
---
# <a name="trusting-third-party-connectors"></a>サードパーティ製のコネクタを信頼します。

## <a name="why-do-you-need-trusted-third-party-connectors"></a>信頼されたサード パーティ製のコネクタを必要な理由

Power BI で一般的な推奨事項、上位のレベル、マイクロソフトで認定されていないコードの読み込みが原因で、'データ拡張機能のセキュリティ' レベルを維持します。 ただし、特定のコネクタ - 次のように記述した、またはコンサルタントまたは Microsoft の証明書のパスの外部のベンダーによって提供されるものをロードする多くの場合があります。

指定されたコネクタの開発者は、証明書を使用して署名しのセキュリティ設定を下げることがなく安全にロードする必要がある情報を提供できます。

それらについて確認できるセキュリティ設定の詳細を確認するには場合、[ここ](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)します。

## <a name="using-the-registry-to-trust-third-party-connectors"></a>レジストリを使用して、サードパーティ製のコネクタの信頼

Power BI でのサード パーティ製のコネクタを信頼する側は、指定されたレジストリ値を信頼する証明書の拇印の一覧を表示して行われます。 この拇印には、ロードするコネクタの証明書の拇印が一致するは、Power BI の [推奨] セキュリティ レベルでこれを読み込むことができます。 

レジストリ パスでは、HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop です。 作成またはパスが存在するかどうかを確認します。 編集するローカル コンピューターの管理アクセスを必要とすると、IT ポリシーによって制御されている主にしているため、この場所を選択しました。 

![信頼済みのサードパーティ製キーなしで power BI Desktop のレジストリ設定](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

上記で指定したパスの下の新しい値を追加します。 クラスを対象に「複数行文字列の値」(REG_MULTI_SZ) と"TrustedCertificateThumbprints"を呼び出す必要があること 

![信頼されたサード パーティ製のコネクタがないキーのエントリを使って power BI Desktop のレジストリ](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

信頼する証明書の拇印を追加します。 「\0」を使用して、区切り記号、または右クリックして レジストリ エディターで、複数の証明書を変更し、各拇印を新しい行に配置を追加することができます。 サムプリントの例は、自己署名証明書から取得されます。 

 ![信頼されたサード パーティのキーを使用して power BI Desktop のレジストリ設定](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

手順については、適切に従っているし、開発者から適切な拇印が与えられている場合に安全に信頼コネクタが関連付けられている証明書で署名することがなります。

## <a name="how-to-sign-connectors"></a>コネクタに署名する方法

Power Query のドキュメントについて読むことができますかサインインする必要がある開発者にコネクタがある場合[ここ](https://docs.microsoft.com/power-query/handlingconnectorsigning)します。
