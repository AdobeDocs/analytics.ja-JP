---
description: FTP を使用してデータファイルをアップロードする方法。
title: FTP インポート
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
source-git-commit: 5edf3e6684b3572616f76db3f7c3bf0cf58ed408
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# FTP インポート

FTP を使用してデータファイルをアップロードする方法について手順を説明します。

## FTP インポート {#concept_2F965BE873254546A61FB755F25299FD}

FTP を使用してデータファイルをアップロードする方法について手順を説明します。

**[!UICONTROL 管理者]**／**[!UICONTROL 分類インポーター]**

次の推奨限度に注意してください。

* 小さなファイルが多数あると、大きなファイルが少数ある場合よりも処理が遅くなります。これは、小さなジョブに対して必要なキューと優先順位の設定の量が原因です。
* 大きなファイルは 50 MB 以下に分割してください。これは必須ではありませんが、バックエンドでの進捗の視認性が高まるので、お勧めします。また、ジョブの処理中にエラーが発生した場合は、ジョブが再起動されますが、大きなファイルはこのシナリオで再実行する作業量が多くなります。

初回アップロードでは、少数の行の再分類や行の追加が行われるのではなく、元の大きいデータが分類データベースに入力されるか、または分類が再構成されます。

レポートスイートでの（指定の変数またはレポートに関する）最初のアップロードに続くインポートでは、新しい行と更新された行のみをアップロードすることを推奨します。変更されていない行は、その後のアップロードから除外してください。

新しいキー値をアップロードするごとに、その月の変数あたりのユニーク値の数が増加します。

その月のユニーク値が超過すると、その超過した値に対応する分類データはレポート上で表示されません。これらの分類は、Data Warehouse で表示できます。

>[!NOTE]
>
>分類データファイルの処理にかかる時間は、ファイルサイズと、アドビのサーバーで処理中のファイルの数によって異なります。データファイルの処理にかかる時間は、通常 72 時間以内です。

FTP を使用してデータをアップロードする前に、FTP アカウントを作成します。詳しくは、[FTP アカウントの作成](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)を参照してください。

## FTP を使用した分類のインポート {#task_132C36830B69418B8C929E39838EF01D}

FTP アカウントを使用して分類を Adobe Analytics にインポートする方法について手順を説明します。

FTP アカウントの作成について詳しくは、[FTP アカウントの作成](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)を参照してください。

1. **[!UICONTROL 管理者]**／**[!UICONTROL 分類インポーター]**&#x200B;をクリックします。
1. 「**[!UICONTROL ファイルのインポート]**」をクリックしてから「**[!UICONTROL FTP インポート]**」をクリックします。
1. 使用する FTP アカウントの横の「**[!UICONTROL 表示]**」をクリックします。
1. FTP アクセス情報（ホスト、ログイン、パスワード）を使用して、選択した FTP クライアントで FTP サーバーにアクセスします。
1. データファイル（[!DNL .tab] または [!DNL .txt]）を FTP サーバーにアップロードします。
1. データファイルをアップロードしたら、ファイルの処理準備が完了したことを示す FIN ファイルをアップロードします。

   この FIN ファイルは、使用するデータファイルと同じ名前を持つ空のファイルで、ファイル名の拡張子は [!DNL .fin] です。例えば、使用するデータファイルが [!DNL classdata1.tab] の場合、FIN ファイル名は [!DNL classdata1.fin] です。

関連する FIN ファイルを持つアップロードされたデータファイルは、定期的に、アドビによって取得されます。アドビは、FTP アカウント設定で指定されたレポートスイートとデータセットに、これらのファイルをインポートします。

Adobe Analyticsが FTP フォルダーにアップロードされたファイルを読み取り、処理すると、そのファイルは自動的に削除されます。

## FTP アカウントの作成 {#task_C019268E6C934C7C95F4326F42A22CCF}

FTP を使用してデータをアップロードする前に、FTP アカウントを作成します。>

Adobe FTP サーバーについて詳しくは、「[FTP と SFTP](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html?lang=ja)」を参照してください。

1. **[!UICONTROL 管理者]**／**[!UICONTROL 分類インポーター]**&#x200B;をクリックします。
1. 「**[!UICONTROL ファイルのインポート]**」をクリックしてから「**[!UICONTROL FTP インポート]**」をクリックします。
1. 「**[!UICONTROL ファイルのインポート]**」タブで、「**[!UICONTROL 新規追加]**」をクリックします。
1. FTP アカウントについて次の詳細を指定します。

   | 要素 | 説明 |
   |---|---|
   | 名前 | FTP アカウント名です。 |
   | 分類するデータセット | ドロップダウンリストから、分類するデータセット（マーケティングレポート変数）を選択します。 |
   | レポートスイートの選択 | 選択したデータセットを分類するレポートスイートを選択します。複数のレポートスイートを選択するには、選択したすべてのレポートスイートで同じ分類が使用されている必要があります。 |
   | 競合を無視してデータを上書きする | 重複したデータを上書きする場合には、このオプションを選択します。このオプションは、既存の分類を更新する場合に役に立ちます。別の分類を追加する場合は、このオプションは推奨されません。 |
   | インポートの完了後 | インポートの完了後にこの FTP アカウントに関する通知を受信する電子メールアドレスを指定して、更新されたデータセットを同じ FTP アカウントに自動でエクスポートするには、このオプションを選択します。 |
   | 通知受信者 | この FTP アカウントに関する通知を受信する電子メールアドレスを指定します。 |
   | 許可する | （必須）アドビに対して、新しい FTP アカウントに送信されたすべてのデータファイルを自動的にインポートすることを許可します。 |

1. 「**[!UICONTROL 保存]**」をクリックします。

アカウントを作成したら、FTP アカウントの横にある該当するリンクをクリックして、FTP アカウントを編集または削除できます。

>[!NOTE]
>
>読み込みによって分類が変更されない場合、通知は送信されません。電子メールは、正常に実行され、その結果分類が変更された場合にのみ送信されます。
