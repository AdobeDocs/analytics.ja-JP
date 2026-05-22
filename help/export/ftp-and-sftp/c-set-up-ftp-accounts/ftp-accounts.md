---
description: アドビがホストする FTP アカウントを設定して使用します。
keywords: ftp;sftp
title: FTP アカウントの設定 - 概要
feature: FTP Export
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
TQID: 'https://experienceleague.adobe.com/dB-Sb1aM5VYz5FAkvxOunFGeAQvttU7vxCjjqj1pesQ'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 6%

---

# FTPまたはSFTP アカウントの設定 – 概要

AdobeでホストされているFTPまたはSFTP アカウントを設定して使用します。

Adobeは、ファイル転送の信頼性を向上させるように特別に設計された、高可用性の高性能FTPまたはSFTP クラスターを維持しながら、高パフォーマンスを維持します。

Adobeのお客様は、メンテナンスイベントがスケジュールされているため、標準プロセスを通じてメンテナンス通知を受け取ります。 AdobeのFTPまたはSFTP システムが設計通りに機能し、安全で信頼性の高い高性能なデータ転送を提供し続けるように、Adobeでは次のガイドラインに準拠することを求めています。

* ほとんどのAdobe FTPまたはSFTP アカウント（分類、データソースなど）は、特定の機能が設定されると自動的に有効になります。 データフィードおよび一般的なファイル配信アカウントの場合、Adobe カスタマーケアは新しいFTPまたはSFTP アカウントを設定できます。 このプロセスは、FTPまたはSFTP アカウントでセキュリティとスペースの両方を使用できるようにするために設定されています。
* ユーザーは、データがシステムに正常に転送された後、AdobeによってFTPまたはSFTP アカウントに配信されたデータを削除する必要があります。
* FTPまたはSFTP アカウントが不要になったときにAdobeに通知し、非アクティブ化できるようにします。

アドビの FTP ホスト名は、`ftp://ftp.omniture.com` または `ftp://ftp2.omniture.com` です。

この情報は、ユーザー名とパスワードとともに、CX Enterprise （分類とデータソース用）内で、またはリクエスト時にアカウントの設定を担当するAdobe担当者から提供する必要があります。 使用するFTPまたはSFTP アドレスがわからない場合は、Adobe アカウントチームにお問い合わせください。 また、分類およびデータソースアカウントの場合、Adobeには、FTPまたはSFTP ファイルが処理される特定の時間帯はありません。 代わりに、Adobeは、新しいファイルプロセスを求めてFTP アカウントまたはSFTP アカウントを常にポーリングするスクリプトを使用します。 これらのアカウントにアップロードされたファイルは、可能な限り迅速に処理されます。
