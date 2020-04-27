---
description: Report Builder の「リクエストの管理」におけるフィールドの説明です。
title: リクエストの管理 - 定義
topic: Report builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# リクエストの管理 - 定義

Report Builder の「リクエストの管理」におけるフィールドの説明です。

## 概要 {#section_75C288C945FA4781A4EDF806711A5660}

The [!UICONTROL Request Manager] provides a detailed view of the status of all requests you have built for all sheets or just one sheet of the active workbook. You can also add, edit, refresh, and delete a request (functions typically associated with the [!UICONTROL Request Wizard] and [!UICONTROL Request Manager]) by right-clicking on an available cell in the Excel spreadsheet that contains previous requests.

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE]Adobe Report Builder では、同一ワークシート内でのみリクエストの依存関係を実行します。ワークシート間では実行しません。依存関係を単一のワークシート内に制限することによって、確実にタイムリーに実行します。

## 定義 {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>すべてのシート </p> </td> 
   <td colname="col2"> <p>実行中のワークブックにあるすべてのシート上のリクエストを表示します。特定のシートのリクエストを表示するには、このオプションをオフにします。このオプションをオフにする場合は、Excel の下側にある「シート」タブをクリックして、 <span class="wintitle"> Request Manager</span> で該当シートを最前面に表示しておく必要があります。このチェックボックスの隣のラベルは、現在フォーカスがあるワークブックのシート名になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>シート </p> </td> 
   <td colname="col2"> <p>ワークブック内のシート名を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートスイート </p> </td> 
   <td colname="col2"> <p>レポートスイート名を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付範囲 </p> </td> 
   <td colname="col2"> <p>レポートの日付範囲を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>精度 </p> </td> 
   <td colname="col2"> <p>リクエストの精度です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 前回の実行 </p> </td> 
   <td colname="col2"> <p>リクエストが Report Builder によって最後に処理された日付です。該当する場合は、このテーブルの「<span class="wintitle">前回の実行</span>」列内に、診断メッセージも表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>追加 </p> </td> 
   <td colname="col2"> <p>リクエストウィザードダイアログを表示します。<a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   >データリクエストの作成</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>テンプレートを </p> </td> 
   <td colname="col2"> <p> （または「複数を編集」）選択したリクエストを編集します。<span class="wintitle">リクエストウィザード</span>ダイアログを表示します。<a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   >複数のリクエストの編集</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>削除 </p> </td> 
   <td colname="col2"> <p>リクエストを削除します。選択された複数のリクエストを削除できます。リクエストを選択し、キーボードの Delete キーを押して、リスト内のリクエストを削除することもできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> すべて選択 </p> </td> 
   <td colname="col2"> <p>すべてのリクエストを選択します。<span class="wintitle">リクエストマネージャー</span>のリクエストリストの下側に、選択したリクエスト数が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>セルから取得 </p> </td> 
   <td colname="col2"> <p>ワークシートからリクエスト用のデータを取得します。現在選択されているセルとの関連付けられたリクエストが選択されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 更新 </p> </td> 
   <td colname="col2"> <p>選択した 1 つまたは複数のリクエストを更新します(<a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   >リクエストの更新</a>を参照してください。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リストを更新 </p> </td> 
   <td colname="col2"> <p>表示中のすべてのリクエストを更新します。すべてのリクエストを更新する際に、サーバーから手元のレポートに対する情報の更新にかかる時間は、レポート内のリクエストの複雑さに比例します。非常に大きなレポートでは、すべてのリクエストの更新に数分かかることがあります。このため、すぐに必要なリクエストは個別に更新し、「<span class="wintitle">すべて更新</span>」は時間があるときに実行してください。 </p> <p> <p>注意：複数のリクエストを含むワークシートを更新する場合は、<span class="wintitle">リクエストマネージャー</span>で結果を頻繁にしてください。リクエストが失敗すると、診断列にエラーメッセージが表示されるので、エラーの原因特定に役立てることができます。ほとんどの場合はリクエストの失敗時にエラーメッセージが表示されますが、エラーメッセージが表示されないこともあります。更新によって参照を含むセル内のデータが更新されなかったり、セル内のデータが削除されたりすることがあります。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

