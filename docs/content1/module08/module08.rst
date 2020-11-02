クライアントからの接続テスト①
=========================================================

#. Windowsクライアントを起動し、プロキシ設定として、SSLOで設定したExplicit Proxyのアドレスとポート番号を設定します。

   .. image:: images/mod8-1.png
       :scale: 60%
       :align: center
   |  
#. ブラウザを開き、任意のHTTPSサイトに接続し、そのサーバ証明書がSSLOで設定したCA証明書によって書換えられていることを確認します。

   .. image:: images/mod8-2.png
   |  
#. curlコマンドで確認する場合は、**curl -vk --proxy 10.1.10.150:3128 https://httpbin.org/get**　と入力し、確認します。

   .. image:: images/mod8-3.png
   |  
#. （オプション）F5ハンズオンではL2デバイスにSSH接続し、tcpdumpコマンドで通信の確認をします。（F５ハンズオンでは、ネットワークブリッジ名は **L2PEOLD** となります。）

   - コマンド例：tcpdump -i L2PEOLD -A -s 0 'tcp port 80 and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)'

   .. image:: images/mod8-4.png
   |  
#. （オプション）NTOPNGでトラフィック確認した場合のイメージです。

   .. image:: images/mod8-5.png
   |  


