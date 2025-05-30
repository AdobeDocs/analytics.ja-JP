---
title: データソースの管理
description: データソース管理インターフェイスに移動します。
exl-id: 315501fb-26e1-436a-938d-5957ca037cd0
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 7%

---

# データソースの管理

データソースマネージャーを使用して、データソースの作成、編集、非アクティブ化を行います。また、このインターフェイスを使用して、データソースの FTP の場所にアップロードされたファイルのステータスを追跡することもできます。

**[!UICONTROL 管理者]**/**[!UICONTROL すべての管理者]**/**[!UICONTROL データソース]**

右上のレポートスイートセレクターを使用して、組織内のレポートスイートを切り替えます。

このインターフェイスには、**[!UICONTROL 管理]**、**[!UICONTROL 作成]**、**[!UICONTROL ファイルログ]** の 3 つのメインタブがあります。

## 管理

**[!UICONTROL 管理]** タブは、組織が作成したすべてのデータソースを処理します。 FTP 情報を表示したり、テンプレートファイルで使用されている変数を編集したり、データソースを完全に非アクティブ化したりできます。

![管理](assets/manage.png)

最上位のデータソースは常に [!UICONTROL Web ビーコン &#x200B;] です。 このデータソースは、AppMeasurementを介した一般的なデータ収集に使用します。 編集または非アクティブ化はできません。

各データソースには次のオプションがあります。

* **[!UICONTROL 処理を再開]**: エラーが原因で以前に停止したデータソース処理を再開します。 次のエラーが発生するまで処理は続行されます。データソースは、「**[!UICONTROL エラーの処理を停止]**」を選択した場合にのみ、データソースファイルの処理を停止します。
* **[!UICONTROL 処理を完了]**：使用しなくなりました – このボタンは、[ フル処理データソース ](full-processing-eol.md) にのみ使用されました。
* **[!UICONTROL エラーの処理を停止]**: エラーが発生した場合に処理サーバーを停止するように指示するチェックボックス。 データソースは、「処理を再開 **[!UICONTROL を選択するまで処理を再開しません]**。 データソースでファイルエラーが発生すると、そのエラーを通知します。 Adobeが、エラーを含むファイルを FTP サーバー上の `files_with_errors` というフォルダーに移動します。 問題を解決したら、ファイルを再送信して処理します。
* **[!UICONTROL 設定]**：このデータソースに関するデータソース作成ウィザードに移動するリンク。 このウィザードを使用すると、データ ソースの名前を変更したり、テンプレート ファイルをダウンロードするときに自動的に含まれる変数を再構成したりできます。
* **[!UICONTROL FTP 情報]**:FTP 資格情報が表示される、データソース作成ウィザードの最後の手順に移動するリンクです。

データソースがデータを受信すると、アップロードされたファイルに対する複数の列を含んだテーブルが表示されます。

* **[!UICONTROL Files In Processing Queue]**：ファイルの名前。
* **[!UICONTROL 行]**: ファイルの行の合計数。
* **[!UICONTROL エラー]**：エラーが含まれ、取り込むことができなかった行の数。
* **[!UICONTROL 警告]**：警告を含んだ行数。
* **[!UICONTROL 受信済み]**：レポートスイートのタイムゾーンでファイルが受信されたタイムスタンプ。
* **[!UICONTROL ステータス]**：ファイルのステータス（`Success` または `Failed`）。

## 作成

**[!UICONTROL 作成]** タブでは、データソース作成ウィザードを開始できます。

![ 作成 ](assets/create.png)

データソースのカテゴリとタイプは、以前のバージョンのAdobe Analyticsでより価値がありました。 ただし、次のような制限された使用方法はあります。

* データソースのタイプは、データソース自体の場合は「[ 管理 ](#manage)」タブに表示され、個々のファイルの場合は「[ ファイルログ ](#file-log)」タブに表示されます。
* 一部のデータソースタイプは、テンプレートファイルのダウンロード時に自動的に変数を含めます。 ただし、確立された [ ファイル形式 ](file-format.md) に準拠している限り、使用可能な任意のディメンションまたは指標を含めることができます。

これらの理由に加えて、選択できるすべてのデータソースカテゴリとデータソースタイプは、実質的に同じです。 データソースを使用する目的を最もよく表すカテゴリとタイプを選択します。

[ フル処理データソース ](full-processing-eol.md) の廃止により、複数のカテゴリおよびタイプを選択できなくなります。 フル処理データソースのタイプを選択した場合、「**[!UICONTROL アクティベート]**」ボタンは灰色表示になります。

## ファイル ログ

「**[!UICONTROL ファイルログ]**」タブには、特定のレポートスイート用にアップロードされたすべてのデータソースファイルの集計表示が表示されます。

![ ファイル ログ ](assets/file-log.png)

特定のデータソースを見つけるのに役立つ検索バーを使用できます。 このテーブルには、次の列が表示されます。

* **[!UICONTROL Data Source名]**：データソースの名前です。
* **[!UICONTROL タイプ]**：データソースのタイプ。
* **[!UICONTROL ファイル名]**：アップロードされたファイルの名前。
* **[!UICONTROL 行]**: ファイルの行の合計数。
* **[!UICONTROL エラー]**：エラーを含んだ行数。
* **[!UICONTROL 警告]**：使用されなくなりました。 警告を含んだ行の数。
* **[!UICONTROL 受信済み]**: Adobeがファイルの処理を開始した日時。
* **[!UICONTROL ステータス]**：ファイルのステータス（`Success` または `Failed`）。
