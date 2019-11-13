---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 82060388a9a2122b66c57725cafa0eb4ce54e147

---


# s.linkTrackEvents

custom、exit、またはdownload 変数は、カスタムリンク、離脱リンクまたはダウンロードリンクのトラッキング時に送信されるイベントのコンマ区切りのリストです。The `linkTrackEvents` parameter should include each event you want to track with every file download, exit link, and custom link. これらのリンクタイプのいずれかが発生した場合、識別された各変数の現在値が追跡されます。この変数は、`linkTrackVars` に「events」が含まれる場合にのみ考慮されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | コンバージョン | "なし" |

If an event is not in `linkTrackEvents`, it is not sent to Analytics, even if it is populated in the `onClick` event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

The values of [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) and `linkTrackEvents` override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link. 両方の設定は、すべてのファイルのダウンロード数、離脱リンク、カスタムリンクに影響します。 各変数とイベントのインスタンスは、変数（またはイベント）が現在のページに適用される状況で水増しできますが、特定のファイルのダウンロード数、離脱リンクまたはカスタムリンクでは水増しできません。

カスタムリンクコードで適切な変数が設定されるように、カスタムリンクコード内で次のよ *`linkTrackVars`* うに設 *`linkTrackEvents`* 定することをお勧めします。

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

上の例では、prop1の値はカスタムリンクコード内に設定されています。 prop2 の値はページで設定された変数の現在値から適用されます。

*注意：(ま`linkTrackVars`たは`linkTrackEvents`)がnull（または""などの空の文字列）の場合、現在のページに対して定義されているすべてのAnalytics変数（またはイベント）が追跡されます。 つまり、値を持つすべての変数がリンクデータと共に送信されます。 これは、各変数のインスタンスを水増しする可能性が高くなります。 他の変数に関連付けられたインスタンスやページビューの水増しを防ぐため、アドビでは、リンクトラッキングに使用するリンクの`linkTrackVars`onClick`linkTrackEvents`イベントで[!UICONTROL および]を生成することをお勧めします。*

リンクデータ（カスタムリンク、離脱リンク、ダウンロードリンク）と共に送信されるすべての変数を、`linkTrackVars` にリストする必要があります。`linkTrackEvents` を使用する場合は、`linkTrackVars` に「events」を含める必要があります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | いずれか | "なし" |

When populating `linkTrackEvents`, do not use the 's.' prefix for variables. 例えば、「s.event1」を入力する代わりに、「event1」を入力する必要があります。 次の例は、その使用方法を示しています。

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

最初のリンクでは、イベント変数には、リンクがクリックされる前に設定された値が保持されています。 これにより、event1 がカスタムリンクで送信されます。In the second example, the link to event2 is not recorded because it is not listed in `linkTrackEvents`.

混乱や潜在的な問題を回避するため、アドビでは、リンクトラッキングに使用するリンクの [ イベントに、`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)`linkTrackEvents` および `onClick` を入力することをお勧めします。

## 構文と可能な値

*`linkTrackEvents`* 変数は、コンマで区切られたイベントのリストです（スペースは使用できません）。

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

 `linkTrackEvents` ではイベント名のみを使用できます。これらのイベントについては、「[イベント](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html)」にリストされています。イベント名の前または後にスペースがある場合、そのイベントはリンクイメージリクエストと共に送信できません。

## 例

To track `prop1`, `eVar1`, and `event1` with every file download, exit link, and custom link, use the following settings within the global JS file:

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

* ページでイベントが発生するかどうか、およびそのイベントが `linkTrackEvents` にリストされているかどうかを把握しておいてください。このイベントは、[!UICONTROL 離脱]リンク、[!UICONTROL ダウンロード]リンクまたは[!UICONTROL カスタム]リンクで再度記録されます。ただし、このイベントより前（リンクの [!UICONTROL onClick] 内または `t()` 関数への呼び出しの後）に、events 変数がリセットされている場合を除きます。

* `linkTrackEvents` でイベント名の間にスペースが含まれていると、それらのイベントは記録されません。
