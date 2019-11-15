---
description: パスワードを使用しないでFTPアカウントに接続する方法は、SFTP接続と代替認証方法の両方を使用する場合にのみ可能です。 この方法では、公開鍵と秘密鍵の組み合わせと呼ばれる一対のファイルを使用します（1 つは FTP アカウントに、もう 1 つはユーザーのコンピューター上に配置します）。
keywords: ftp;sftp
solution: Analytics
title: パスワードなしでの SFTP 経由でのアドビへの接続
uuid: 88728309-50d2-450b-b0e6-7dcdf61b5dbc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# パスワードなしでの SFTP 経由でのアドビへの接続

パスワードを使用しないでFTPアカウントに接続する方法は、SFTP接続と代替認証方法の両方を使用する場合にのみ可能です。 この方法では、公開鍵と秘密鍵の組み合わせと呼ばれる一対のファイルを使用します（1 つは FTP アカウントに、もう 1 つはユーザーのコンピューター上に配置します）。

この方法の安全性は、パスワード認証を使用した場合と変わりません。ユーザーが毎回パスワードを入力しなくても認証できる方式です。正しく使用すれば、これらのファイルを使用することで、パスワードを指定しなくても特定のコンピューターからログインできます。これは、コンピューターごとに設定する必要があります。これらの鍵のファイルを使用しない他のすべての接続では、パスワードを指定する必要があります。

一部のクライアントでは、機密データを送信するためにSFTP（セキュアファイル転送プロトコル）が必要です。 SFTP接続は、暗号化されたデータ通信を可能にするので、通常のFTP接続よりも安全です。 デフォルトでは、すべてのアドビのFTPアカウントがSFTPに対応しています。 SFTP接続は、有効なユーザー名とパスワードを使用して開くことができます。これには、ポート22で接続するSFTPクライアントを使用します（安全でない通常のFTP接続では、ポート21を使用します）。

SFTPを使用する場合、特定の条件下で、秘密鍵を使用してパスワードなしでアカウントに接続できます。 この方法を使用することで、コンピューターで、通常のパスワード認証の代わりに、鍵のファイルを認証に使用できます。つまり、秘密鍵を保持するコンピューターのみがパスワードなしで接続できます。他のすべてのコンピューター／ユーザーは、引き続きパスワード認証を使用する必要があります（それらの他のコンピューターにも秘密鍵が設定されている場合を除きます）。

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

   公開鍵をアップロードして、テストします。Connect to the Adobe FTP account and create a [!DNL .ssh] directory, if it does not already exist. Upload the [!DNL authorized_keys] file to this [!DNL .ssh] directory. これには様々な方法があります（コマンドライン、GUI の FTP クライアントなど）。ディレクトリを作成し、ファイルをアップロードできればどのような方法でもかまいません。

   ここでも、UNIX シェルを使用して行う例を示します。

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

