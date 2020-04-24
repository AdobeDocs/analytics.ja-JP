---
description: 分類（SAINT）FTP オプションは、複数のレポートスイートへのデータアップロード機能や、50,000 行を超えるデータセットのアップロード機能など、大規模な分類データセットを柔軟にアップロードできる機能を備えています。
keywords: ftp;sftp
title: 分類
uuid: 35936c98-b785-43eb-89f4-ab42a10db256
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 分類

分類 FTP オプションは、複数のレポートスイートへのデータアップロード機能や、50,000 行を超えるデータセットのアップロード機能など、大規模な分類データセットを柔軟にアップロードできる機能を備えています。

FTP 経由で分類データをダウンロードしたり、データファイルをアップロードしたりする手順（FTP アカウントを作成する手順を含む）については、[分類](https://marketing.adobe.com/resources/help/ja_JP/reference/c_working_with_saint.html)を参照してください。

システムでこれらのファイルを読み込むのに必要な時間は、多くの要素に応じて異なります。アップロードしたファイルが 6 時間経過しても FTP サーバー上に残っている場合は、組織のサポート対象ユーザーがアドビカスタマーケアに連絡してください。

インポートが成功すると、エクスポートには適切な変更が即時に反映されますが、Analytics のデータが変更されるには、ブラウザーによるインポートの場合は最大 4 時間、FTP によるインポートの場合は最大 24 時間かかります。

FTP の制限およびデータ保持期間については、[FTP の制限とデータ保持期間](/help/export/ftp-and-sftp/ftp-limits.md)を参照してください。

## 分類およびデータソースのアップロードの .fin ファイルについて {#section_1484719F8A134EAE91212DBD8F15174F}

When you upload a classification or [!UICONTROL Data Source] file ( [!DNL .tab]or [!DNL .txt]) the upload also requires that you upload an empty file with the exact same name as the data file being imported, but with a [!DNL .fin] extension. この [!DNL .fin] ファイルは、完了通知ファイルです。このファイルは、データファイルが FTP アカウントに完全にアップロードされたことをシステムに通知します。[!DNL .fin] ファイルがアップロードされることで、お客様が読み込みデータのアップロードを完了したことをアドビで認識できます。このファイルが送信された後、アドビでは両方のファイルを FTP から削除し、読み込みの処理を開始します。ファイルの読み込み：[!DNL Classifications.tab]

ファイルの終了：[!DNL Classifications.fin]

データソースまたは分類ファイルをアップロードしても、[!DNL .fin] ファイルをアップロードしないと、処理用のキューに追加されません。ファイルは FTP に残ったままになり、[!UICONTROL Experience Cloud] のデータに適用されません。You are notified of this only if you have entered your email address as the [!UICONTROL Notification Recipient] in the [!UICONTROL Create FTP Account] window of Analytics. このフィールドに電子メールアドレスを入力していない場合、通知は送信されません。

ファイルをアップロードし、[!DNL .fin] ファイルをアップロードしたが、ファイルにエラーがある場合、ファイルは処理のために送信されますが、エラーによって処理が中止され、ファイルはエラーフォルダーに送信されます。If this occurs, a notification is sent to the email address listed in the [!UICONTROL Notification Recipient] field in the [!UICONTROL Create FTP Account] window. 電子メールアドレスを入力していない場合、通知は送信されません。
