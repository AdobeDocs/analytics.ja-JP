---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# mediaLength

変数は、再生されるメディアの合計の長さを指定します。


<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大サイズ </th> 
   <th class="entry"> デバッガーパラメーター </th> 
   <th class="entry"> 入力されるレポート </th> 
   <th class="entry"> デフォルト値 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> pev3 リクエスト全体に対しては最大サイズはありません。サイズはブラウザーにおける URL の長さの限度に制限されます。 </td> 
   <td> pev3 </td> 
   <td> ビデオ滞在時間、 <p>閲覧ビデオセグメント </p> </td> 
   <td> なし </td> 
  </tr> 
 </tbody> 
</table>

**構文と可能な値** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**autoTrack メソッド：**

[!UICONTROL s.Media.autoTrack] を使用する場合、[!UICONTROL mediaLength] 変数を明示的に導入する必要はありません。この変数は、JavaScript 版 AppMeasurement コードによって自動的に判別されます。

**手動トラッキングメソッド：**

構文:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能な値:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**例** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**注意事項、質問、ヒント** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* [!UICONTROL s.Media.autoTrack] を true に設定してもプレイヤーを追跡できない場合にのみ、メディアトラッキングメソッドを呼び出す必要があります。
* [!UICONTROL autoTrack] を使用したトラッキングでない場合は、長さを秒数で設定するようにしてください。

