クライアントからの接続テスト２
=========================================================

#. Blockingモードへ変更すると、Event logに攻撃として記録され、更にブロックされます。**Security >> Application Security : Security Policies : Policies List >> DVWA_policy** にて、**General Settings** を選択し、**Enforcement Mode** に変更し、:guilabel:`Save` ボタンを選択します。

   .. image:: images/mod10-1.png
   | 
#. :guilabel:`Apply Policy` を押します。

   .. image:: images/mod10-2.png
   | 
#. 再度WindowsクライアントからSQLインジェクションを試みます。

   .. image:: images/mod10-3.png
   | 
#. **Security >> Event Logs : Application : Requests** にて、**Block Alarm Learn** でSQLインジェクションが検出されていることを確認します。

   .. image:: images/mod10-4.png
   |  


