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

には、 [!UICONTROL Request Manager] すべてのシートまたはアクティブなワークブックの1つのシートに対して作成したすべてのリクエストのステータスの詳細な表示が表示されます。 また、以前のリクエストを含むExcelスプレッドシートの使用可能なセルを右クリックして、リクエスト(通常はANDに関連付けられる [!UICONTROL Request Wizard][!UICONTROL Request Manager]関数)を追加、編集、更新および削除できます。

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
   <td colname="col2"> <p>作業中のワークブックのすべてのシートからのリクエストを表示します。 特定のシートから表示リクエストを送信する場合は、このオプションをオフにします。 このオプションをオフにする場合は、Excel の下側にある「シート」タブをクリックして、 <span class="wintitle"> Request Manager</span> で該当シートを最前面に表示しておく必要があります。チェックボックスの横のラベルは、現在フォーカスがあるワークブックのシートを示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>シート </p> </td> 
   <td colname="col2"> <p>ワークブック内のシートの名前を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートスイート </p> </td> 
   <td colname="col2"> <p>レポートスイートの名前を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付範囲 </p> </td> 
   <td colname="col2"> <p>レポートの指定した日付範囲を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>精度 </p> </td> 
   <td colname="col2"> <p>リクエストの精度を指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 前回の実行 </p> </td> 
   <td colname="col2"> <p>リクエストがReport Builderで最後に処理された日付を指定します。 該当する場合は、このテーブルの「<span class="wintitle">前回の実行</span>」列内に、診断メッセージも表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>追加 </p> </td> 
   <td colname="col2"> <p>リクエストウィザードダイアログを表示します。 <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   >データリクエストの作成</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>テンプレートを </p> </td> 
   <td colname="col2"> <p> （または複数を編集）選択したリクエストを編集します。 <span class="wintitle">リクエストウィザード</span>ダイアログを表示します。<a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   >複数のリクエストの編集</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>削除 </p> </td> 
   <td colname="col2"> <p>リクエストを削除します。 選択した複数のリクエストを削除できます。 リクエストを選択し、リストのDeleteキーを押して、リクエストを削除することもできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> すべて選択 </p> </td> 
   <td colname="col2"> <p>すべてのリクエストを選択します。 <span class="wintitle">リクエストマネージャー</span>のリクエストリストの下側に、選択したリクエスト数が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>セルから </p> </td> 
   <td colname="col2"> <p>ワークシートからリクエスト用のデータを取得します。アクティブなワークシートで現在選択されているセルにリクエストが関連付けられている場合は、リスト内の関連リクエストが選択されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 更新 </p> </td> 
   <td colname="col2"> <p>1つのリクエストまたは選択したリクエストを更新します。 (See <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Refresh a Request</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新リスト </p> </td> 
   <td colname="col2"> <p>表示されているすべてのリクエストを更新します。 すべてのリクエストを更新すると、サーバーからレポートに情報を更新する時間は、レポート内のリクエストの複雑さに比例します。 非常に大きなレポートの場合、すべてのリクエストの更新に数分かかる場合があります。 このため、すぐに必要なリクエストは個別に更新し、「<span class="wintitle">すべて更新</span>」は時間があるときに実行してください。 </p> <p> <p>注意：複数のリクエストを含むワークシートを更新する場合は、<span class="wintitle">リクエストマネージャー</span>で結果を頻繁にしてください。リクエストの失敗が発生した場合は、診断列のエラーメッセージを参考にして、エラーの原因を特定できます。 ほとんどの場合、リクエストが失敗したときにエラーメッセージが表示されますが、エラーメッセージが生成されないことがあります。 参照を含むセル内のデータは更新されない場合や、セルからデータが削除される場合があります。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

