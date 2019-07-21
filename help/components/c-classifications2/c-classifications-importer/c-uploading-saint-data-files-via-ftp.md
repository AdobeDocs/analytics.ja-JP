---
description: FTP を使用してデータファイルをアップロードする方法について手順を説明します。
seo-description: FTP を使用してデータファイルをアップロードする方法について手順を説明します。
seo-title: FTPインポート
solution: Analytics
subtopic: '分類      '
title: FTPインポート
topic: 管理ツール
uuid: a914970d- ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# FTPインポート

FTP を使用してデータファイルをアップロードする方法について手順を説明します。

## FTP import {#concept_2F965BE873254546A61FB755F25299FD}

FTP を使用してデータファイルをアップロードする方法について手順を説明します。

**[!UICONTROL 管理]** 者/ **[!UICONTROL 分類インポーター]**

次の推奨限度に注意してください。

* 小さなファイルが多数あると、大きなファイルが少数ある場合よりも処理が遅くなります。これは、小さなジョブに対して必要なキューと優先順位の設定の量が原因です。
* 大きなファイルは 50 MB 以下に分割してください。これは必須ではありませんが、バックエンドでの進捗の視認性が高まるので、お勧めします。また、ジョブの処理中にエラーが発生した場合は、ジョブが再起動されますが、大きなファイルはこのシナリオで再実行する作業量が多くなります。

初回アップロードでは、少数の行の再分類や行の追加が行われるのではなく、元の大きいデータが分類データベースに入力されるか、または分類が再構成されます。

レポートスイートでの（指定の変数またはレポートに関する）最初のアップロードに続くインポートでは、新しい行と更新された行のみをアップロードすることを推奨します。変更されていない行は、その後のアップロードから除外してください。

新しいキー値をアップロードするごとに、その月の変数あたりのユニーク値の数が増加します。

その月のユニーク値が超過すると、その超過した値に対応する分類データはレポート上で表示されません。このような分類は、data warehouse または ad hoc analysis で表示できます。

>[!NOTE]
>
>分類データファイルの処理に要する時間は、ファイルのサイズと、アドビのサーバーが処理中のファイル数によって異なります。データファイルの処理にかかる時間は、通常 72 時間以内です。

FTP を使用してデータをアップロードする前に、FTP アカウントを作成します。詳しくは、 [FTP アカウントの作成](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## FTP を使用した分類のインポート {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

FTP アカウントを使用して分類を Adobe Analytics にインポートする方法について手順を説明します。

FTP アカウントの作成について詳しくは、 [FTP アカウントの作成](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. **[!UICONTROL 管理者]** / **[!UICONTROL 分類インポーター]**&#x200B;をクリックします。
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. FTP アクセス情報（ホスト、ログイン、パスワード）を使用して、選択した FTP クライアントで FTP サーバーにアクセスします。
1. Upload the data file ( [!DNL .tab] or [!DNL .txt]) to the FTP server.
1. データファイルをアップロードしたら、ファイルの処理準備が完了したことを示す FIN ファイルをアップロードします。

   The FIN file is an empty file that has the same name as your data file, with a [!DNL .fin] filename extension. For example, if your data file is [!DNL classdata1.tab], the FIN filename is [!DNL classdata1.fin].

関連する FIN ファイルを持つアップロードされたデータファイルは、定期的に、アドビによって取得されます。アドビは、FTP アカウント設定で指定されたレポートスイートとデータセットに、これらのファイルをインポートします。

## FTP アカウントの作成 {#task_C019268E6C934C7C95F4326F42A22CCF}

FTP を使用してデータをアップロードする前に、FTP アカウントを作成します。&gt;

<!-- 

t_create_an_ftp_account.xml

 -->

Adobe FTP サーバーについて詳しくは、「[FTP と SFTP（FTP and SFTP）](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/)」を参照してください。

1. **[!UICONTROL 管理者]** / **[!UICONTROL 分類インポーター]**&#x200B;をクリックします。
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. On the **[!UICONTROL Import File]** tab, click **[!UICONTROL Add New]**.
1. FTP アカウントについて次の詳細を指定します。

   | 要素 | 説明 |
   |---|---|
   | 名前 | FTP アカウント名です。 |
   | 分類するデータセット | ドロップダウンリストから、分類するデータセット（マーケティングレポート変数）を選択します。 |
   | レポートスイートを選択 | 選択したデータセットを分類するレポートスイートを選択します。複数のレポートスイートを選択するには、選択したすべてのレポートスイートで同じ分類が使用されている必要があります。 |
   | 競合を無視してデータを上書きする | 重複したデータを上書きする場合には、このオプションを選択します。このオプションは、既存の分類を更新する場合に役に立ちます。別の分類を追加する場合は、このオプションは推奨されません。 |
   | インポートの完了後 | インポートの完了後にこの FTP アカウントに関する通知を受信する電子メールアドレスを指定して、更新されたデータセットを同じ FTP アカウントに自動でエクスポートするには、このオプションを選択します。 |
   | 通知受信者 | この FTP アカウントに関する通知を受信する電子メールアドレスを指定します。 |
   | 許可する | （必須）アドビに対して、新しい FTP アカウントに送信されたすべてのデータファイルを自動的にインポートすることを許可します。 |

1. 「**[!UICONTROL 保存]**」をクリックします。

アカウントを作成したら、FTP アカウントの横にある該当するリンクをクリックして、FTP アカウントを編集または削除できます。
