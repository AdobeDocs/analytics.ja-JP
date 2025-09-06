---
title: SFTP サービスのアップグレード - FAQ
description: 予定されている SFTP サービスのアップグレードに関するよくある質問（FAQ）です。
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 100%

---

# SFTP サービスのアップグレード - FAQ

2022年9月20日に、Adobe Analytics は、ファイル転送のセキュリティを向上させるために、セキュアファイル転送プロトコル [SFTP] サービスをアップグレードします。この変更により、一部の SFTP クライアント設定はサポートされなくなります。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、SFTP クライアント（コード、ツール、サービス）が、以下に説明する変更に従っていることを確認してください。

## 組織で現在使用されているアルゴリズム、接続タイプおよびプロトコルを確認するには、どうすればよいですか？

お使いの FTP/SFTP ソフトウェアは、Adobe Analytics とのデータ交換用に設定した接続で使用されている特定の設定を示しています。このソフトウェアには、接続に使用できる様々なオプションに関するドキュメントも含まれています。この更新後にサポートされるオプションは、業界で広くサポートされ、受け入れられています。

削除される接続オプションは、通常は古いものと見なされ、現在のソフトウェアでは使用されません。過去 3 年以内に FTP／SFTP ソフトウェアをアップグレードした場合、標準に準拠した接続が既に存在する可能性があります。

## Adobe Analytics でデータ取り込みに SFTP を使用するのは、どの機能ですか？

次の機能には、SFTP を使用して Adobe Analytics にデータをアップロードするオプションが用意されています。

* [分類](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)

* [顧客属性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=ja)

* [データフィード](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)

* [データソース](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)

* [Data Warehouse が配信するレポート](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)

* さらに、 [エンジニアリングサービス](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md) を通じて作成された一部のカスタム実装では、アドビとのデータ交換に SFTP を使用する場合があります。

## このアップデートには、具体的にはどのような変更が含まれていますか？

以下は、削除される接続とアルゴリズム、およびサポートされる接続とアルゴリズムの詳細なリストです。

* SFTP プロトコルの MAC アルゴリズム：

   * サポートされなくなるもの：hmac-md5、hmac-md5-96、hmac-ripemd160、hmacripemd160@openssh.com、hmac-sha1、hmac-sha1-96、hmac-sha1-etm@openssh.com、umac-64-etm@openssh.com、umac-64@openssh.com

   * サポートされるもの：hmac-sha2-512-etm@openssh.com、hmac-sha2-256-etm@openssh.com、umac-128-etm@openssh.com、hmac-sha2-512、hmacsha2-256、umac-128@openssh.com

* SFTP プロトコルの暗号アルゴリズム：

   * サポートされなくなるもの：3des-cbc、aes128-cbc、aes128-gcm@openssh.com、aes192-cbc、aes256-cbc、aes256-gcm@openssh.com、arcfour、 arcfour128、arcfour256、blowfish-cbc、cast128-cbc、rijndael-cbc@lysator.liu.se

   * サポートされるもの：aes128-ctr、aes192-ctr、aes256-ctr

* SFTP プロトコルでサポートされる接続：

   * scp および rsync コマンドの使用や sftp プロトコルでの接続はサポートされなくなります

   * 純粋な SFTP プロトコル接続のみをサポートします

* サポートされる FTP／SFTP クライアント／プロトコル：

   * FTP：vsftpd バージョン 3.0.2～25 以降

   * SFTP：openssh バージョン 7.4p1～21 以降
