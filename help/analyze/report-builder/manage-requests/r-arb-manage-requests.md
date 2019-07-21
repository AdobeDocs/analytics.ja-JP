---
description: Report Builder の「リクエストを管理」におけるフィールドの説明です。
seo-description: Report Builder の「リクエストを管理」におけるフィールドの説明です。
seo-title: リクエストの管理-定義
solution: Analytics
title: リクエストの管理-定義
topic: Report Builder
uuid: 01b21d0e- c870-4df8-95b9- f4aef1f4d16b
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# リクエストの管理-定義

Report Builder の「リクエストを管理」におけるフィールドの説明です。

## 概要 {#section_75C288C945FA4781A4EDF806711A5660}

[!UICONTROL リクエストマネージャー]は、実行中のワークブックのすべてのシートで作成された、すべてのリクエストの状況について詳細を表示します。また、リクエストが設定されたセルを右クリックして、リクエストの追加、編集、更新および削除（[!UICONTROL リクエストウィザード]および[!UICONTROL リクエストマネージャー]に関連付けられた一般的な機能）を実行することもできます。

[!UICONTROL リクエストマネージャー] は、Report Builderツールバーの **[!UICONTROL 「管理」]**![](assets/edit_request.gif) をクリックすると表示されます。

>[!NOTE]
>
>Adobe Report Builderでは、同じワークシート内でのみリクエストの依存関係が実行されます。ワークシート間では実行されません。依存関係を単一のワークシート内に制限することによって、確実にタイムリーに実行します。

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
   <td colname="col2"> <p>実行中のワークブックにあるすべてのシート上のリクエストを表示します。特定のシートのリクエストを表示するには、このオプションをオフにします。このオプションをオフにする場合は、Excel の下側にある「シート」タブをクリックして、該当シートを最前面に表示しておく<span class="wintitle"></span>必要があります。このチェックボックスの隣のラベルは、現在フォーカスがあるワークブックのシート名になります。 </p> </td> 
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
   <td colname="col1"> <p>期間 </p> </td> 
   <td colname="col2"> <p>レポートの日付範囲を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>精度 </p> </td> 
   <td colname="col2"> <p>リクエストの精度です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 前回の実行 </p> </td> 
   <td colname="col2"> <p>リクエストが Report Builder によって最後に処理された日付です。該当する場合は、<span class="wintitle"></span>ここに、診断メッセージも表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>追加 </p> </td> 
   <td colname="col2"> <p>リクエストウィザードダイアログを表示します。詳しくは、<a href="../../../analyze/report-builder/data-requests/t-create-a-data-request.md#task_65B453C8F015429A8EA73A1B64025B6C" type="task" format="dita" scope="local">データリクエストの作成</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>編集 </p> </td> 
   <td colname="col2"> <p> （または「複数を編集」）選択したリクエストを編集します。<span class="wintitle">リクエストウィザード</span>ダイアログを表示します。See <a href="../../../analyze/report-builder/manage-requests/t-edit-multiple-requests.md#task_70A13DBE43CD4BBEBE1B62459ADB3AD1" type="task" format="dita" scope="local"> Edit Multiple Requests</a>. </p> </td> 
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
   <td colname="col2"> <p>ワークシートからリクエストのデータを取得します。現在選択されているセルとの関連付けられたリクエストが選択されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 更新 </p> </td> 
   <td colname="col2"> <p>選択した 1 つまたは複数のリクエストを更新します（ <a href="../../../analyze/report-builder/manage-requests/t-refresh-a-request.md#task_96556DB051A2479A955999D3837EE609" type="task" format="dita" scope="local"> リクエストの更新</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リストを更新 </p> </td> 
   <td colname="col2"> <p>表示中のすべてのリクエストを更新します。すべてのリクエストを更新する際に、サーバーから手元のレポートに対する情報の更新にかかる時間は、レポート内のリクエストの複雑さに比例します。非常に大きなレポートでは、すべてのリクエストの更新に数分かかることがあります。このため、すぐに必要なリクエストは個別に更新し、「<span class="wintitle">すべて更新</span>」は時間があるときに実行してください。 </p> <p> <p>注意：複数のリクエストを含むワークシートを更新する場合は、<span class="wintitle">リクエストマネージャー</span>で結果を頻繁にしてください。リクエストが失敗すると、診断列にエラーメッセージが表示されるので、エラーの原因特定に役立てることができます。ほとんどの場合はリクエストの失敗時にエラーメッセージが表示されますが、エラーメッセージが表示されないこともあります。更新によって参照を含むセル内のデータが更新されなかったり、セル内のデータが削除されたりすることがあります。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

