---
description: アドビの FTP サーバーとの安全な転送を設定するための手順です。
keywords: ftp;sftp
seo-description: アドビの FTP サーバーとの安全な転送を設定するための手順です。
seo-title: SFTPを使用したアドビFTPアカウントへの接続
solution: Analytics
title: SFTPを使用したアドビFTPアカウントへの接続
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# SFTPを使用したアドビFTPアカウントへの接続

アドビの FTP サーバーとの安全な転送を設定するための手順です。

1. アドビがホストする FTP アカウントを要求します（50 MB の割り当て）。
1. 公開／秘密 RSA 鍵を作成します。Linux では、次のコマンドを実行します。

   ```
   ssh-keygen -t rsa
   ```

   Windows 環境では、puttyGen を使用して鍵を作成します。

1. [!DNL authorized_keys] （拡張子なしの）ファイルを作成します。
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

   * アドビの FTP アカウントに接続します。
   * [!DNL .ssh] ディレクトリを作成します（まだ存在しない場合）。
   * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. SFTPを使用してFTPアカウントにログインし、接続をテストします。

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846).
