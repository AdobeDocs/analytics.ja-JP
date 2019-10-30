---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkTrackEvents

[!UICONTROL custom]、[!UICONTROL exit]、または[!UICONTROL download] 変数は、カスタムリンク、離脱リンクまたはダウンロードリンクのトラッキング時に送信されるイベントのコンマ区切りのリストです。

イベントが *`linkTrackEvents`* に含まれていない場合、リンクの [!UICONTROL onClick] イベントに入力されていても、[!DNL Analytics] に送信されません。以下に例を示します。

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

[!DNL help.php] への最初のリンクでは、events 変数にはリンクがクリックされる前に設定された値が保持されています。これにより、event1 がカスタムリンクで送信されます。2 番目の例である [!DNL test.php] へのリンクでは、event2 は *`linkTrackEvents`* にリストされていないので、記録されません。

混乱や潜在的な問題を回避するため、アドビでは、リンクトラッキングに使用するリンクの [!UICONTROL onClick] イベントに、*`linkTrackVars`* および *`linkTrackEvents`* を入力することをお勧めします。

*`linkTrackEvents`* 変数には、[!UICONTROL カスタム]リンク、[!UICONTROL ダウンロード]リンクおよび[!UICONTROL 離脱]リンクで送信されるイベントが含まれます。この変数は、*`linkTrackVars`* に「events」が含まれる場合にのみ考慮されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | コンバージョン | "なし" |

## 構文と可能な値

*`linkTrackEvents`* 変数は、コンマで区切られたイベントのリストです（スペースは使用できません）。

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

 *`linkTrackEvents`* ではイベント名のみを使用できます。これらのイベントについては、「[イベント](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html)」にリストされています。イベント名の前または後ろにスペースがある場合、どのリンクイメージリクエストでもイベントは送信されません。

## 例

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## 設定

なし

## 注意事項、質問、ヒント

* JavaScript ファイルは、*`linkTrackVars`* に「events」変数が含まれている場合にのみ *`linkTrackEvents`* を使用します。「events」は、*`linkTrackEvents`* が定義されている場合にのみ、*`linkTrackVars`* に含める必要があります。

* ページでイベントが発生するかどうか、およびそのイベントが *`linkTrackEvents`* にリストされているかどうかを把握しておいてください。このイベントは、[!UICONTROL 離脱]リンク、[!UICONTROL ダウンロード]リンクまたは[!UICONTROL カスタム]リンクで再度記録されます。ただし、このイベントより前（リンクの [!UICONTROL onClick] 内または *`t()`* 関数への呼び出しの後）に、events 変数がリセットされている場合を除きます。

* *`linkTrackEvents`* でイベント名の間にスペースが含まれていると、それらのイベントは記録されません。
