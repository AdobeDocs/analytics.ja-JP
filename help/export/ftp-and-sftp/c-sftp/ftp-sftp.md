---
description: SFTP は、データ転送を安全に行うためのプロトコルであり、当事者以外がデータを盗み見ることはできません。 Adobe Engineering Services では、データを安全に保持するために SFTP アカウントを設定できます。
keywords: ftp;sftp
title: セキュアファイル転送プロトコル - 概要
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
TQID: https://experienceleague.adobe.com/kJYtQSuxz-2NMUYqZb01wsr6ltQQbD5itpPYYzsmlCM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 220
ht-degree: 80%

---

# セキュアファイル転送プロトコル - 概要

SFTPは、データを転送するための安全なプロトコルであり、誰もがあなたのデータを見ることができないことを保証します。 Adobe Engineering Services では、データを安全に保持するために SFTP アカウントを設定できます。

## プッシュ配信 {#section_A47831BB1DCA490BB57F0940617AA506}

つまり、Adobeのサーバーは、ファイルをサーバーに「プッシュ」します。 基本的にエンドポイントに配信します。

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) と [Analytics のデータフィード](/help/export/analytics-data-feed/data-feed-overview.md)は、SFTP 経由でデータをプッシュできます。

Report Builder **では、SFTP経由でデータをプッシュできません**。

## プル配信 {#section_FA29FAEF02FE40B8B32452146A036F48}

これは、通常の FTP を使用して、アドビのいずれかのサーバーにファイルが送信されることを意味しています。 ユーザーが各自のサーバーにファイルを取得したい場合は、各自のサーバーからアドビの FTP サーバーへの SFTP 接続を使用して、アドビのサーバーからファイルを取得する必要があります。 これは、以下の 3 つの方法のうちいずれかを使用して行うことができます。

* [パスワードなしでの SFTP 経由でのアドビへの接続。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [SFTP を使用したアドビの FTP アカウントへの接続](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* データフィード、Reports &amp; Analytics、Ad Hoc Analysis などの任意のレポートをアドビの FTP にプッシュしたり、アドビの FTP から取得したりできます。 アドビは、これらのレポートをユーザーが設定した SFTP サーバーに配信することはできません。
