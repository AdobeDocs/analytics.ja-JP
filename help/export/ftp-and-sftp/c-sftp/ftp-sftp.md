---
description: SFTPはデータ転送に安全なプロトコルであり、誰もデータを表示できないことを保証します。Adobe Engineering Servicesは、安全にデータを保持するためにSFTPアカウントを設定できます。
keywords: ftp;sftp
seo-description: SFTPはデータ転送に安全なプロトコルであり、誰もデータを表示できないことを保証します。Adobe Engineering Servicesは、安全にデータを保持するためにSFTPアカウントを設定できます。
seo-title: セキュアファイル転送プロトコル-概要
solution: Analytics
title: セキュアファイル転送プロトコル-概要
uuid: 7dd1a867- e828-4c7b- bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# セキュアファイル転送プロトコル-概要

SFTPはデータ転送に安全なプロトコルであり、誰もデータを表示できないことを保証します。Adobe Engineering Servicesは、安全にデータを保持するためにSFTPアカウントを設定できます。

## プッシュ配信 {#section_A47831BB1DCA490BB57F0940617AA506}

これは、アドビのサーバーがファイルをユーザーのサーバーに「プッシュ」することを意味しています。基本的に、ファイルはエンドポイントに配信されます。

[Data Warehouse](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md#concept_904ADB7B4FE04DCCB90EFDB6D0DB1076) および [Analyticsデータフィード](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) では、SFTP経由でデータをプッシュできます。

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## プル配信 {#section_FA29FAEF02FE40B8B32452146A036F48}

これは、通常の FTP を使用して、アドビのいずれかのサーバーにファイルが送信されることを意味しています。ファイルをサーバー上に配置する場合は、サーバーからアドビのFTPサーバーにSFTPを使用してアドビのサーバーから取得する必要があります。これは、以下の 3 つの方法のうちいずれかを使用して行うことができます。

* [パスワードなしでSFTP経由でアドビに接続します。](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)
* [SFTPを使用してアドビのFTPアカウントに接続します。](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md#concept_01176600188441C6AFB28F5E264D89F8)
* データフィード、Reports &amp; Analytics、Ad Hoc Analysis などの任意のレポートをアドビの FTP にプッシュしたり、アドビの FTP から取得したりできます。アドビは、これらのレポートを設定したSFTPサーバーに配信できません。

