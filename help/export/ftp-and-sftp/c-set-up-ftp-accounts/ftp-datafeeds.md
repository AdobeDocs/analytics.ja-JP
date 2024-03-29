---
description: データフィードは、アドビが受信したクリックストリームデータを書き出したもので、標準およびカスタムの両方のデータフィードを提供します。
keywords: ftp;sftp
title: データフィード
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
source-git-commit: 05b4dc07de567b25e71b47fd92743bee0b5621f8
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 84%

---

# データフィード

>[!NOTE]
>
>次の情報は、FTP および SFTP の宛先タイプに関連しています。 FTP と SFTP は従来の宛先タイプです。 データフィードを設定する場合は、より安全なクラウドの宛先タイプを使用する必要があります。 データフィードのクラウドの宛先タイプの設定について詳しくは、 [データフィードの作成](/help/export/analytics-data-feed/create-feed.md).

データフィードは、アドビが受信したクリックストリームデータを書き出したもので、標準およびカスタムの両方の[データフィード](/help/export/analytics-data-feed/data-feed-overview.md)を提供します。

Adobe Data Warehouse、[!UICONTROL 標準データフィード]を購入済みの場合は、独自の Analytics データフィードを設定できます。標準データフィードは、任意の FTP アカウントに送信できます（アドビが設定するアカウントでも、外部 FTP でも使用できます）。Adobe Engineering Services は、ほとんどどのような方法でも送信できるカスタム[!UICONTROL データフィード]を提供します。

[!UICONTROL データフィード] FTP アカウントでは、デフォルトで 10GB を保持できます。他のすべての標準 FTP アカウントの場合は、デフォルトで 50 MB です。お客様が適切な使用目的で FTP アカウントを使用している場合でも、トラフィックの量が増えるとすぐにこれらのアカウントの容量がいっぱいになることがあります。FTP アカウントがいっぱいになると、ファイルをアカウントにプッシュできなくなります。したがって、FTP アカウントに配信されるファイル（[!UICONTROL データフィード]、Data Warehouse リクエストなど）も配信されなくなります。そのため、受信およびダウンロードが完了したファイルを削除し、アドビの FTP アカウントを管理することが重要です。

FTP アカウントがいっぱいになった場合は、現在あるファイルをダウンロードおよび削除して、容量を確保したことをアドビに通知してください。通知があった後、配信されなかったファイルを再送信します。Data Warehouse などの一部のツールでは、ユーザーがこれらのファイルを再送信することができます。アドビの関与なく再送信できる場合があります。FTP アカウントがいっぱいになることが頻繁にある場合は、アドビカスタマーケアにご連絡ください。アカウントの FTP 容量やファイル数の割り当ての増加など、利用できる配信オプションについてご提案します。
