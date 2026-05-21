---
description: SFTP 接続と代替認証方法の両方を使用した場合にのみ、パスワードなしで FTP アカウントに接続できます。 この方法では、公開鍵と秘密鍵の組み合わせと呼ばれる一対のファイルを使用します（1 つは FTP アカウントに、もう 1 つはユーザーのコンピューター上に配置します）。
keywords: ftp;sftp
title: パスワードなしでの SFTP 経由でのアドビへの接続
feature: FTP Export
exl-id: 7ff9511c-50a2-466f-b5af-6bbd59941ce5
TQID: https://experienceleague.adobe.com/qQmzBUalqWjJ7FYow1DBCEfVixzultPI2PJSNhOsLlY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 609
ht-degree: 41%

---

# パスワードなしでの SFTP 経由でのアドビへの接続

SFTP 接続と代替認証方法の両方を使用した場合にのみ、パスワードなしで FTP アカウントに接続できます。 この方法では、公開鍵と秘密鍵の組み合わせと呼ばれる一対のファイルを使用します（1 つは FTP アカウントに、もう 1 つはユーザーのコンピューター上に配置します）。

これはパスワード認証よりも安全ではありません。 これは、ユーザーが毎回パスワードを入力する必要がない別の認証方法です。 これらのファイルを正しく使用すると、パスワードを指定することなく、その特定のコンピューターがログインできるようになります。 これはコンピューターごとに設定する必要があります。 これらのキーファイルを使用しない他のすべての接続では、引き続きパスワードを指定する必要があります。

機密データを転送するために、一部のクライアントでは SFTP（セキュアファイル転送プロトコル）が必要です。 SFTP では、データを暗号化して通信できるので、通常の FTP 接続よりも安全です。 すべてのアドビ FTP アカウントは、デフォルトで SFTP に対応しています。 SFTP 接続は、有効なユーザー名とパスワードを指定し、ポート 22 に接続する SFTP クライアントを使用することで確立できます（安全性の低い通常の FTP 接続はポート 21 を使用します）。

SFTP を使用する場合、特定の条件においては、パスワードなしで秘密鍵を使用してアカウントに接続できます。 この方法を使用すると、通常のパスワード認証の代わりにキーファイルを認証に使用できます。 つまり、秘密鍵を保持するコンピューターのみがパスワードなしで接続できます。 他のすべてのコンピューター/ユーザーは、引き続きパスワード認証を使用する必要があります（他のコンピューターにも秘密鍵が設定されている場合を除く）。

**パスワードなしの認証に秘密鍵を設定して使用するには**

1. FTP アカウントが作成されました（Adobe）。

   Adobeの担当者は、FTP アカウントがまだ存在しない場合は、FTP アカウントを作成できます。 アカウントを作成するには、Adobe アカウントチームまたはAdobe カスタマーケアにお問い合わせください。
1. 公開鍵/秘密鍵の作成（お客様）。

   公開鍵と秘密鍵の組み合わせを作成します。 秘密鍵は、コンピューターやサーバーに対して非公開で、そこに存在するファイルです。 公開鍵ファイルをAdobe アカウントにアップロードする必要があります。 この方法を使用すると、パスワード認証なしで接続できます。 Adobeの公開鍵ファイルは、コンピューター/サーバー上の秘密鍵ファイルと一致し、その方法で認証されます。

   これらのファイルを作成するには、内部ネットワークサポートグループに連絡して、環境に適したキーセットを作成します。 この2つのファイルを作成するために使用できるツールやアプリケーションは多数あります。

   UNIX シェル環境でこれをおこなう方法の例を以下に示します。 これは、タスクをどのように実行できるのかを示す一例にすぎません。また、チームや社内のネットワークグループに要件を伝えるための参考にもなります。

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

   公開鍵をアップロードしてテストします。 アドビの FTP アカウントに接続し、[!DNL .ssh] ディレクトリが存在しない場合は作成します。 [!DNL authorized_keys] ファイルをこの [!DNL .ssh] ディレクトリにアップロードします。 これは、様々な方法（コマンドライン、グラフィカル FTP クライアントなど）で実行できます。 必要なのは、ディレクトリを作成してファイルをアップロードする機能だけです。

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
