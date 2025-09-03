インターネット接続環境に関して調査してみた

接続方式例
・ipv4 over ipv6
・IPoEとPPPoE自動切換え
・NAT64 / DNS64 
・ipv4とipv6デュアルスタック

ipconfig /allを確認したところipv4,ipv6両アドレスが割り当てられていることを確認
curl ifconfig.~でipv4とipv6のグローバルIPアドレスを調査したところ、ipv4はisp側でNATされていることが判明した。（ipv6はNATなし）
また、ping -4 google.comやping -6 google.comも疎通する。（nslookup google.comなども確認）
さらにrasdialの結果は、接続中のPPPoEセッションはなしであった。
上記より「ipv4とipv6デュアルスタック環境」であることがわかった。


