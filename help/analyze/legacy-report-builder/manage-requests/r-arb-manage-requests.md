---
description: Report Builderでのリクエストの管理のフィールドの説明について説明します。
title: Report Builderでのリクエストの管理方法
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: User, Admin
exl-id: fd8c0145-4c7e-4f07-aa63-656a8a20724c
TQID: https://experienceleague.adobe.com/ZAVAW4NN9WCHCdj-ZPXDOflV4oC0-WPbClzkdlrf3JM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 563
ht-degree: 26%

---

# リクエストの管理 - 定義

{{legacy-arb}}

リクエストステータスの詳細を表示し、フィールドの説明を使用してReport Builderでリクエストを管理します。

## 概要 {#section_75C288C945FA4781A4EDF806711A5660}

[!UICONTROL &#x200B; リクエストマネージャー]には、すべてのシートまたはアクティブなワークブックの1枚のシートに対して作成したすべてのリクエストのステータスの詳細が表示されます。 また、リクエストを追加、編集、更新、削除することもできます。 これらの関数は、通常、以前のリクエストを含むExcel スプレッドシートで使用可能なセルを右クリックすると、[!UICONTROL &#x200B; リクエストウィザード &#x200B;]および[!UICONTROL &#x200B; リクエストマネージャー]に関連付けられます。

Report Builder ツールバーの&#x200B;**[!UICONTROL 管理]** ![](assets/edit_request.gif)をクリックすると、[!UICONTROL Request Manager]が表示されます。

>[!NOTE]
>
>Adobe Report Builderでは、リクエストの依存関係は、ワークシート間ではなく、同じワークシート内でのみ適用されます。 単一のワークシート内の依存関係に制限することで、実行のタイムリー性が確保されます。

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
   <td colname="col2"> <p>アクティブなワークブックのすべてのシートからのリクエストを表示します。 特定のシートからリクエストを表示するには、このオプションをオフにします。 このオプションをオフにする場合は、Excel の下側にある「シート」タブをクリックして、 <span class="wintitle"> Request Manager</span> で該当シートを最前面に表示しておく必要があります。 チェックボックスの横にあるラベルは、現在ワークブックのどのシートにフォーカスがあるかを示します。 </p> </td> 
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
   <td colname="col2"> <p>レポートの指定された日付範囲を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>精度 </p> </td> 
   <td colname="col2"> <p>リクエストの精度を指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 前回の実行 </p> </td> 
   <td colname="col2"> <p>リクエストがReport Builderによって最後に処理された日付を指定します。 該当する場合は、このテーブルの「<span class="wintitle">前回の実行</span>」列内に、診断メッセージも表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>追加 </p> </td> 
   <td colname="col2"> <p>リクエストウィザード ダイアログを表示します。 「<a href="/help/analyze/legacy-report-builder/data-requests/t-create-a-data-request.md"   > データ要求の作成</a>」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>編集 </p> </td> 
   <td colname="col2"> <p> （または複数を編集）選択したリクエストを編集します。 <span class="wintitle">リクエストウィザード</span>ダイアログを表示します。 <a href="/help/analyze/legacy-report-builder/manage-requests/t-edit-multiple-requests.md"   >複数のリクエストの編集</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>削除 </p> </td> 
   <td colname="col2"> <p>リクエストを削除します。 選択した複数のリクエストを削除できます。 リスト内のリクエストを削除するには、リクエストを選択し、キーボードの「削除」を押します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> すべて選択 </p> </td> 
   <td colname="col2"> <p>すべてのリクエストを選択します。 <span class="wintitle">リクエストマネージャー</span>のリクエストリストの下側に、選択したリクエスト数が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>セルから </p> </td> 
   <td colname="col2"> <p>ワークシートからリクエスト用のデータを取得します。 リクエストがアクティブなワークシートで現在選択されているセルに関連付けられている場合、リスト内の関連するリクエストが選択されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 更新 </p> </td> 
   <td colname="col2"> <p>1つのリクエストまたは選択したリクエストを更新します。 （<a href="/help/analyze/legacy-report-builder/manage-requests/t-refresh-a-request.md"   > リクエストの更新</a>を参照）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>リストを更新 </p> </td> 
   <td colname="col2"> <p>表示されているすべてのリクエストを更新します。 すべてのリクエストを更新すると、サーバーからレポートに情報を更新する時間は、レポート内のリクエストの複雑さに直接比例します。 非常に大きなレポートの場合、すべてのリクエストを更新するには数分かかる場合があります。 このため、すぐに必要なリクエストは個別に更新し、「<span class="wintitle">すべて更新</span>」は時間があるときに実行してください。 </p> <p> <p>注意：複数のリクエストを含むワークシートを更新する場合は、<span class="wintitle">リクエストマネージャー</span>で結果を頻繁にしてください。 リクエスト失敗が発生した場合、診断列のエラーメッセージは、エラーの原因を特定するのに役立ちます。 ほとんどの場合、リクエストが失敗したときにエラーメッセージが表示されますが、エラーメッセージが生成されないことがあります。 更新によって、参照を含むセル内のデータが更新されないことや、更新によってセルからデータが削除されることがあります。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
