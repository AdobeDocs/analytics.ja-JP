---
description: Analytics を使用して、FTP ベースのデータソースを作成および管理できます。このデータソースは、FTP ファイル転送を利用して、オフラインデータまたは履歴データを Experience Cloud にインポートします。
keywords: ftp;sftp
seo-description: Analytics を使用して、FTP ベースのデータソースを作成および管理できます。このデータソースは、FTP ファイル転送を利用して、オフラインデータまたは履歴データを Experience Cloud にインポートします。
seo-title: データソース
solution: Analytics
title: データソース
uuid: 41ba2de7- d33d-4394- b7d8-04a116f45419
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# データソース

Analytics を使用して、FTP ベースのデータソースを作成および管理できます。このデータソースは、FTP ファイル転送を利用して、オフラインデータまたは履歴データを Experience Cloud にインポートします。

データソースインスタンス作成後、データソースファイルのアップロードに使用できる FTP ロケーションが提供されます。アップロードされたデータはデータソースで自動的に検出され、処理されます。ファイルの処理後、データを Analytics レポートに使用できるようになります。

データソースマネージャーの「[!UICONTROL 作成]」タブでは、選択したレポートスイートに対して新しいデータソースインスタンスを設定できます。[!UICONTROL データソースウィザード]によってデータソーステンプレートを作成する処理が進められ、データをアップロードするための FTP の場所が作成されます。

[!UICONTROL データソースの管理]ウィンドウでは、データソースを検索し、FTP 情報のリンクを選択できます。[!UICONTROL データソースをアクティブにする]ウィンドウの「[!UICONTROL アップロード／FTP 情報]」セクションに、FTP ログイン情報が表示されます。

FTP の制限およびデータ保持期間については、[FTP の制限とデータ保持期間](../../../export/ftp-and-sftp/ftp-limits.md#concept_8CAA1D8F27B3411AB902520AD6C9A70E)を参照してください。

## 分類およびデータソースのアップロードの .fin ファイルについて {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classifications or [!UICONTROL Data Source] file ( [!DNL .tab] or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. [!DNL .fin] このファイルは完了ファイルです。このファイルは、データファイルが FTP アカウントに完全にアップロードされたことをシステムに通知します。[!DNL .fin] ファイルによって、インポートが完了したことがアドビに認識されます。このファイルが送信された後、アドビでは両方のファイルを FTP から削除し、インポートの処理を開始します。ファイルのインポート: [!DNL Classifications.tab]

Finish File: [!DNL Classifications.fin]

If you upload your Data Sources or SAINT file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. レポートの [!UICONTROL FTP アカウントを作成]ウィンドウで、「[!UICONTROL 通知受信者]」として電子メールアドレスを入力している場合にのみ、これについての通知が送信されます。このフィールドに電子メールアドレスを入力していない場合、通知は送信されません。

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. この場合、[!UICONTROL FTP アカウントを作成]ウィンドウで「[!UICONTROL 通知受信者]」フィールドに指定された電子メールアドレスに通知が送信されます。電子メールアドレスを入力していない場合、通知は送信されません。
