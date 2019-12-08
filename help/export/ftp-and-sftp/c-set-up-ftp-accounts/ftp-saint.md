---
description: 分類（SAINT）FTP オプションは、複数のレポートスイートへのデータアップロード機能や、50,000 行を超えるデータセットのアップロード機能など、大規模な分類データセットを柔軟にアップロードできる機能を備えています。
keywords: ftp;sftp
title: 分類
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 分類

分類FTPオプションを使用すると、複数のレポートスイートにデータをアップロードしたり、50,000行を超えるデータセットをアップロードしたりするなど、大規模な分類データセットを柔軟にアップロードできます。

FTP 経由で分類データをダウンロードしたり、データファイルをアップロードしたりする手順（FTP アカウントを作成する手順を含む）については、[分類](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html)を参照してください。

システムでこれらのファイルをインポートするのに必要な時間は、多くの要素に応じて異なります。アップロードしたファイルが 6 時間経過しても FTP サーバー上に残っている場合は、組織のサポート対象ユーザーがアドビカスタマーケアに連絡してください。

インポートが成功すると、エクスポートには適切な変更が即時に反映されますが、Analytics のデータが変更されるには、ブラウザーによるインポートの場合は最大 4 時間、FTP によるインポートの場合は最大 24 時間かかります。

FTP の制限およびデータ保持期間については、[FTP の制限とデータ保持期間](/help/export/ftp-and-sftp/ftp-limits.md)を参照してください。

## 分類およびデータソースのアップロードの .fin ファイルについて {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. This [!DNL .fin] file is a finish file. このファイルは、データファイルが FTP アカウントに完全にアップロードされたことをシステムに通知します。The [!DNL .fin] file lets Adobe recognize that you are done with your import. このファイルが送信された後、アドビでは両方のファイルを FTP から削除し、インポートの処理を開始します。ファイルのインポート: [!DNL Classifications.tab]

ファイルの終了： [!DNL Classifications.fin]

If you upload your Data Sources or classification file without an accompanying [!DNL .fin] file, Adobe does not add it to the queue for processing. The file remains on the FTP, and is not applied to your data in the [!UICONTROL Experience Cloud]. Analytics の [!UICONTROL FTP アカウントを作成]ウィンドウで、「[!UICONTROL 通知受信者]」として電子メールアドレスを入力している場合にのみ、これについての通知が送信されます。このフィールドに電子メールアドレスを入力していない場合、通知は送信されません。

If you do upload your file with a [!DNL .fin] file, but there is an error in the file, it is submitted for processing, but the error causes the processing to cease and the file to be sent to an error folder. この場合、[!UICONTROL FTP アカウントを作成]ウィンドウで「[!UICONTROL 通知受信者]」フィールドに指定された電子メールアドレスに通知が送信されます。電子メールアドレスを入力していない場合、通知は送信されません。
