---
description: アドビの FTP ポリシーにより、90 日間連続で使用されなかった FTP アカウントについては、アカウントへのアクセスが自動的に無効になります。
keywords: ftp;sftp
title: FTPおよびSFTP アカウントとデータの削除
feature: FTP Export
exl-id: accf2f8d-c22c-4684-ba85-73a286325d0c
TQID: https://experienceleague.adobe.com/7x8bYAZmZ4Bn-7Sbpf7wGFfOQbkxRQ2CsUcXUgVDTPQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 8%

---

# FTPおよびSFTP アカウントとデータの削除

AdobeのFTPおよびSFTP ポリシーは、90日間連続してアイドル状態が続くFTPおよびSFTP アカウントへのアクセスを無効にすることがあります。

その後、Adobeは、無効なFTP アカウントおよびSFTP アカウントを削除し（これらのアカウントに保存されているすべてのデータを完全に削除します）、さらに90日間の猶予期間が経過した後に削除します。 例えば、2025年7月5日から2025年10月2日までの90日間アイドル状態が続くSFTP アカウントは、2025年10月3日に無効になります。 その後、2026年1月2日に完全に削除されます。

2025年10月5日より前に無効になったアカウントはありません。また、2026年1月2日より前に削除されたアカウントはありません。

また、Adobeは、90日間アクセスされていないアクティブなアカウントの古いデータを完全に削除することもできます。

このプロセスを支援し、FTPまたはSFTP環境が引き続き顧客に安全で信頼性の高いデータ転送を提供することを保証するために、お客様に次の操作を依頼します。

* データが社内環境に正常に転送された後、FTPおよびSFTP システムから送信データを削除します。 Adobeは、90日後にシステムに残っているファイルを識別して削除することができます。
* FTPおよびSFTP アカウントが不要になったときにAdobeに通知し、非アクティブ化および削除できるようにします。
