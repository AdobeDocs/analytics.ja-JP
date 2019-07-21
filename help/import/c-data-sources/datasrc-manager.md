---
description: データソースの作成および管理を行い、レポートスイートでのデータソースの使用状況を表示します。
seo-description: データソースの作成および管理を行い、レポートスイートでのデータソースの使用状況を表示します。
seo-title: データソースマネージャー
solution: Analytics
subtopic: データソース
title: データソースマネージャー
topic: 開発者と導入
uuid: cca4a1c-7c56-421b-8ee6- a42b334659b1
translation-type: tm+mt
source-git-commit: 887f48d2ea5f21b7db95a1a8f716f7da9cf43662

---


# データソースマネージャー

データソースの作成および管理を行い、レポートスイートでのデータソースの使用状況を表示します。

**[!UICONTROL Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL データソース]**

## 「作成」タブ{#section_74603FDA3D8842E49F1A51624A06DE20}

[!UICONTROL 「作成」]タブでは、現在選択されているレポートスイートに対して新しいデータソースを設定できます。データソースをアクティブにすると、[!UICONTROL データソースウィザード]によってデータソーステンプレートを作成する処理が進められ、データをアップロードするための FTP の場所が作成されます。

「作成」タブでの選択内容により、作成されるテンプレートの初期設定のフィールドが決まります。詳しくは、 [インポートファイルテンプレートの作成](../../import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md#task_A2F150D9DC1A4D338E878534FA506267).

## 「管理」タブ{#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>オプション </p> </th> 
   <th colname="col2" class="entry"> <p>説明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>処理の再開 </p> </td> 
   <td colname="col2"> <p>エラーや警告が原因で停止していたデータソースの処理を再開します。次のエラーが発生するまで処理は続行されます。データソースは、<span class="uicontrol">「エラー時に処理を中断する」</span>が選択された場合にのみ、データソースファイルの処理を停止します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>処理の完了 </p> </td> 
   <td colname="col2"> <p>データソースファイル内で開いている訪問をすべて閉じるよう指示し、データソースファイルの処理が完了したかのように処理を終了します。複数のデータソースファイルにまたがる訪問がある場合に便利です。これは <a href="../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> フル処理</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>非アクティブ化 </p> </td> 
   <td colname="col2"> <p> 非アクティブ化したデータソースは削除されます。サーバー上で処理を開始しているファイルがある場合、その処理は完了するまで続行されます。処理が開始されていないファイルの処理は行われません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>エラー時に処理を中断する／警告時に処理を中断する </p> </td> 
   <td colname="col2"> <p> エラーの発生時に処理を停止するよう、データソース処理エンジンに指示します。「処理の再開」を選択するまで、データソースの処理は再開しません。警告時に処理を中断するオプションは、 <a href="../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> フル処理</a>. </p> <p>ファイルエラーが検出されると、データソースによってエラーが通知されます。エラーのあるデータソースファイルは、FTP サーバー上の <span class="filepath">files_with_errors</span> というフォルダーに移動されます。問題を解決した後、処理を実行するためにデータソースファイルを再送信してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>設定 </p> </td> 
   <td colname="col2"> <p>データソーステンプレートなど、このデータソースに固有の設定を変更できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FTP 情報 </p> </td> 
   <td colname="col2"> <p>このデータソースの FTP 情報を表示します。この情報を使用してデータソーステンプレートにアクセスし、データソースのデータを送信します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ファイル名 </p> </td> 
   <td colname="col2"> <p>アップロードされたファイルの名前 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ステータス </p> </td> 
   <td colname="col2"> <p> ファイルの現在のステータス。可能なステータス値は次のとおりです。 </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">待機中（手順 1／3）：ファイルは存在しますが、処理が開始されていません。ファイルが 30 分以内に表示されない場合は、関連する <span class="filepath">.fin</span> ファイルが存在することを確認してください。 </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">準備（手順 2／3）：ファイルはエラーや警告の確認中です。 </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">処理（手順 3／3）：ファイルは処理中です。 </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">失敗：エラーにより、ファイルは処理されませんでした。 </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">成功：ファイルは処理が完了しました。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 「ファイルログ」タブ {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

ファイルログには検索機能があり、データソース名、データソースタイプ、ファイル名、受信日、ステータスによって情報を検索できます。
