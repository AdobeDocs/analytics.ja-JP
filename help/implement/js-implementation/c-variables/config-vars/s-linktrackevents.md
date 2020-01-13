---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: ca0797a353661a72d4064aa5aa84c3d9b7eb38a5

---


# s.linkTrackEvents

変数は、カスタムリンク、出口リンクまたはダウンロードリンクのトラッキング時に送信されるイベントのコンマ区切りのリストです。`linkTrackEvents` パラメーターには、すべてのファイルのダウンロード、出口リンク、カスタムリンクで追跡する各イベントを含める必要があります。これらのリンクタイプのいずれかが発生した場合、識別された各変数の現在値が追跡されます。この変数は、[`linkTrackVars`](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) に「events」が含まれる場合にのみ考慮されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | コンバージョン | 「なし」 |

イベントが `linkTrackEvents` に含まれていない場合、リンクの `onClick` イベントに入力されていても Analytics に送信されません。以下に例を示します。

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

[`linkTrackVars`](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) と `linkTrackEvents` の値が JS ファイルの設定に優先するので、カスタムリンクコードで指定された変数とイベントのみが特定リンクに対して確実に設定されます。両方の設定は、すべてのファイルのダウンロード数、出口リンク、カスタムリンクに影響します。各変数とイベントのインスタンスは、変数（またはイベント）が現在のページに適用される場合に増加できますが、特定のファイルのダウンロード、出口リンクまたはカスタムリンクでは増加できません。

カスタムリンクコードによって適切な変数が設定されるように、アドビではカスタムリンクコード内で   *`linkTrackVars`* および *`linkTrackEvents`* を次のように設定することをお勧めします。

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

上の例では、`prop1` の値はカスタムリンクコード内で設定されます。`prop2` の値はページで設定された変数の現在値から適用されます。

*メモ：`linkTrackVars`（または`linkTrackEvents`）が null（または "" のように空の文字列）の場合、現在のページに対して定義されたすべての Analytics 変数（またはイベント）が追跡されます。つまり、値を持つすべての変数がリンクデータと共に送信されます。これは、各変数のインスタンスを水増しする可能性が高くなります。他の変数に関連付けられたインスタンスやページビューの水増しを防ぐため、アドビでは、リンクトラッキングに使用するリンクの`linkTrackVars`イベントで`linkTrackEvents`および`onClick`を生成することをお勧めします。*

リンクデータ（カスタムリンク、出口リンク、ダウンロードリンク）と共に送信されるすべての変数を、`linkTrackVars` にリストする必要があります。`linkTrackEvents` を使用する場合は、`linkTrackVars` に「events」を含める必要があります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | いずれか | 「なし」 |

`linkTrackEvents` に値を入力する場合は、変数にプレフィックス「s.」を使用しないでください。例えば、「s.event1」を入力する代わりに、「event1」を使用して入力する必要があります。次の例は、使用方法を示しています。

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

最初のリンクでは。events 変数にはリンクがクリックされる前に設定された値が保持されています。これにより、`event1` がカスタムリンクで送信されます。2 番目の例では、`event2` へのリンクはは、`linkTrackEvents` にリストされていないので、記録されません。

混乱や潜在的な問題を回避するため、アドビでは、リンクトラッキングに使用するリンクの [ イベントに、`linkTrackVars`](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)`linkTrackEvents` および `onClick` を入力することをお勧めします。

## 構文と可能な値

*`linkTrackEvents`* 変数は、コンマで区切られたイベントのリストです（スペースは使用できません）。

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

 `linkTrackEvents` ではイベント名のみを使用できます。これらのイベントについては、[イベント](https://docs.adobe.com/content/help/ja-JP/analytics/implementation/analytics-basics/ref-events.html)にリストされています。イベント名の前または後ろにスペースがある場合、どのリンクイメージリクエストでもイベントは送信されません。

## 例

例えば、すべてのファイルのダウンロード、出口リンク、カスタムリンクで `prop1`、`eVar1`、および `event1` を追跡するには、グローバル JS ファイル内で以下の設定を使用します。

```
s.linkTrackVars="prop1,eVar1,events"
```

```
s.linkTrackEvents="event1"
```

**その他の例**

```
s.linkTrackEvents="purchase,event1"
```

```
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## 設定

なし

## 注意事項、質問、ヒント

* JavaScript ファイルは、`linkTrackEvents` に「events」変数が含まれている場合にのみ `linkTrackVars` を使用します。「events」は、`linkTrackVars` が定義されている場合にのみ、`linkTrackEvents` に含める必要があります。

* ページでイベントが発生するかどうか、およびそのイベントが `linkTrackEvents` にリストされているかどうかを把握しておいてください。このイベントは、出口リンク、ダウンロードリンクまたはカスタムリンクで再度記録されます。ただし、このイベントより前（リンクの `onClick` 内または `t()` 関数への呼び出しの後）に、events 変数がリセットされている場合を除きます。

* `linkTrackEvents` でイベント名の間にスペースが含まれていると、それらのイベントは記録されません。
