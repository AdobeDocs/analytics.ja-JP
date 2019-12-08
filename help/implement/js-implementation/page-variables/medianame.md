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


# mediaName

この変数はビデオまたはメディアの名前を指定します。


<!-- 

mediaName.xml

 -->

この変数は、[!UICONTROL Data Insertion API] と[!UICONTROL フル処理のデータソース]を介してのみ使用できます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 64 KB | pev3 | ビデオ、次のビデオフロー、前のビデオフロー、閲覧ビデオセグメント、ビデオ滞在時間 | なし |

**構文と可能な値** {#section_F97A2253BBD24FEBBC225F233A319F5D}

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

```js
s.Media.close(mediaName)
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

```js
s.Media.close("de_bofr_1045Making_400k")
```

**例** {#section_4B9584265B1A47289818141B2A88021D}

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
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**注意事項、質問、ヒント** {#section_941A445BB52E4063B0F6920E61BB90DE}

* [!UICONTROL s.Media.autoTrack] を true に設定してもプレイヤーを追跡できない場合にのみ、メディアトラッキングメソッドを呼び出す必要があります。
* この変数は、VARCHAR(100) とは対照的に、mySQL TEXT 変数として格納されます。
