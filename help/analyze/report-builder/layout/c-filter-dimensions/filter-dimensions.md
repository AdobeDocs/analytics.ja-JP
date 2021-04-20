---
description: ディメンションに対して、フィルターを設定できます。フィルターによって、表示されるディメンションのデータが絞り込まれます。フィルターは、ピボットレイアウトまたはカスタムレイアウトで適用できます。ピボットレイアウトからディメンションフィルターを設定する際は、さらにセルから表示エントリ数を指定することができます。
title: ディメンションフィルターの概要
uuid: c54d5add-f278-476d-8f14-73f1c2e37671
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 97%

---


# ディメンションフィルターの概要

ディメンションに対して、フィルターを設定できます。フィルターによって、表示されるディメンションのデータが絞り込まれます。フィルターは、ピボットレイアウトまたはカスタムレイアウトで適用できます。ピボットレイアウトからディメンションフィルターを設定する際は、さらにセルから表示エントリ数を指定することができます。

選択されたフィルターフォームに、Report Builder リクエストで選択されたエレメントおよび指標に基づいて値が入力されます。

## フィルターの定義 - 値と特殊文字 {#section_15840216A4044C40974945FAA435AD93}

**[!UICONTROL 最頻使用フィルター]**／**[!UICONTROL フィルターを定義]**&#x200B;パネルのフィルターについての情報です。

![](assets/define_filter.png)

次の表に、フィルターの例とフィルターについての情報を示します。

<table id="table_8AC3A26FF02143DBA949B30F2A46CF11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィルター </th> 
   <th colname="col02" class="entry"> 説明 </th> 
   <th colname="col2" class="entry"> フィルターの例 </th> 
   <th colname="col3" class="entry"> フィルタリング結果 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>すべての語句を含む </p> </td> 
   <td colname="col02"> <p>スペースで区切られた値すべて（順不同）を含むデータを抽出します。 </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>抽出される:<span class="term"> a b c</span> および <span class="term"> b a c</span>、など。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>いずれかの語句を含む </p> </td> 
   <td colname="col02"> <p>スペースで区切られた値の少なくとも 1 つを含むデータを抽出します。 </p> </td> 
   <td colname="col2"> <p>A B C </p> </td> 
   <td colname="col3"> <p>抽出される:<span class="term">A1</span>、<span class="term"> B2</span>、<span class="term"> C3</span> は抽出され、<span class="term"> D4</span> は抽出されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>フレーズを含む </p> </td> 
   <td colname="col02"> <p>フレーズを含むデータを抽出します。フレーズ以外の語句が付加される場合もあります。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>抽出される:<span class="term"> abc</span> および <span class="term"> abc def</span> が抽出される。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>いずれの語句も含まない </p> </td> 
   <td colname="col02"> <p>指定した値を含まないデータをすべて抽出します。 </p> </td> 
   <td colname="col2"> <p>a b c </p> </td> 
   <td colname="col3"> <p>抽出される:<span class="term"> d e f</span> を抽出し、<span class="term"> c d e f</span> は抽出されない。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>このフレーズを含まない </p> </td> 
   <td colname="col02"> <p>指定したフレーズを含まないデータをすべて抽出します。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>抽出されない：<span class="term"> abc</span>、<span class="term"> abc def</span> は除外され、<span class="term"> def</span> は抽出されない。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>次と等しい </p> </td> 
   <td colname="col02"> <p>指定した値と完全に一致するデータを抽出します。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p> <span class="term"> abc</span> のみが抽出されます。ほかのものは一切抽出される。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>等しくない </p> </td> 
   <td colname="col02"> <p>指定した値と一致しないデータをすべて抽出します。 </p> </td> 
   <td colname="col2"> <p>a </p> </td> 
   <td colname="col3"> <p>Does not match<span class="term"> a</span> は抽出される。 </p> <p><span class="term"> a b c</span> は抽出される。 </p> <p><span class="term"> abc</span> は抽出される。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>次の語句で始まる </p> </td> 
   <td colname="col02"> <p>指定した値で始まるデータを抽出します。 </p> </td> 
   <td colname="col2"> <p>abc </p> </td> 
   <td colname="col3"> <p>抽出される:<span class="term">abcd</span> は抽出され、<span class="term">1abc</span> は抽出されない。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>次の語句で終わる </p> </td> 
   <td colname="col02"> <p>指定した値で終わるデータを抽出します。 </p> </td> 
   <td colname="col2"> <p>xyz </p> </td> 
   <td colname="col3"> <p>抽出される:<span class="term"> wxyz</span> は抽出され、<span class="term"> wxyz0</span> は抽出されない。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アドバンス（特殊文字） </p> </td> 
   <td colname="col02"> <p>正規表現用の文字を使用できます。 </p> <p> <code> "", ^, -, *, $, | </code> </p> </td> 
   <td colname="col2"> <p>"^ホーム*ページ$" | スポーツ </p> </td> 
   <td colname="col3"> <p> このフィルターでは<span class="term">ホーム</span> で始まり、間に 0 文字以上の語を挟んで、<span class="term">ページ</span>で終わる文字列を抽出する。 </p> <p>さらに、その中の<span class="term">スポーツ</span>という名前の付いたページを含む。 </p> <p>抽出結果の例： </p> 
    <ul id="ul_72D76C5AFEAF405E8A0E4E3C604D10AE"> 
     <li id="li_4D490059B667450DA8A0103167C7B391">ホームページ </li> 
     <li id="li_1351619156274092AEB2771D882AD357">ホーム および (その他の文字列) ページ </li> 
     <li id="li_940EAA99A8CF49308E8471065EB317B1">ホーム スポーツ </li> 
     <li id="li_50A895F14A454BE9BF06EE0F07F99B3B">スポーツ ページ </li> 
     <li id="li_F3CE0D07941D4C2485D2DE0B73E00677">スポーツ </li> 
     <li id="li_E84C15C061824A5D922D9900392F2996">xyz スポーツ abc </li> 
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
   <td colname="col2"> 次と等しい </td> 
   <td colname="col3"> <p>引用符をペアで使用しなければエスケープされません。例えば、<span class="term"> 17" Display</span>はフレーズではありません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> * </td> 
   <td colname="col2"> ワイルドカード </td> 
   <td colname="col3"> <p>通常の正規表現で使われるアスタリスクと同じです。 </p> </td> 
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
   <td colname="col2"> OR </td> 
   <td colname="col3"> <p>サポートされるのは<span class="term">アドバンス（特殊文字）</span>フィルターでのみです。 </p> </td> 
  </tr> 
 </tbody> 
</table>
