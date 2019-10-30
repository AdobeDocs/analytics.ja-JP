---
description: アドビの FTP サーバーとの安全な転送を設定するための手順です。
keywords: ftp;sftp
seo-description: アドビの FTP サーバーとの安全な転送を設定するための手順です。
seo-title: SFTP を使用したアドビの FTP アカウントへの接続
solution: Analytics
title: SFTP を使用したアドビの FTP アカウントへの接続
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# SFTP を使用したアドビの FTP アカウントへの接続

アドビの FTP サーバーとの安全な転送を設定するための手順です。

1. アドビがホストする FTP アカウントを要求します（50 MB の割り当て）。
1. 公開／秘密 RSA 鍵を作成します。Linux では、次のコマンドを実行します。

   ```
   ssh-keygen -t rsa
   ```

   Windows 環境では、puttyGen を使用して鍵を作成します。

1. Create a file named [!DNL authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

   * アドビの FTP アカウントに接続します。
   * Create a [!DNL .ssh] directory (if it does not already exist).
   * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. SFTPを使用してFTPアカウントにログインし、接続をテストします。

[詳しくは、「パスワードな ](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)しでSFTP経由でアドビに接続する方法」を参照してください。.
