---
description: データフィードは、アドビが受信したクリックストリームデータを書き出したもので、標準およびカスタムの両方のデータフィードを提供します。
keywords: ftp;sftp
title: データフィード
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
translation-type: tm+mt
source-git-commit: fc14751c810019c5257a23a8a598b16f42ed10ee

---


# データフィード

データフィードは、アドビが受信したクリックストリームデータを書き出したもので、標準およびカスタムの両方の[データフィード](/help/export/analytics-data-feed/data-feed-overview.md)を提供します。

If you have purchased Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] you can set up your own Analytics data feeds. 標準データフィードは、任意の FTP アカウントに送信できます（アドビが設定するアカウントでも、外部 FTP でも使用できます）。Adobe Engineering Services offers custom [!UICONTROL Data Feeds] that can be sent by virtually any means.

[!UICONTROL Data Feed]FTPアカウントでは、10 GB（デフォルト）を使用できます。 他のすべての標準 FTP アカウントの場合は、デフォルトで 50 MB です。お客様が適切な使用目的で FTP アカウントを使用している場合でも、トラフィックの量が増えるとすぐにこれらのアカウントの容量がいっぱいになることがあります。FTP アカウントがいっぱいになると、ファイルをアカウントにプッシュできなくなります。Therefore, any files being delivered to that FTP account ( [!UICONTROL Data Feeds], data warehouse requests, and so forth) are not delivered. そのため、受信およびダウンロードが完了したファイルを削除し、アドビの FTP アカウントを管理することが重要です。

FTP アカウントがいっぱいになった場合は、現在あるファイルをダウンロードおよび削除して、容量を確保したことをアドビに通知してください。通知があった後、配信されなかったファイルを再送信します。Data Warehouse などの一部のツールでは、ユーザーがこれらのファイルを再送信することができます。アドビの関与なく再送信できる場合があります。FTP アカウントがいっぱいになることが頻繁にある場合は、アドビカスタマーケアにご連絡ください。アカウントの FTP 容量やファイル数の割り当ての増加など、利用できる配信オプションについてご提案します。
