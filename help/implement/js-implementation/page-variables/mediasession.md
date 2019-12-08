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


# mediaSession

この変数は、使用されるビデオまたはメディアアセットのセグメントを指定します。


<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
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
   <td> 255 バイト </td> 
   <td> pev3 </td> 
   <td> ビデオ滞在時間 <p>閲覧ビデオセグメント </p> </td> 
   <td> なし </td> 
  </tr> 
 </tbody> 
</table>

**構文と可能な値** {#section_9A63266633C4427CB4A6549E4D887B85}

**autoTrack メソッド：**

[!UICONTROL s.Media.autoTrack] を使用する場合、*`mediaName`* 変数を明示的に導入する必要はありません。この変数は、JavaScript 版 AppMeasurement コードによって自動的に判別されます。

**手動トラッキングメソッド：**

構文:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

可能な値:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**例** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**注意事項、質問、ヒント** {#section_1BCEB037AB724B6EBE87420BD3604B88}

[!UICONTROL s.Media.autoTrack] を true に設定してもプレイヤーを追跡できない場合にのみ、メディアトラッキングメソッドを呼び出す必要があります。
