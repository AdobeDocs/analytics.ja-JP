---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkTrackEvents

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

[!DNL help.php] への最初のリンクでは、events 変数にはリンクがクリックされる前に設定された値が保持されています。これにより、event1 がカスタムリンクで送信されます。In the second example, the link to [!DNL test.php], event2 is not recorded because it is not listed in *`linkTrackEvents`*.

混乱や潜在的な問題を避けるため、アドビでは、リンクトラッキ *`linkTrackVars`* ングに使 *`linkTrackEvents`* 用するリ [!UICONTROL ンクのonClick] イベントにデータを埋め込むことをお勧めします。

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. この変数は、「events」が含まれ *`linkTrackVars`* る場合にのみ考慮されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | コンバージョン | "なし" |

## 構文と可能な値

Folio Builder *`linkTrackEvents`* 変数は、コンマで区切られたイベントのリストです（スペースは使用できません）。

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

 *`linkTrackEvents`*. These events are listed in [Events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). イベント名の前または後ろにスペースがある場合、どのリンクイメージリクエストでもイベントは送信されません。

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

* JavaScript ファイルでは  に「 *`linkTrackEvents`**`linkTrackVars`* events」変数が含まれる場合は、 「events」は、が定義されている場合にの *`linkTrackVars`* み含める必 *`linkTrackEvents`* 要があります。

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.
