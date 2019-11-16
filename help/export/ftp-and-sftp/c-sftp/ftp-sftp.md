---
description: SFTPは、データを転送するための安全なプロトコルであり、自分以外の誰もデータを見ることができないようにします。 Adobe Engineering Servicesでは、SFTPアカウントを設定して、データを安全に保持できます。
keywords: ftp;sftp
solution: Analytics
title: セキュアファイル転送プロトコル - 概要
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# セキュアファイル転送プロトコル - 概要

SFTPは、データを転送するための安全なプロトコルであり、自分以外の誰もデータを見ることができないようにします。 Adobe Engineering Servicesでは、SFTPアカウントを設定して、データを安全に保持できます。

## プッシュ配信 {#section_A47831BB1DCA490BB57F0940617AA506}

これは、アドビのサーバーがファイルをユーザーのサーバーに「プッシュ」することを意味しています。基本的に、ファイルはエンドポイントに配信されます。

[Data Warehouseと](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) Analyticsのデータフィードは [](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) 、SFTP経由でデータをプッシュできます。

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## プル配信 {#section_FA29FAEF02FE40B8B32452146A036F48}

これは、通常の FTP を使用して、アドビのいずれかのサーバーにファイルが送信されることを意味しています。ファイルをサーバー上に置く場合は、お使いのサーバーからアドビのFTPサーバーにSFTPを使用して、ファイルをアドビのサーバーから取り出す必要があります。 これは、以下の 3 つの方法のうちいずれかを使用して行うことができます。

* [パスワードなしでの SFTP 経由でのアドビへの接続.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [SFTPを使用してアドビのFTPアカウントに接続します。](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* データフィード、Reports &amp; Analytics、Ad Hoc Analysis などの任意のレポートをアドビの FTP にプッシュしたり、アドビの FTP から取得したりできます。アドビは、これらのレポートを設定済みのSFTPサーバーに配信できません。

