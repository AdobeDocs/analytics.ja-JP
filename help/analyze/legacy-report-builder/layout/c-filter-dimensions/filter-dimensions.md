---
description: 行ラベル グリッドに追加するディメンションをフィルタリングできます。 フィルターは、リクエストによって返されるデータを絞り込み、ピボットまたはカスタムレイアウトから適用できます。 ピボットレイアウトからディメンションフィルターを設定する際は、さらにセルから表示エントリ数を指定できます。
title: ディメンションフィルターの概要
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: User, Admin
exl-id: eded07d5-3c06-419b-92fd-1a48856ac293
TQID: https://experienceleague.adobe.com/yY1Sl6vEWRb-62SzM5e5qxt5lZPHeg-LU5ZiUNb5z8Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 28%

---

# ディメンションフィルターの概要

{{legacy-arb}}

行ラベル グリッドに追加するディメンションをフィルタリングできます。 フィルターは、リクエストによって返されるデータを絞り込み、ピボットまたはカスタムレイアウトから適用できます。 ピボットレイアウトからディメンションフィルターを設定する際は、さらにセルから表示エントリ数を指定できます。

選択したフィルターフォームは、Report Builder リクエストで選択した要素と指標に基づいて入力されます。

## フィルターの定義 - 値と特殊文字 {#section_15840216A4044C40974945FAA435AD93}

**[!UICONTROL 最も人気のあるフィルター]** / **[!UICONTROL フィルターを定義]** パネルのフィルターに関する情報。

アプリケーション、ユーザー、およびプロジェクトでフィルターを適用するオプションを含むフィルターを定義ダイアログを表示する![ スクリーンショット。](/help/admin/tools/assets/filter.png)

次の表に、フィルターに関する例と情報を示します。

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィルター </th> 
   <th colname="col02" class="entry"> 説明 </th> 
   <th colname="col2" class="entry"> フィルターの例 </th> 
   <th colname="col3" class="entry"> 結果を一致 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>すべての語句を含む </p> </td> 
   <td colname="col02"> <p>スペースで区切られたすべての値を任意の順序で含みます。 </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p><span class="term"> a b c</span>と<span class="term"> b a c</span>に一致します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>が次のいずれかの語句を含む </p> </td> 
   <td colname="col02"> <p>1つ以上のフィルター（スペース区切り）が含まれています。 </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p><span class="term"> A1</span>、<span class="term"> B2</span>、<span class="term"> C3</span>に一致しますが、<span class="term"> D4</span>には一致しません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>が次のフレーズを含む </p> </td> 
   <td colname="col02"> <p>検索フィルターと、場合によっては他の用語が含まれています。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p><span class="term"> abc</span>と<span class="term"> abc def</span>に一致します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>が次のいずれの語句も含まない </p> </td> 
   <td colname="col02"> <p>入力した値が含まれていない限り、すべてを返します。 </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p><span class="term"> d e f</span>に一致しますが、<span class="term"> c d e f</span>には一致しません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>が次のフレーズを含まない </p> </td> 
   <td colname="col02"> <p>フレーズが含まれていないすべてを返します。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p><span class="term"> abc</span>、<span class="term"> abc def</span>を除外し、<span class="term"> def</span>と一致します </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>が次に等しい </p> </td> 
   <td colname="col02"> <p>完全一致を返します。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> のみが抽出されます。ほかのものは一切抽出される。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>が次に等しくない </p> </td> 
   <td colname="col02"> <p>エントリと完全に一致しない項目を返します。 </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p><span class="term"> a</span>と一致しません。 </p> <p><span class="term"> a b c</span> は抽出される。 </p> <p><span class="term"> abc</span> は抽出される。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>次の語句で始まる </p> </td> 
   <td colname="col02"> <p>特定の値で始まる結果を返します。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p><span class="term"> abcd</span>に一致しますが、<span class="term"> 1abc</span>には一致しません </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>次の語句で終わる </p> </td> 
   <td colname="col02"> <p>特定の値で終わる結果を返します。 </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p><span class="term"> wxyz</span>に一致しますが、<span class="term"> wxyz0</span>には一致しません </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>詳細設定（特殊文字） </p> </td> 
   <td colname="col02"> <p>正規表現の文字を使用できます。 </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^ホーム*ページ$" | スポーツ </p> </td> 
   <td colname="col3"> <p> これは、<span class="term"> ホーム </span>で始まり、0文字以上を検索し、<span class="term"> ページ </span>で終わるフィルターを定義します。 </p> <p>さらに、その中の<span class="term">スポーツ</span>という名前の付いたページを含む。 </p> <p>いくつかの例は次のようになります。 </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">HomePage </li> 
     <li id="li_1351619156274092AEB2771D882AD357">ホームと（その他の文字） ページ </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">ホームスポーツ </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">スポーツページ </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">スポーツ </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz sports abc </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8BBB06C8860745DEA41B39673699DC0F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特殊文字 </th> 
   <th colname="col2" class="entry"> 目的 </th> 
   <th colname="col3" class="entry"> メモ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> " " </td> 
   <td colname="col2"> が次に等しい </td> 
   <td colname="col3"> <p>引用符をペアで使用しなければエスケープされません。 例えば、<span class="term">17" ディスプレイ</span>はフレーズではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> ワイルドカード </td> 
   <td colname="col3"> <p>正規表現で使用されるアスタリスクと同じです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ^ </td> 
   <td colname="col2"> 次の語句で始まる </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> $ </td> 
   <td colname="col2"> 次の語句で終わる </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> - </td> 
   <td colname="col2"> Not </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> | </td> 
   <td colname="col2"> または </td> 
   <td colname="col3"> <p><span class="term">詳細（特殊文字） </span> フィルターでのみサポートされます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
