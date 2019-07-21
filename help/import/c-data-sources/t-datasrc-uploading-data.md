---
description: データソースファイルのアップロード方法を説明した手順です。
seo-description: データソースファイルのアップロード方法を説明した手順です。
seo-title: データソースファイルのアップロード
solution: Analytics
subtopic: データソース
title: データソースファイルのアップロード
topic: 開発者と導入
uuid: 5a9dbc91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# データソースファイルのアップロード

データソースファイルのアップロード方法を説明した手順です。

データソースのデータファイルを準備したら、処理を行うためにそのファイルをデータソースに送信します。アドビが管理するデータソース FTP サーバーがいくつかあり、このサーバーにデータソースファイルをアップロードすることができます。データソース FTP サーバーについて、次の点に注意してください。

* 「[!UICONTROL データソースの管理]」タブでデータソースエントリの横にある「FTP 情報」を選択すると、そのデータソースの FTP アカウントについて FTP ホスト、ログイン、およびパスワードの情報を確認できます。この情報にアクセスできるユーザーは誰でも、データをレポートスイートにアップロードできます。
* セキュリティの都合上、FTP アカウントは 30 日間未使用の状態が続くとクローズされます。
* FTP アカウントは、データソースに固有のものです。1 つの FTP アカウントを使用して、複数のデータソースにデータソースファイルをアップロードすることはできません。

**データソースファイルをアップロードするには**

1. FTP クライアントを使用して、データをデータソース FTP サイトに送信します

   （データソースマネージャーの FTP 情報のリンクから実行できます）。

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   The [!DNL .fin] file must have the exact same name as the Data Sources file, except for the file extension. Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   すべてのデータソースファイルのアップロードが完了するまでは、このファイルをアップロードしないでください。そうしないと、データソースは不完全なファイルを処理しようとします。
1. データソースファイルの処理中、メッセージが表示されていないか確認します。

   ファイルの処理中に発生したエラーはすべてデータソースマネージャーに表示されます。

