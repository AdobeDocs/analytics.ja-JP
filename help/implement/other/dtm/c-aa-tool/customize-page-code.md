---
description: Analytics のデプロイ時にページコードをカスタマイズするには、Dynamic Tag Management のフィールドの説明を使用します。
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: ページコードのカスタマイズ
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# ページコードのカスタマイズ

Analytics のデプロイ時にページコードをカスタマイズするには、Dynamic Tag Management のフィールドの説明を使用します。

**[!UICONTROL *`Property`*]**> **[!UICONTROL![](assets/settings_gear.png)

ツールの編集]**／**[!UICONTROL ページコードをカスタマイズ]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>エディターを開く </p> </td> 
   <td colname="col2"> <p><code> s.t()</code> に含まれる、最後の <code> s_code</code> 呼び出しの前にトリガーされる必要のある任意の JavaScript 呼び出しを挿入できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>実行 </p> </td> 
   <td colname="col2"> <p> 「<b>UI 設定の前</b>」：インターフェイス設定をカスタムコードよりも優先します（例えば、インターフェイスで設定が有効になっている場合に eVar をオーバーライドする場合）。 </p> <p> 「<b>UI 設定の後</b>」：カスタムコードをインターフェイス設定よりも優先します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

