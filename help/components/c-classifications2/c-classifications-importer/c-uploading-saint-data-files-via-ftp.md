---
description: FTP を使用してデータファイルをアップロードする方法について手順を説明します。
subtopic: Classifications
title: FTP インポート
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# FTP インポート

FTP を使用してデータファイルをアップロードする方法について手順を説明します。

## FTP インポート {#concept_2F965BE873254546A61FB755F25299FD}

FTP を使用してデータファイルをアップロードする方法について手順を説明します。

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

次の推奨制限が重要です。

* 小さなファイルが多いと、大きなファイルが少ない場合よりも処理が遅くなります。 これは、より小さなジョブに必要なキューと優先順位の設定の量が原因です。
* 大きなファイルを50 MBのチャンクに分割してください。 これは必須ではありませんが、バックエンドでの進行状況をより明確に把握できるので、お勧めします。 また、ジョブの処理中にエラーが発生した場合は、ジョブが再開されます。大きなファイルの場合、このシナリオでは大量の作業が再実行されます。

初期設定では、少数の行の再分類や行の追加を行わずに、元の大きなデータのセットが分類データベースに入力されるか、分類が再構成されます。

（特定の変数またはレポートに対する）レポートスイートでの最初のアップロードの後に行をアップロードする場合は、新しい行と更新した行のみをアップロードすることをお勧めします。 変更されていない行は、今後のアップロードから除外する必要があります。

新しいキー値をアップロードするたびに、その月のその変数の個別の数に対してカウントされます。

その月の個別の数が超過した場合、超過した値に対応する分類データはレポートに表示されません。 これらの分類は、Data WarehouseまたはAd Hoc分析で表示できます。

>[!NOTE]分類データファイルの処理にかかる時間は、ファイルサイズと、アドビのサーバーで処理中のファイルの数によって異なります。データファイルの処理には通常72時間以内かかります。

FTP を使用してデータをアップロードする前に、FTP アカウントを作成します。詳しくは、[FTP アカウントの作成](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)を参照してください。

## FTP を使用した分類のインポート {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

FTPアカウントを使用して分類をAdobe Analyticsにインポートする手順を説明します。

FTPアカウントの作成について詳しくは、「FTPアカウントの作成」 [を参照してください](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

1. クリック **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. をクリック **[!UICONTROL Import File]**&#x200B;し、をクリックしま **[!UICONTROL FTP Import]**&#x200B;す。
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. FTP アクセス情報（ホスト、ログイン、パスワード）を使用して、選択した FTP クライアントで FTP サーバーにアクセスします。
1. データファイル（[!DNL .tab] または [!DNL .txt]）を FTP サーバーにアップロードします。
1. データファイルをアップロードしたら、ファイルの処理準備が完了したことを示す FIN ファイルをアップロードします。

   この ファイルは、使用するデータファイルと同じ名前を持つ空のファイルで、ファイル名の拡張子は [!DNL .fin] です。例えば、使用するデータファイルが [!DNL classdata1.tab] の場合、 ファイルの名前は [!DNL classdata1.fin].fin です。

関連するFINファイルを持つアップロードされたデータファイルは、一定の間隔でアドビが取得します。 アドビは、FTPアカウント設定で指定されたレポートスイートおよびデータセットに読み込みます。

## FTP アカウントの作成 {#task_C019268E6C934C7C95F4326F42A22CCF}

FTP を使用してデータをアップロードする前に、FTP アカウントを作成します。>

<!-- 

t_create_an_ftp_account.xml

 -->

Adobe FTP サーバーについて詳しくは、「[FTP と SFTP（FTP and SFTP）](https://marketing.adobe.com/resources/help/ja_JP/whitepapers/ftp/)」を参照してください。

1. クリック **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. をクリック **[!UICONTROL Import File]**&#x200B;し、をクリックしま **[!UICONTROL FTP Import]**&#x200B;す。
1. タブで、をク **[!UICONTROL Import File]** リックしま **[!UICONTROL Add New]**&#x200B;す。
1. FTP アカウントについて次の詳細を指定します。

   | 要素 | 説明 |
   |---|---|
   | 名前 | FTPアカウント名。 |
   | 分類するデータセット | ドロップダウンリストから、分類するデータセット（マーケティングレポート変数）を選択します。 |
   | レポートスイートの選択 | 選択したデータセットを分類するレポートスイートを選択します。 複数のレポートスイートを選択するには、選択した各レポートスイートの分類が同じである必要があります。 |
   | 競合時にデータを上書き | このオプションを選択すると、重複データが上書きされます。 このオプションは、既存の分類を更新する場合に役立ちます。 分類を追加する場合は、このオプションは推奨されません。 |
   | インポートの完了後 | インポートの完了後にこのFTPアカウントに関する通知を受信する電子メールアドレスを指定し、同じFTPアカウントに更新されたデータセットを自動的にエクスポートするには、このオプションを選択します。 |
   | 通知受信者 | このFTPアカウントに関する通知を受信する電子メールアドレスを指定します。 |
   | 許可 | （必須）アドビに対し、新しいFTPアカウントに送信されたすべてのデータファイルを自動的にインポートすることを許可します。 |

1. クリック **[!UICONTROL Save]**.

アカウントを作成したら、FTP アカウントの横にある該当するリンクをクリックして、FTP アカウントを編集または削除できます。
