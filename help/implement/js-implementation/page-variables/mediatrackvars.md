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


# media.trackVars

 変数は、どの変数がメディアヒットと共に送信されるかを示します。


<!-- 

media_trackVars.xml

 -->

この変数は、JavaScript と [!UICONTROL ActionSource] でのみ適用できます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | s.Media.trackVars="None" |

**構文と可能な値** {#section_7374684A7EB34AE685E8C40A66CFD289}

[!UICONTROL propN]、*`eVarN`*、*`events`*, *`channel`*、などの変数。

**例** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**注意事項、質問、ヒント** {#section_615AE1B696124B00B78F651B03813EAB}

* [!UICONTROL trackVars] で eVar3 を指定した場合でも、この変数はメディアヒットと共に送信されます。

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

 変数は、訪問者の識別に使用される cookie と加入者 ID の順序を制御します。

<!-- 

mobile.xml

 -->

「[モバイルネットワークプロトコル](/help/implement/js-implementation/c-additional-libraries/network-protocols.md)」を参照してください。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | イメージ URL のパス内の /5/ または /1/ | 該当なし | なし |

**構文と可能な値** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**注意事項、質問、ヒント** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

JavaScript cookie 実装で *`s.mobile`* 変数を使用する場合は、訪問者の識別を使用して、訪問者トラフィックのスパイクが発生する可能性を軽減します。
