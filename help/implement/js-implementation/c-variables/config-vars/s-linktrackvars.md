---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.linkTrackVars

 変数は、カスタムリンク、離脱リンク、ダウンロードリンクで送信される変数のコンマ区切りのリストです。

*`linkTrackVars`*&#x200B;が "" に設定されている場合、値を持つすべての変数がリンクデータと共に送信されます。他の変数に関連付けられたインスタンスやページビューの水増しを防ぐため、アドビでは、リンクトラッキングに使用するリンクの [!UICONTROL onClick] イベントで *`linkTrackVars`* および *`linkTrackEvents`* を生成することをお勧めします。

リンクデータ（カスタムリンク、離脱リンク、ダウンロードリンク）と共に送信されるすべての変数を、*`linkTrackVars`* にリストする必要があります。*`linkTrackEvents`* を使用する場合は、*`linkTrackVars`* に「events」を含める必要があります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | いずれか | "なし" |

When populating *`linkTrackVars`*, do not use the 's.' prefix for variables. 例えば、「s.prop1」を使用して *`linkTrackVars`* に入力する代わりに、「prop1」を使用して入力する必要があります。次の例は、*`linkTrackVars`* の使用方法を示しています。

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

google.com へのリンクは離脱リンクであるので（現在の場所が Google である場合を除く）、event1 と eVar1 は離脱リンクデータと共に送信され、eVar1 に関連付けられているインスタンスの数および event1 の発生回数が増加します。*`tl()`* が呼び出された時点での[!UICONTROL eVar1] の現在の値が「value C」なので、[!DNL test.php]へのリンクでは、[!UICONTROL eVar1] が「value C」という値で送信されます。

## 構文と可能な値

*`linkTrackVars`* 変数は、コンマで区切られた変数名のリストです。大文字と小文字が区別され、変数名にはオブジェクト名のプレフィックスを含めません。つまり、「s.eVar1」ではなく「eVar1」を使用します。

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

Folio Builder *`linkTrackVars`* 変数には、[!DNL Analytics] に送信される変数のみを含めることができます。例：*`events`*、*`campaign`*、*`purchaseID`*、*`products`*、[!UICONTROL eVar1-75]、[!UICONTROL prop1-75]、[!UICONTROL hier1-5]、*`channel`*、*`server`*、*`state`*、*`zip`*、and *`pageType`*。

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

* *`linkTrackVars`* が空白に設定されている場合、値を持つすべての変数がすべてのサーバーコールで追跡されます。
* *`linkTrackVars`* に含まれる変数で、ダウンロードリンク、離脱リンクまたはカスタムリンクのクリック時点で値を持つものが追跡されます。
* *`linkTrackEvents`* を使用する場合は、*`linkTrackVars`* に「events」を含める必要があります。

* 変数に「s.」または「s_objectname」のプレフィックスを使用しないでください。
