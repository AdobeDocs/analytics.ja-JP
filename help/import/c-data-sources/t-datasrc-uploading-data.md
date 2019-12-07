---
description: データソースファイルのアップロード方法を説明した手順です。
subtopic: Data sources
title: データソースファイルのアップロード
topic: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# データソースファイルのアップロード

データソースファイルのアップロード方法を説明した手順です。

データソースのデータファイルを準備したら、処理を行うためにそのファイルをデータソースに送信します。アドビが管理するデータソース FTP サーバーがいくつかあり、このサーバーにデータソースファイルをアップロードすることができます。データソース FTP サーバーについて、次の点に注意してください。

* Select FTP Info next to the Data Source entry in the [!UICONTROL Data Sources Manage] tab to see the FTP Host, Login, and Password information for the data source's FTP account. この情報にアクセスできるユーザーは誰でも、データをレポートスイートにアップロードできます。
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

