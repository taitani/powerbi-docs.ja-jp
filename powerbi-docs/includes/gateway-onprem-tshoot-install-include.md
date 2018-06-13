## <a name="update-to-the-latest-version"></a>最新のバージョンに更新する
多くの問題は、ゲートウェイのバージョンが期限切れになると発生します。  常に最新のバージョンを使用することは一般に適切な方法です。  ゲートウェイを 1 か月以上更新していない場合は、ゲートウェイの最新バージョンのインストールを検討して問題が再発するかどうかを確認することをお勧めします。

## <a name="common-issues"></a>一般的な問題
ここでは、インターネット アクセスが制限されている環境でのユーザーに役立つ、一般的な問題と解決策について説明します。

### <a name="authentication-to-proxy-server"></a>プロキシ サーバーへの認証
プロキシは、ドメイン ユーザー アカウントからの認証を必要とする場合があります。 既定では、ゲートウェイは Windows サービスのログオン ユーザーのサービス SID を使用します。 ログオン ユーザーをドメイン ユーザーに変更すると、この認証に役立ちます。 詳細については、「[ドメイン ユーザーへのゲートウェイ サービス アカウントの変更](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user)」をご覧ください。

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>プロキシはポート 80 と 443 のトラフィックのみを許可する
一部のプロキシは、トラフィックをポート 80 と 443 のみに制限します。 既定では、Azure Service Bus への通信は 443 以外のポートで行われます。

ゲートウェイと Azure Service Bus との間の通信に、直接 TCP ではなく HTTPS を使用するように強制できます。 *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* ファイルを変更する必要があります。 値を `AutoDetect` から `Https` に変更します。 このファイルは、既定では *C:\Program Files\On-premises data gateway* にあります。

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>インストール
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>エラー: ユーザーをグループに追加できませんでした。  (-2147463168   PBIEgwService   Performance Log Users   )
ゲートウェイをドメイン コントローラーにインストールしようとした場合に、このエラーが発生することがあります。 ドメイン コントローラーへの展開はサポートされていません。 ゲートウェイは、ドメイン コントローラーではないコンピューターに展開する必要があります。

### <a name="installation-fails"></a>インストールに失敗しました
インストール コンピューター上のウイルス対策ソフトウェアが古いと、インストールに失敗することがあります。 ウイルス対策のインストールを更新するか、ゲートウェイのインストールが完了するまでの間だけウイルス対策を無効にし、その後、ウイルス対策を再度有効にすることができます。

