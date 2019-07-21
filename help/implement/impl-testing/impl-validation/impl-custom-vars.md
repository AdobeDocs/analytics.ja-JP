---
description: Analytics で使用されるカスタム変数の一覧です。
keywords: Analytics の導入
seo-description: Analytics で使用されるカスタム変数の一覧です。
seo-title: カスタム変数 ～
solution: Analytics
title: カスタム変数 ～
topic: 開発者と導入
uuid: 54adf622-7f05-49c0- b7e6-702bb2f17b1c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# カスタム変数 ～

Analytics で使用されるカスタム変数の一覧です。

<table id="table_E8C7871F63F648A59644638FB56BD0E1"> 
 <thead> 
  <tr> 
   <th class="entry"> 変数 </th> 
   <th class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> トラフィック変数 </td> 
   <td> prop1 ～ 75 の値をチェックします。以下は、チェックすべき項目の一覧です。 
    <ul id="ul_0EE2D50BA90F4F21BD63268A5082F980"> 
     <li id="li_A6E4D66E8A03400491A26A08E4945908">大文字と小文字を正しく使用しているか。「ValueA」と「valueA」は異なるレコードと見なされます。一部のブラウザーではすべての変数が小文字に変換されるので、すべて小文字を使用するとよいでしょう。 </li> 
     <li id="li_65CBFB908E7B4ED5AF9518FE5B58D4E2">値の長さは 100 文字未満であるか。100 文字以上の場合は、値が一部切り詰められる可能性があります。 </li> 
     <li id="li_CC506D114AFE44699D89AB84BBCCEBFC"> 1 つのプロパティ変数内のすべての値が関連した値であるか。無関係に見える値がないか。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> コンバージョン変数 </td> 
   <td> <span class="wintitle">コンバージョン</span>変数には eVar 1 ～ 75 が含まれます。以下は、チェックすべき問題の一覧です。 
    <ul id="ul_CA10C5B9F24B4C49A64CA84A9DCE8E63"> 
     <li id="li_8CCD92F3AD5E49EBA91C9B008DA47016">大文字と小文字を正しく使用しているか。「ValueA」と「valueA」は異なるレコードと見なされます。一部のブラウザーではすべての変数が小文字に変換されるので、すべて小文字を使用するとよいでしょう。 </li> 
     <li id="li_5B6FDEDB2C32409AA59D6BB0DF2346CB">値の長さは 255 文字未満であるか。100 文字以上の場合は、値が一部切り詰められる可能性があります。 </li> 
     <li id="li_C31AFBAC99D84E96A1244E795CE7765D">1 つの eVar 内のすべての値が関連した値であるか。無関係に見える値がないか。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> カスタムイベント </td> 
   <td> イベントには、標準的な値（<span class="wintitle">prodView</span>、<span class="wintitle">scOpen</span>、<span class="wintitle">scAdd</span>、<span class="wintitle">scCheckout</span>、<span class="wintitle">purchase</span>）の他に、event1 ～ event100 のカスタムイベントがあります。すべてのイベントは events 変数内で送信されます。同じページ上の複数のイベントは、空白文字ではなくコンマで区切る必要があります。 
    <ul id="ul_2213CC9DE892433FAF6FC1F5A2B841B4"> 
     <li id="li_15E31A9FF1654DFA93C158F422B9EAE3">また、標準的なコンバージョンイベントのすべてにおいて、products に適切な製品を設定する必要があります。購入を除くすべてのイベントで、qty と price という要素はオプションです。 </li> 
     <li id="li_03ED9AAC45DA47A58AB482E2CEBF5108"><span class="wintitle">購入</span>イベントは、購入が完了し確定された後、セッション内で 1 回だけ設定する必要があります。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

