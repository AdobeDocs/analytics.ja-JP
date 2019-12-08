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


# propN

プロパティ（`prop`）変数は、トラフィックモジュール内でカスタムレポートを作成するために使用します。


<!-- 

propN.xml

 -->

prop 変数は、パスレポートやクロス集計レポートで、（ページビューが送信された回数をカウントするために）カウンターとして使用することができます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | c1 ～ c75 | カスタムトラフィック | "" |

**構文と可能な値**

```js
s.propN="value"
```

[!UICONTROL プロパティ]変数には、標準的な変数の制限以外の制限はありません。

**例**

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**設定**

 変数用の訪問指標、訪問者指標およびパス指標の表示については、アドビ`prop`カスタマーケアにお問い合わせください。
