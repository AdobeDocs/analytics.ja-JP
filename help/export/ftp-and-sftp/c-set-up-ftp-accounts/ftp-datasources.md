---
description: Analytics を使用して、FTP ベースのデータソースを作成および管理できます。このデータソースは、FTP ファイル転送を利用して、オフラインデータまたは履歴データを Experience Cloud に読み込みます。
keywords: ftp;sftp
title: データソース
uuid: 41ba2de7-d33d-4394-b7d8-04a116f45419
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# データソース

Analytics を使用して、FTP ベースのデータソースを作成および管理できます。このデータソースは、FTP ファイル転送を利用して、オフラインデータまたは履歴データを Experience Cloud に読み込みます。

データソースインスタンス作成後、データソースファイルのアップロードに使用できる FTP ロケーションが提供されます。アップロードされたデータはデータソースで自動的に検出され、処理されます。ファイルの処理後、データを Analytics レポートに使用できるようになります。

The [!UICONTROL Create] tab in the Data Sources Manager lets you configure a new Data Sources instance for the selected report suite. The [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

In the [!UICONTROL Manage Data Sources] window, find your data source and select the FTP Info link. FTPログイン情報が、セクションのウィ [!UICONTROL Activate a Data Source] ンドウに表示さ [!UICONTROL Upload/FTP Information] れます。

FTPの制限とデータ保持期間について詳しくは、 [FTPの制限とデータ保持期間を参照してください](/help/export/ftp-and-sftp/ftp-limits.md)。

## 分類およびデータソースのアップロードの .fin ファイルについて {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. この [!DNL .fin] ファイルは、完了通知ファイルです。このファイルは、データファイルが FTP アカウントに完全にアップロードされたことをシステムに通知します。[!DNL .fin] ファイルがアップロードされることで、お客様が読み込みデータのアップロードを完了したことをアドビで認識できます。このファイルが送信された後、アドビでは両方のファイルを FTP から削除し、読み込みの処理を開始します。ファイルの読み込み：[!DNL Classifications.tab]

ファイルの終了：[!DNL Classifications.fin]

データソースまたは SAINT ファイルをアップロードしても、[!DNL .fin] ファイルをアップロードしないと、処理のためのキューに追加されません。ファイルは FTP に残ったままになり、[!UICONTROL Experience Cloud] のデータに適用されません。You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of reporting. このフィールドに電子メールアドレスを入力していない場合、通知は送信されません。

ファイルをアップロードし、[!DNL .fin] ファイルをアップロードしたが、ファイルにエラーがある場合、ファイルは処理のために送信されますが、エラーによって処理が中止され、ファイルはエラーフォルダーに送信されます。If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. 電子メールアドレスを入力していない場合、通知は送信されません。
