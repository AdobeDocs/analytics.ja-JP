---
title: SFTP サービスのアップグレード — FAQ
description: 2022 年 5 月に予定されている SFTP サービスのアップグレードに関するよくある質問 (FAQ) です。
source-git-commit: eb9bdcbd99d45afc913c5ade37e8fb5c62a3a456
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---


# SFTP サービスのアップグレード — FAQ

オン **2022 年 5 月 3 日**、Adobe Analyticsは Secure File Transfer Protocol をアップグレードします [SFTP] ファイル転送のセキュリティを強化するためのサービス。 この変更により、一部の SFTP クライアント設定はサポートされなくなります。 また、次の方法で利用できる接続オプションもいくつか追加します。 **2022 年 3 月 2 日**. これは、SFTP を使用してAdobe Analyticsに送信された、またはから取得されたデータにのみ影響します。 FTP プロトコルに影響はありません。 サービスの中断を避けるために、SFTP クライアント（コード、ツール、サービス）が以下に説明する変更に従っていることを確認してください。

## 組織で現在使用されているアルゴリズム、接続タイプ、プロトコルをどのように判断できますか？

使用している FTP/SFTP ソフトウェアは、Adobe Analyticsとのデータ交換用に設定した接続で使用されている特定の設定を示す必要があります。 このソフトウェアには、接続に使用できる様々なオプションに関するドキュメントも含める必要があります。 この更新後にサポートされるオプションは、業界で広くサポートされ、受け入れられています。

## データ取り込みに SFTP を使用するAdobe Analyticsの機能はどれですか？

次の機能には、SFTP を使用してAdobe Analyticsにデータをアップロードするオプションが用意されています。

* [分類](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [データフィード](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [データソース](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Data Warehouse が配信するレポート](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* さらに、 [エンジニアリングサービス](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) は、SFTP を使用してデータをAdobeと交換できます。

## この更新には、具体的な変更が含まれますか？

次に、削除される接続とアルゴリズムの詳細なリストと、それらのリストを示します。

* SFTP プロトコルの mac アルゴリズム：

   * 今後のサポートはおこなわれません。hmac-md5、hmac-md5-96、hmac-ripemd160、hmacripemd160@openssh.com、hmac-sha1、hmac-sha1-96、hmac-sha1-etm@openssh.com、umac-64-etm@openssh.com、umac-64@openssh.com

   * サポート対象は次のみです。hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* SFTP プロトコル暗号アルゴリズム：

   * 今後のサポートはおこなわれません。3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour, arcfour2128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * サポート対象は次のみです。aes128-ctr、aes192-ctr、aes256-ctr

* SFTP プロトコルでサポートされる接続：

   * scp および rsync コマンドや sftp プロトコルを使用した接続の使用はサポートされなくなります

   * 純粋な SFTP プロトコル接続のみサポートします

* サポートされる FTP/SFTP クライアント/プロトコル：

   * FTP:vsftpd バージョン 3.0.2～25 以降

   * SFTP:openssh バージョン 7.4p1～21 以降