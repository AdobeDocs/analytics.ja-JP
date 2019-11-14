---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# propN

プロパティ（[!UICONTROL prop]）変数は、[!UICONTROL トラフィックモジュール]内でカスタムレポートを作成するために使用します。

<!-- 

propN.xml

 -->

prop 変数は、パスレポートやクロス集計レポートで、（ページビューが送信された回数をカウントするために）カウンターとして使用することができます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | c1 ～ c75 | カスタムトラフィック | "" |

**構文と可能な値** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

[!UICONTROL プロパティ]変数には、標準的な変数の制限以外の制限はありません。

**例** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**設定** {#section_25FDEB6ECA8242A2A44EE540C083078A}

prop 変数用の[!UICONTROL 訪問]指標、[!UICONTROL 訪問者]指標および[!UICONTROL パス]指標の表示については、アドビ[!UICONTROL カスタマーケア]にお問い合わせください。
