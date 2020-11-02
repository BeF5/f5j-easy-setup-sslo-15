SSLO Guided ConfigurationによるSSLOの設定
=========================================================

#. **SSL Orchestrator >> Configuration** を選択します。**DNS** と **NTP** と **Route** が **Configure** となっているのを確認し、:guilabel:`Next` ボタンを押します。

    .. image:: images/mod7-1.png
    |  
#. **任意の名前** を設定し、SSL Orchestrator Topologiesとして、**L3 Explicit Proxy** を選択し、:guilabel:`Save＆Next` ボタンを押します。

    .. image:: images/mod7-2.png
    |  
#. **Create New** を設定し、右上の :guilabel:`Show Advanced Setting` をクリックします。

    .. image:: images/mod7-3.png
    |  
#. **Client-side SSL** にて、利用したい **TLSのバージョン** を選択します。

    .. image:: images/mod7-4.png
    |  
#. **CA Certificate KeyChain** にて、既にインポート済みのCAファイル（F５ハンズオンでは、証明書と秘密鍵に **f5jCA** を選択し、Passphraseに **f5demo** と入力します。）を選択して :guilabel:`Done` を押します。

    .. image:: images/mod7-5.png
    |  
#. **Server-side SSL** も同様に利用したい **TLSバージョン** を選択します。

    .. image:: images/mod7-6.png
    |  
#. 期限切れの証明書や自己署名証明書に対しての動作も確認し、:guilabel:`Save＆Next` を押します。

    .. image:: images/mod7-7.png
    |  
#. :guilabel:`Add Service` を押します。

    .. image:: images/mod7-8.png
    |  
#. **Generic Inline Layer2** を選択し、:guilabel:`Add` ボタンを押します。

    .. image:: images/mod7-9.png
    |  
#. 右上の :guilabel:`Show Advanced Setting` をクリックし、**任意の名前** を設定します。

    .. image:: images/mod7-10.png
    |  
#. **Network Configuration** の **From BIGIP VLAN** にて **Create New** を選択し、任意の名前を設定し、**Interface** を選択します。同様に、**To BIGIP VLAN** も設定します。（F5ハンズオンでは、名称は任意で構いませんが、Interfaceはそれぞれ、**1.3** と **1.4** を選択します。）:guilabel:`Done` ボタンを押します。

    .. image:: images/mod7-11.png
    |  
#. L2デバイスの受信ポートに応じて、ポートリマップを行います。（L2デバイスの仕様によっては不要です。）　**Enable Port Remap** にチェックをいれ、**Remap Port** に必要なポート番号を設定し、:guilabel:`Save` ボタンを押します。（F5ハンズオンでは、**8080** と設定しておきます。）

    .. image:: images/mod7-12.png
    |  
#. 以下のようにサービスが追加されているのを確認したら、:guilabel:`Save＆Next` を選択します。

    .. image:: images/mod7-13.png
    |  
#. **Service Chain List** で :guilabel:`Add` を押します。

    .. image:: images/mod7-14.png
    |  
#. **任意の名前** を設定し、先程作成したサービスを右に移動させ、:guilabel:`Save` ボタンを押します。

    .. image:: images/mod7-15.png
    |  
#. **Service Chain** ができたことを確認し、:guilabel:`Save＆Next` ボタンを押します。

    .. image:: images/mod7-16.png
    |  
#. All Trafficの :guilabel:`ペンマーク` をクリックします。

    .. image:: images/mod7-17.png
    |  
#. 先程作成した **Service Chain** を選択し、:guilabel:`OK` ボタンを押します。

    .. image:: images/mod7-18.png
    |  
#. サービスチェーンが追加されたことを確認し、:guilabel:`Save＆Next` ボタンを押します。

    .. image:: images/mod7-19.png
    |  
#. **Proxy Server Settings** にクライアントからプロキシとしてアクセスさせるIPアドレスを入力し、**Ingress Network** として、クライアントからアクセス可能な **VLAN** を選択し、:guilabel:`Save＆Next` ボタンを押します。

    .. image:: images/mod7-20.png
    |  
#. **Manage SNAT Settings** で **Auto Map**、**Gateways** で **Default Route** を選択し、:guilabel:`Save＆Next` ボタンを押します。(F5ハンズオンではこのように設定しますが、環境に合わせてください。)

    .. image:: images/mod7-21.png
    |  
#. :guilabel:`Save＆Next` ボタンを押します。

    .. image:: images/mod7-22.png
    |  
#. 必要に応じて、設定内容を見直し、 :guilabel:`Save＆Next` ボタンを押します。

    .. image:: images/mod7-23.png
    |  
#. Successポップアップが表示されます。:guilabel:`OK` ボタンを押します。

    .. image:: images/mod7-24.png
    |  
#. Deployに成功すると以下のような緑色の **DEPLOYED** マークが表示されます。右上の **System Settings** アイコンを選択します。

    .. image:: images/mod7-25.png
    |  
#. SSLOがExplicit Proxyとして利用する **DNS** を設定し、:guilabel:`Deploy` を押します。

    .. image:: images/mod7-26.png
    |  
#. Successポップアップが表示されます。:guilabel:`OK` ボタンを押します。

    .. image:: images/mod7-27.png
    |  