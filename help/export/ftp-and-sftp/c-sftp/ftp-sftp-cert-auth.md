---
description: SFTP 接続と代替認証方法の両方を使用した場合にのみ、パスワードなしで FTP アカウントに接続できます。この方法では、公開鍵と秘密鍵の組み合わせと呼ばれる一対のファイルを使用します（1 つは FTP アカウントに、もう 1 つはユーザーのコンピューター上に配置します）。
keywords: ftp;sftp
title: パスワードなしでの SFTP 経由でのアドビへの接続
uuid: 88728309-50d2-450b-b0e6-7dcdf61b5dbc
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '603'
ht-degree: 100%

---

# パスワードなしでの SFTP 経由でのアドビへの接続

SFTP 接続と代替認証方法の両方を使用した場合にのみ、パスワードなしで FTP アカウントに接続できます。この方法では、公開鍵と秘密鍵の組み合わせと呼ばれる一対のファイルを使用します（1 つは FTP アカウントに、もう 1 つはユーザーのコンピューター上に配置します）。

この方法の安全性は、パスワード認証を使用した場合と変わりません。ユーザーが毎回パスワードを入力しなくても認証できる方式です。正しく使用すれば、これらのファイルを使用することで、パスワードを指定しなくても特定のコンピューターからログインできます。これは、コンピューターごとに設定する必要があります。これらの鍵のファイルを使用しない他のすべての接続では、パスワードを指定する必要があります。

機密データを転送するために、一部のクライアントでは SFTP（セキュアファイル転送プロトコル）が必要です。SFTP では、データを暗号化して通信できるので、通常の FTP 接続よりも安全です。すべてのアドビ FTP アカウントは、デフォルトで SFTP に対応しています。SFTP 接続は、有効なユーザー名とパスワードを指定し、ポート 22 に接続する SFTP クライアントを使用することで確立できます（安全性の低い通常の FTP 接続はポート 21 を使用します）。

SFTP を使用する場合、特定の条件においては、パスワードなしで秘密鍵を使用してアカウントに接続できます。この方法を使用することで、コンピューターで、通常のパスワード認証の代わりに、鍵のファイルを認証に使用できます。つまり、秘密鍵を保持するコンピューターのみがパスワードなしで接続できます。他のすべてのコンピューター／ユーザーは、引き続きパスワード認証を使用する必要があります（それらの他のコンピューターにも秘密鍵が設定されている場合を除きます）。

**パスワードを使用しない認証で秘密鍵を設定して使用するには**

1. FTP アカウントを作成します（アドビ）。

   FTP アカウントがまだない場合は、アドビの担当者が FTP アカウントを作成できます。アドビのアカウントマネージャーまたはアドビカスタマーケアに連絡して、アカウントの作成を依頼します。
1. 公開鍵および秘密鍵を作成します（お客様）。

   公開鍵と秘密鍵の組み合わせを作成します。秘密鍵は、ユーザーのコンピューター／サーバーに配置される非公開のファイルです。公開鍵ファイルは、アドビのアカウントにアップロードする必要があります。このように使用することで、パスワード認証なしで接続できます。アドビのアカウントにアップロードした公開鍵ファイルと、ユーザーのコンピューター／サーバーの秘密鍵ファイルが対となって認証されます。

   これらのファイルを作成するには、社内のネットワークサポートグループと協力して、環境に適した鍵のセットを作成します。これら 2 つのファイルの作成に使用できる様々なツールやアプリケーションがあります。

   例えば、以下に示すように UNIX シェル環境で作成することもできます。これは、作成方法の一例であり、チームや社内ネットワークグループに要件を伝えるときに参考として利用できます。

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. 公開鍵を FTP アカウントにアップロードします（お客様）。

   公開鍵をアップロードして、テストします。アドビの FTP アカウントに接続し、[!DNL .ssh] ディレクトリが存在しない場合は作成します。[!DNL authorized_keys] ファイルをこの [!DNL .ssh] ディレクトリにアップロードします。これには様々な方法があります（コマンドライン、GUI の FTP クライアントなど）。ディレクトリを作成し、ファイルをアップロードできればどのような方法でもかまいません。

   ここでも、UNIX シェルを使用しておこなう例を示します。

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```
