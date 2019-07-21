---
description: データフィードは、アドビが受信したクリックストリームデータをエクスポートしたもので、標準およびカスタムの両方のデータフィードを提供します。
keywords: ftp;sftp
seo-description: データフィードは、アドビが受信したクリックストリームデータをエクスポートしたもので、標準およびカスタムの両方のデータフィードを提供します。
seo-title: データフィード
solution: Analytics
title: データフィード
uuid: 3c70eea3- ca59-4aa5-9b11-64e1bb677bfa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# データフィード

データフィードは、アドビが受信したクリックストリームデータをエクスポートしたもので、標準およびカスタムの両方の[データフィード](/help/export/analytics-data-feed/c-getstarted/data-feed-overview.md)を提供します。

If you have purchased Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] you can set up your own Analytics data feeds. 標準データフィードは、任意の FTP アカウントに送信できます（アドビが設定するアカウントでも、外部 FTP でも使用できます）。Adobe Engineering Services は、ほとんどどのような方法でも送信できるカスタム[!UICONTROL データフィード]を提供します。

[!UICONTROL データフィード] FTP アカウントでは、デフォルトで 2 GB または 63 ファイルを保持できます。他のすべての標準 FTP アカウントは、デフォルトで 50 MB です。お客様が適切な使用目的で FTP アカウントを使用している場合でも、トラフィックの量が増えるとすぐにこれらのアカウントの容量がいっぱいになることがあります。FTP アカウントがいっぱいになると、ファイルをアカウントにプッシュできなくなります。したがって、FTP アカウントに配信されるファイル（[!UICONTROL データフィード]、Data Warehouse リクエストなど）も配信されなくなります。そのため、受信およびダウンロードが完了したファイルを削除し、アドビの FTP アカウントを管理することが重要です。

FTP アカウントがいっぱいになった場合は、現在あるファイルをダウンロードおよび削除して、容量を確保したことをアドビに通知してください。通知があった後、配信されなかったファイルを再送信します。Data Warehouse などの一部のツールでは、ユーザーがこれらのファイルを再送信することができます。アドビの関与なく再送信できる場合があります。FTP アカウントがいっぱいになることが頻繁にある場合は、アドビカスタマーケアにご連絡ください。アカウントの FTP 容量やファイル数の割り当ての増加など、利用できる配信オプションについてご提案します。

FTP の制限およびデータ保持期間については、[FTP の制限とデータ保持期間](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E)を参照してください。
