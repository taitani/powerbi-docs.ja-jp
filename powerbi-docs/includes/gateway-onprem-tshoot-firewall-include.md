## <a name="firewall-or-proxy"></a>ファイアウォールまたはプロキシ
ゲートウェイのプロキシ情報の指定については、「[Power BI Gateway のプロキシ設定を構成する](../service-gateway-proxy.md)」を参照してください。

PowerShell プロンプトから [Test-NetConnection](https://technet.microsoft.com/library/dn372891.aspx) を実行して、ファイアウォールまたはプロキシが接続をブロックしている可能性があるかどうかをテストできます。 これは、Azure Service Bus への接続をテストすることになります。 これはネットワーク接続のみをテストし、クラウド サーバー サービスやゲートウェイとはまったく関係ありません。 コンピューターが実際にインターネットに接続できるかどうかを確認するのに役立ちます。

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection を使用できるのは、Windows Server 2012 R2 以降だけです。 Windows 8.1 以降でも使用できます。 これらより前のバージョンの OS では、Telnet を使ってポートの接続をテストできます。
> 
> 

結果は次のようになります。 TcpTestSucceeded の値を確認してください。 **TcpTestSucceeded** が *true* でない場合、ファイアウォールによってブロックされています。

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

すべてを網羅するには、**ComputerName** と **Port** の値を、「[ポート](../service-gateway-onprem.md#ports)」に記載されている値に置き換えます。

ファイアウォールが Azure Service Bus から Azure データ センターへの接続をブロックしている場合もあります。 そのような場合には、お住まいの地域のデータ センターの IP アドレスをホワイトリストに指定 (ブロック解除) します。 Azure IP アドレスのリストは[こちら](https://www.microsoft.com/download/details.aspx?id=41653)で取得できます。

