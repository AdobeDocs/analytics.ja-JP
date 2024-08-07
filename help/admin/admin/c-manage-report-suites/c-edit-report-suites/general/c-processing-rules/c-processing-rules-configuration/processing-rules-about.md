---
description: 処理ルールを使用して、定義した条件に基づいてデータを変更できます。属性や値が定義した条件に一致する場合、値を設定および削除でき、イベントを設定できます。
subtopic: Processing rules
title: 処理ルールのしくみ
feature: Processing Rules
role: Admin
exl-id: 9d2d9f2d-1e16-486f-9191-2c43776374da
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 94%

---

# 処理ルールのしくみ

処理ルールを使用して、定義した条件に基づいてデータを変更できます。属性や値が定義した条件に一致する場合、値を設定および削除でき、イベントを設定できます。

処理ルールはデータの収集時にデータに適用されます。また、ルールは、AppMeasurement ライブラリおよび Data Insertion API を介して取得されるすべてのデータに適用されます。処理ルールは、フルデータソースとログデータソースにも適用されます。これらのソースには、ユーザーが実行する *`hit`* またはアクションを表すデータが含まれています。 処理ルールは他のデータソースには適用されません。

## 重要な概念 {#section_EB138775E7C64C74B0D1D3213F7A823C}

次の表に、処理ルールを使用する場合に理解する必要がある主要な概念を示します。

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>概念 </p> </th> 
   <th colname="col2" class="entry"> <p>詳細 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ルールは単一のレポートスイートに適用されます。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> 他のレポートスイートへの処理ルールのコピー </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>処理ルールはリストに表示された順番で適用されます。 </p> </td> 
   <td colname="col2"> <p>アクションによって値が変更された場合、その後の条件では新しい値が使われます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>処理ルールは、保存後すぐにレポートスイートに適用されます。 </p> </td> 
   <td colname="col2"> <p>処理ルールの変更は、保存後数分以内にレポートスイートに表示される必要があります。処理ルールをテストする場合は、処理ルールの結果 <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md"> すばやく確認できるように </a> テストレポートスイートでリアルタイムレポートを設定することをお勧めします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>処理ルールは、コンテキストデータ変数にアクセスする唯一の方法です。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> コンテキストデータ変数の eVar へのコピー </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>処理ルールは、VISTA ルールとマーケティングチャネルルールの前に適用されます。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/technotes/processing-order.md"> 処理順序 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ヒットは除外できません。 </p> </td> 
   <td colname="col2"> <p>ヒットを除外するには、VISTA ルールを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>製品文字列、リファラー、ユーザーエージェントは変更できません。 </p> </td> 
   <td colname="col2"> <p>リファラーとユーザーエージェントは読み取り専用です。製品文字列は使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>モバイルデバイスの属性と分類は使用できません。 </p> </td> 
   <td colname="col2"> <p>モバイルデバイスの参照は、処理ルールの前におこなわれますが、処理ルールで属性は使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>JavaScript AppMeasurement H.25.2 以前を実行している場合は、URL の最初の 255 文字を超えるクエリ文字列パラメーターを読み取ることはできません。JavaScript AppMeasurement H.25.3 以降では、処理ルールに対してすべてのクエリ文字列パラメーターを含む完全修飾 URL が提供されます。 </p> </td> 
   <td colname="col2"> <p>H.25.3 以降へのアップグレードでは、長い URL のクライアントサイドからクエリ文字列パラメーターを読み取り、値を Context Data 変数に格納します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>処理ルールで読み取れるように、クエリ文字列値を Unicode または UTF-8 でエンコードする必要があります。 </p> </td> 
   <td colname="col2"> <p>これは、クエリ文字列を使用して渡されるマルチバイト文字に影響することがあります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>各レポートスイートでは、ルールの数は 150 個まで、ルールに含まれる条件の数は 30 個までに制限されます。 </p> </td> 
   <td colname="col2"> <p>処理ルールの制限は、会社ごとではなく、レポートスイートごとに適用されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>処理ルールは、データが送信される前に、コンテキストデータ変数を取得するように設定する必要があります。 </p> </td> 
   <td colname="col2"> <p>処理ルールは、サーバーの呼び出しが送信されるときに適用されます。コンテキストデータ変数に保存された値は、処理ルールを使用してコピーされない場合に破棄されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>UI の値の比較では、大文字と小文字が区別されません。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md">レポート内の値をクリーンアップします</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンテキストデータ変数の名前には、英数字、アンダースコアおよびドットのみを使用できます。それ以外の文字は削除されます。 </p> </td> 
   <td colname="col2"> <p>例えば、<code> login_page-home</code> というコンテキストデータ変数は、自動的に <code> login_pagehome</code> になります。<code> login_page-home</code> 変数に送信されるすべてのデータは、<code> login_pagehome</code> に割り当てられます。 </p> <p>サポートされていない文字を含むコンテキストデータ変数は、処理ルールインターフェイスに追加できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>キャレット（^）は処理ルールシステムの特殊文字です。 </p> </td> 
   <td colname="col2"> <p>単一のキャレットを照合するには、2 つのキャレット文字（^^）を使用します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 処理ルールの条件 {#section_387390EEE9BA4DA98698522A84326DB4}

条件は、ページ変数の一致する値または値が存在するかどうかをチェックします。複数の条件を追加でき、すべての条件が一致する必要があるかどうかを選択できます。

定義したアクションを常に実行する場合は、条件なしのルールを作成できます。

アクションがおこなわれる前に、変数の値は自動的にチェックされません。例えば Prop1 に「何か」の値が含まれていて、eVar1 が空であるとします。Prop1 を eVar1 と等しくなるように設定すると、両方の値が空になります。これを避けるには、値の存在をチェックする条件を追加します。

## 処理ルールのアクション {#section_E2285C9D008442C7BF136E52A9A4CC06}

アクションはページ変数を設定したり、ページ変数を削除したり、イベントをトリガーしたりします。アクションはレポートに表示する値を連結することもできます。

例えば、2 つの変数を連結して `category:product` を表示できます。
