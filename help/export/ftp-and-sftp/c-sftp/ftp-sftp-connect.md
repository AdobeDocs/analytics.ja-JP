---
description: アドビの FTP サーバーとの安全な転送を設定するための手順です。
keywords: ftp;sftp
title: SFTP を使用したアドビの FTP アカウントへの接続
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
TQID: 'https://experienceleague.adobe.com/5X1Nx0V0hievpCe9G1Q6gJS1c55T3xl5FuneZxPx4TI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 38%

---

# SFTPでFTP アカウントに接続する

FTPによるセキュアな転送を設定するには：

1. （条件付き）Adobe FTP サーバーとの安全な転送を設定する場合：

   1. AdobeでホストされているFTP アカウント（50 MBのクォータ）をリクエストします。

   1. 公開鍵/秘密鍵を作成します。

      * Linux環境で、以下を実行します。

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        ポリシーでed25519の使用が許可されていない場合は、次を実行します。

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

        **注：**&#x200B;これは通常、新しいFIPS 186-5で最初にサポートされるed25519がFIPS 186-4で動作するお客様に適用されます。

      * Windows環境では、puttyGenを使用します。

1. （条件付き）独自のFTP ロケーションでセキュアな転送を設定する場合は、有効なRSAまたはed25519公開鍵を含むSFTP ホスト、ユーザー名、宛先サイトが必要です。 フィードの作成時に、適切な公開キーをダウンロードできます。

1. [!DNL `authorized_keys`]（拡張子なし）という名前のファイルを作成します。

1. 公開鍵の内容を [!DNL `authorized_keys`] にコピーします。

1. [!DNL `authorized_keys`] を FTP アカウントにアップロードします。

   * アドビの FTP アカウントに接続します。
   * [!DNL .ssh] ディレクトリを作成します（存在しない場合）。
   * [!DNL `authorized_keys`] ファイルを [!DNL .ssh] ディレクトリにアップロードします。

1. SFTP を使用して FTP アカウントにログインし、接続をテストします。

詳しくは、[&#x200B; パスワードなしでSFTP経由でAdobeに接続する](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)を参照してください。

