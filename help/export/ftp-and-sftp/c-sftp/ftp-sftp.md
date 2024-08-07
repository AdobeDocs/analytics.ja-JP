---
description: SFTP は、データ転送を安全に行うためのプロトコルであり、当事者以外がデータを盗み見ることはできません。Adobe Engineering Services では、データを安全に保持するために SFTP アカウントを設定できます。
keywords: ftp;sftp
title: セキュアファイル転送プロトコル - 概要
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 88%

---

# セキュアファイル転送プロトコル - 概要

SFTP は、データを転送するための安全なプロトコルで、あなた以外のデータを誰にも見られないようにします。 Adobe Engineering Services では、データを安全に保持するために SFTP アカウントを設定できます。

## プッシュ配信 {#section_A47831BB1DCA490BB57F0940617AA506}

これは、アドビのサーバーがファイルをユーザーのサーバーに「プッシュ」することを意味しています。基本的に、ファイルはエンドポイントに配信されます。

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) と [Analytics のデータフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=ja)は、SFTP 経由でデータをプッシュできます。

Report Builder **SFTP 経由でデータをプッシュできません**。

## プル配信 {#section_FA29FAEF02FE40B8B32452146A036F48}

これは、通常の FTP を使用して、アドビのいずれかのサーバーにファイルが送信されることを意味しています。ユーザーが各自のサーバーにファイルを取得したい場合は、各自のサーバーからアドビの FTP サーバーへの SFTP 接続を使用して、アドビのサーバーからファイルを取得する必要があります。これは、以下の 3 つの方法のうちいずれかを使用して行うことができます。

* [パスワードなしでの SFTP 経由でのアドビへの接続。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [SFTP を使用したアドビの FTP アカウントへの接続](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* データフィード、Reports &amp; Analytics、Ad Hoc Analysis などの任意のレポートをアドビの FTP にプッシュしたり、アドビの FTP から取得したりできます。アドビは、これらのレポートをユーザーが設定した SFTP サーバーに配信することはできません。
