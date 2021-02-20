---
description: アドビの FTP サーバーとの安全な転送を設定するための手順です。
keywords: ftp;sftp
title: SFTP を使用したアドビの FTP アカウントへの接続
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 98%

---


# SFTP を使用したアドビの FTP アカウントへの接続

アドビの FTP サーバーとの安全な転送を設定するための手順です。

1. アドビがホストする FTP アカウントを要求します（50 MB の割り当て）。
1. 公開／秘密 RSA 鍵を作成します。Linux では、次のコマンドを実行します。

   ```
   ssh-keygen -t rsa
   ```

   Windows 環境では、puttyGen を使用して鍵を作成します。

1. [!DNL authorized_keys]（拡張子なし）という名前のファイルを作成します。
1. 公開鍵の内容を [!DNL authorized_keys] にコピーします。
1. [!DNL authorized_keys] を FTP アカウントにアップロードします。

   * アドビの FTP アカウントに接続します。
   * [!DNL .ssh] ディレクトリを作成します（存在しない場合）。
   * [!DNL authorized_keys] ファイルを [!DNL .ssh] ディレクトリにアップロードします。

1. SFTP を使用して FTP アカウントにログインし、接続をテストします。

詳しくは、[パスワードなしでの SFTP 経由でのアドビへの接続](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)を参照してください。
