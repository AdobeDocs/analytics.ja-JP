---
title: データソースの管理
description: データソース管理インターフェイスに移動します。
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 2%

---

# データソースの管理

データソースマネージャーを使用して、データソースの作成、編集、非アクティブ化をおこないます。 また、このインターフェイスを使用して、データソースの FTP の場所にアップロードされたファイルのステータスを追跡することもできます。

**[!UICONTROL 管理者]** > **[!UICONTROL すべての管理者]** > **[!UICONTROL データソース]**

右上のレポートスイートセレクターを使用して、組織内のレポートスイートを切り替えます。

このインターフェイスには主に 3 つのタブがあります。 **[!UICONTROL 管理]**, **[!UICONTROL 作成]**、および **[!UICONTROL ファイルログ]**.

## 管理

この **[!UICONTROL 管理]** 「 」タブでは、組織で作成したすべてのデータソースが処理されます。 FTP 情報の表示、テンプレートファイルで使用される変数の編集、データソースの完全な非アクティブ化をおこなうことができます。

![管理](assets/manage.png)

最上位のデータソースは常に [!UICONTROL Web ビーコン]. このデータソースは、AppMeasurement を使用した一般的なデータ収集で使用するデータソースです。 編集や非アクティブ化はできません。

各データソースには次のオプションがあります。

* **[!UICONTROL 処理の再開]**:エラーが原因で以前に停止したデータソース処理を再開します。 次のエラーが発生するまで処理は続行されます。データソースは、「 **[!UICONTROL エラー時に処理を停止]**.
* **[!UICONTROL 処理の完了]**:現在は使用されていません — このボタンは [フル処理データソース](full-processing-eol.md).
* **[!UICONTROL エラー時に処理を停止]**:エラーが発生した場合に処理サーバーを停止するように指示するチェックボックスです。 選択するまで、データソースの処理は再開されません。 **[!UICONTROL 処理の再開]**. ファイルエラーが検出されると、データソースによってエラーが通知されます。 Adobeーにより、エラーのあるファイルが、 `files_with_errors` を FTP サーバーに設定します。 問題を解決したら、処理用にファイルを再送信します。
* **[!UICONTROL 設定]**:このデータソースのデータソース作成ウィザードの手順を示すリンク。 このウィザードでは、データソースの名前を変更したり、テンプレートファイルのダウンロード時に自動的に含まれる変数を再設定したりできます。
* **[!UICONTROL FTP 情報]**:データソース作成ウィザードの最後の手順に移動するリンク。FTP 資格情報が表示されます。

データソースがデータを受け取ると、アップロードされたファイルの複数の列を含むテーブルが表示されます。

* **[!UICONTROL 処理中のキュー内のファイル]**:ファイルの名前。
* **[!UICONTROL 行]**:ファイル内の合計行数。
* **[!UICONTROL エラー]**:エラーを含み、取り込めなかった行の数。
* **[!UICONTROL 警告]**:警告を含んだ行の数。
* **[!UICONTROL 受信済み]**:レポートスイートのタイムゾーンでファイルが受け取ったタイムスタンプ。
* **[!UICONTROL ステータス]**:ファイルのステータス (`Success` または `Failed`) をクリックします。

## 作成

この **[!UICONTROL 作成]** 「 」タブには、データソース作成ウィザードの開始点が表示されます。

![作成](assets/create.png)

データソースのカテゴリとタイプは、以前のバージョンのAdobe Analyticsではより役に立ちました。 ただし、まだ使用が制限されています。

* データソースのタイプは、 [管理](#manage) タブにデータソース自体を表示し、 [ファイルログ](#file-log) 」タブを使用します。
* 一部のデータソースタイプでは、テンプレートファイルのダウンロード時に変数が自動的に含まれます。 ただし、設定された [ファイル形式](file-format.md).

これらの理由を除き、選択できるデータソースのカテゴリとタイプはすべて同じです。 データソースの使用目的に最適なカテゴリとタイプを選択します。

の引退に伴って [フル処理データソース](full-processing-eol.md)、複数のカテゴリおよびタイプを選択することはできません。 フル処理データソースタイプを選択した場合、 **[!UICONTROL 有効化]** ボタンがグレー表示される。

## ファイルログ

この **[!UICONTROL ファイルログ]** 「 」タブには、特定のレポートスイート用にアップロードされたすべてのデータソースファイルの集計ビューが表示されます。

![ファイルログ](assets/file-log.png)

特定のデータソースを見つけるのに役立つ検索バーが使用できます。 この表は、次の列を示しています。

* **[!UICONTROL データソース名]**:データソースの名前。
* **[!UICONTROL タイプ]**:データソースのタイプ。
* **[!UICONTROL ファイル名]**:アップロードされたファイルの名前。
* **[!UICONTROL 行]**:ファイル内の合計行数。
* **[!UICONTROL エラー]**:エラーを含む行の数。
* **[!UICONTROL 警告]**:廃止。 警告を含んだ行の数。
* **[!UICONTROL 受信済み]**:Adobeがファイルの処理を開始した日時。
* **[!UICONTROL ステータス]**:ファイルのステータス (`Success` または `Failed`) をクリックします。