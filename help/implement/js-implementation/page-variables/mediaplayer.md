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


# mediaPlayer

この変数はビデオまたはメディアを使用するプレイヤーを指定します。


<!-- 

mediaPlayer.xml

 -->

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | pev3 | ビデオプレイヤー | なし |

**構文と可能な値** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**autoTrack メソッド：**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**手動トラッキングメソッド：**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能な値:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**例** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**注意事項、質問、ヒント** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

s.Media.autoTrack を true に設定してもプレイヤーを追跡できない場合にのみ、メディアトラッキングメソッドを呼び出す必要があります。

