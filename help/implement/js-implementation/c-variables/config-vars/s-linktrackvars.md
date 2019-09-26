---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkTrackVars

 変数は、カスタムリンク、離脱リンク、ダウンロードリンクで送信される変数のコンマ区切りのリストです。

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. 他の変数に関連付けられたインスタンスやページビューの水増しを防ぐため、アドビでは、リンクトラッキ *`linkTrackVars`* ングに使 *`linkTrackEvents`* 用されるリンクの [!UICONTROL onClick] イベントにデータを埋め込むことをお勧めします。

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. を使 *`linkTrackEvents`* 用する場合は、 *`linkTrackVars`* 「events」を含める必要があります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | いずれか | "なし" |

埋め込み時 *`linkTrackVars`*, do not use the 's.' prefix for variables. 例えば、「s.prop1」 *`linkTrackVars`* を入力する代わりに、「prop1」を入力する必要があります。 次の例は、使用方法 *`linkTrackVars`* を示しています。

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

google.com へのリンクは離脱リンクであるので（現在の場所が Google である場合を除く）、event1 と eVar1 は離脱リンクデータと共に送信され、eVar1 に関連付けられているインスタンスの数および event1 の発生回数が増加します。In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

## 構文と可能な値

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. つまり、「s.eVar1」ではなく「eVar1」を使用します。

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

Folio Builder 変数に *`linkTrackVars`* は、送信先の変数のみを含めるこ [!DNL Analytics]とができます。 *`events`*,,,, *`campaign`* eVar1-75, *`purchaseID`* eVar1-75 *`products`*, prop1-75, [!UICONTROL prop1-prop1,]prop1, [!UICONTROL prop, prop,]prod, *`channel`**`server`**`state`**`zip`**`pageType`* prod.

## 例

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## 設定

なし

## 注意事項、質問、ヒント

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* を使 *`linkTrackEvents`* 用する場合は、 *`linkTrackVars`* 「events」を含める必要があります。

* 変数に「s.」または「s_objectname」のプレフィックスを使用しないでください。