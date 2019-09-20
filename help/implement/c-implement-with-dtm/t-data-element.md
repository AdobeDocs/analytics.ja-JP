---
description: Dynamic Tag Management でデータ要素を作成します。
keywords: Dynamic Tag Management；データ要素；新しいデータ要素を作成；名前；型；デフォルト値；強制小文字の値；この値を
seo-description: Dynamic Tag Management でデータ要素を作成します。
seo-title: データ要素の作成
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: データ要素の作成
uuid: eacd5c60-6197-4129-a9e1-a39e9a58b38a
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# データ要素の作成

Dynamic Tag Management でデータ要素を作成します。

1. [Web プロパティを作成します](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)（まだ作成していない場合）。
1. In the web property, click **[!UICONTROL Rules]** &gt; **[!UICONTROL Data Elements]**.
1. 「**[!UICONTROL 新規データ要素を作成]**」をクリックします。
1. 次のフィールドおよびオプションに情報を入力します。

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> オプション</th> 
      <th class="chdeschd"> 説明</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>名前</strong></td> 
      <td class="chdesc stentry"> <p>マーケティング担当者が認識できる、データ要素のわかりやすい名前。例えば、 
        <code>
          製品 ID
        </code>. </p> <p> <p>注意：ルール作成時には、ID ではなく名前が参照されます。データ要素の名前を変更した場合は、それを使用しているルール内の参照をすべて変更する必要があります。 </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>タイプ</strong></td> 
      <td class="chdesc stentry"> <p> JS オブジェクト、CSS セレクター、Cookie、URL パラメーター、カスタムスクリプトなど、データ取得元のタイプを指定します。 </p> <p>選択したタイプに応じて、異なるオプションが表示されます。詳細と例については、Dynamic Tag Management 製品ドキュメントの<a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html" format="html" scope="external">データ要素のタイプ</a>を参照してください。 </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>デフォルト値</strong></td> 
      <td class="chdesc stentry"> <p>デフォルトの値。この値は、URL パラメーターが存在しない、または Dynamic Tag Management で見つからない場合でも、データ要素が常に値を持つようにします。 </p> <p> <p>注意：値がなくデフォルト値も指定されていない場合、戻り値は返されず、そのデータ要素を参照する変数は設定されません。ただし、「カスタムコード」データ要素ではデフォルト値フィールドが無視されます。 </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>強制的に小文字に変換値</strong></td> 
      <td class="chdesc stentry"> <p>値が自動的に小文字に変換されるようにします。 </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>この値を記憶しておく期間</strong></td> 
      <td class="chdesc stentry"> <p>Dynamic Tag Management にこの値を記憶させておく期間。 </p> <p> 有効な設定値は以下のとおりです。 </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>セッション：セッションベースのタイミングは、実装によって変わる可能性があります。セッションデータ要素は、セッション Cookie に設定されます。ただし、この設定は Web サーバーやブラウザーの機能に基づくものです。Reports &amp; Analytics で使用されるマーケティング的な意味のセッション（訪問）とは関係ありません。 </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>ページビュー </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>訪問者 </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   データ要素の使用方法について詳しくは、Adobe Tag Management 製品ドキュメントの[データ要素](https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html)を参照してください。
1. Click **[!UICONTROL Save Data Element]**.
