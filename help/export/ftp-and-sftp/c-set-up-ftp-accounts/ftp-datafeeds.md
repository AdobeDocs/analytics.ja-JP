---
description: データフィードは、アドビが受信したクリックストリームデータを書き出したもので、標準およびカスタムの両方のデータフィードを提供します。
keywords: ftp;sftp
title: データフィード
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
TQID: https://experienceleague.adobe.com/SWXC-g3KTGuKiT0CBFfptUSBigs8pgkPVdRLzWhl6z4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 28%

---

# データフィード

>[!NOTE]
>
>次の情報は、FTPおよびSFTPの宛先タイプに関連しています。 FTPとSFTPは従来の宛先タイプです。 データフィードを設定する際には、より安全なクラウド宛先タイプを使用する必要があります。 データフィードのクラウド宛先タイプの設定について詳しくは、[&#x200B; データフィードの作成](/help/export/analytics-data-feed/create-feed.md)を参照してください。

データフィードは、アドビが受信したクリックストリームデータを書き出したもので、標準およびカスタムの両方の[データフィード](/help/export/analytics-data-feed/data-feed-overview.md)を提供します。

Adobe Data Warehouse、[!UICONTROL 標準データフィード]を購入済みの場合は、独自の Analytics データフィードを設定できます。 これらは、任意のFTP アカウント（Adobeで設定されたもの、または外部FTP）に送信できます。 Adobe Engineering Servicesでは、事実上あらゆる手段で送信できるカスタム [!UICONTROL &#x200B; データフィード &#x200B;]を提供しています。

[!UICONTROL &#x200B; データフィード &#x200B;]のFTP アカウントは、10 GBを許可します（デフォルト）。 他のすべての標準 FTP アカウントの場合は、デフォルトで 50 MB です。 クライアントが意図した適切な使用のためにFTP アカウントを使用している場合、トラフィック量が多い一部のユーザーは、これらのアカウントを素早く埋めることができます。 FTP アカウントがいっぱいになると、追加のファイルをプッシュすることはできません。 したがって、FTP アカウントに配信されるファイル（[!UICONTROL データフィード]、Data Warehouse リクエストなど）も配信されなくなります。 これは、受信してダウンロードしたファイルを削除して、Adobe FTP アカウントを管理することが重要な理由の1つです。

FTP アカウントがいっぱいになったら、現在のファイルをダウンロードして削除し、スペースがクリアされたことをAdobeに知らせる必要があります。 その後、Adobeは配信されていないファイルを再送信できます。 データウェアハウスなどの一部のツールでは、ユーザーはこれらのファイルを再送信できます。 再送信する場合は、Adobeの関与が必要ない場合があります。 FTP アカウントが頻繁に入力されているようであれば、Adobe カスタマーケアにお問い合わせください。これは、アカウントのFTP スペースとファイル番号の割り当てを増やすことも可能な配信の代替手段を提案できます。
