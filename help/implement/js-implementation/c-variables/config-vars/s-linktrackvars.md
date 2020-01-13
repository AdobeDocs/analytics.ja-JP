---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkTrackVars

 変数は、カスタムリンク、出口リンク、ダウンロードリンクで送信される変数のコンマ区切りのリストです。

[`linkTrackVars`](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)パラメーターには、すべてのファイルのダウンロード、出口リンク、カスタムリンクで追跡する各変数を含める必要があります。

JS ファイル内の `linkTrackVars` と `linkTrackEvents` の設定は、すべてのファイルダウンロード、出口リンクおよびカスタムリンクに影響を与えます。各変数とイベントのインスタンスは、変数（またはイベント）が現在のページに適用される場合に増加できますが、特定のファイルのダウンロード、出口リンクまたはカスタムリンクでは増加できません。

カスタムリンクコードで適切な変数が設定されるように、カスタムリンクコード内で `linkTrackVars` と `linkTrackEvents` を以下のように設定することをお勧めします。

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

上の例では、prop1 の値はカスタムリンクコード内で設定されます。prop2 の値はページで設定された変数の現在値から適用されます。

`linkTrackVars` と `linkTrackEvents` の値が JS ファイルの設定に優先するので、カスタムリンクコードで指定された変数とイベントのみが特定リンクに対して確実に設定されます。

*メモ：`linkTrackVars`（または`linkTrackEvents`）が null（または "" のように空の文字列）の場合、現在のページに対して定義されたすべての Analytics 変数（またはイベント）が追跡されます。つまり、値を持つすべての変数がリンクデータと共に送信されます。これは、各変数のインスタンスを水増しする可能性が高くなります。他の変数に関連付けられたインスタンスやページビューの水増しを防ぐため、アドビでは、リンクトラッキングに使用するリンクの`linkTrackVars`onClick`linkTrackEvents`イベントで[!UICONTROL および]を生成することをお勧めします。*

リンクデータ（カスタムリンク、出口リンク、ダウンロードリンク）と共に送信されるすべての変数を、`linkTrackVars` にリストする必要があります。`linkTrackEvents` を使用する場合は、`linkTrackVars` に「events」を含める必要があります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | いずれか | 「なし」 |

`linkTrackVars` に値を入力する場合は、変数にプレフィックス「s.」を使用しないでください。例えば、「s.prop1」を使用して `linkTrackVars` に入力する代わりに、「prop1」を使用して入力する必要があります。次の例は、`linkTrackVars` の使用方法を示しています。

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

google.com へのリンクは出口リンクであるので（現在の場所が Google である場合を除く）、event1 と eVar1 は出口リンクデータと共に送信され、eVar1 に関連付けられているインスタンスの数および event1 の発生回数が増加します。[!DNL test.php] が呼び出された時点でのeVar1 の現在の値が「value C」なので、[!UICONTROL へのリンクでは、]eVar1`tl()` が「value C」という値で送信されます。

## 構文と可能な値

`linkTrackVars` 変数は、コンマで区切られた変数名のリストです。大文字と小文字が区別され、変数名にはオブジェクト名のプレフィックスを含めません。つまり、「s.eVar1」ではなく「eVar1」を使用します。

```
s.linkTrackVars="variable_name[,variable_name[...]]"
```

`linkTrackVars` 変数には、[!DNL Analytics] に送信される変数のみを含めることができます。例：`events`、`campaign`、`purchaseID`、`products`、`eVar1-75`、`prop1-75`、`hier1-5`、`channel`、`server`、`state`、`zip`、`pageType`。

## 例

```
s.linkTrackVars="events,prop1,eVar49"
```

```
s.linkTrackVars="products"
```

## 設定

なし

## 注意事項、質問、ヒント

* `linkTrackVars` が空白に設定されている場合、値を持つすべての変数がすべてのサーバーコールで追跡されます。
* `linkTrackVars` に含まれる変数で、ダウンロードリンク、出口リンクまたはカスタムリンクのクリック時点で値を持つものが追跡されます。
* `linkTrackEvents` を使用する場合は、`linkTrackVars` に「events」を含める必要があります。

* 変数に「s.」または「s_objectname」のプレフィックスを使用しないでください。
