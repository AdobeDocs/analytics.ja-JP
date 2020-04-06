---
title: イベントのシリアル化
description: サイト上の指標の重複を除外するのに役立ちます。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# イベント ID のシリアル化

イベントのシリアル化とは、Analytics レポートに重複したイベントが追加されないようにすることです。訪問者がページを更新して指標を水増ししたくない場合、イベントの重複を排除することが重要です。

>[!NOTE]データソースはイベントのシリアル化または重複排除をサポートしていません。

## イベントシリアル化の設定

最初に、レポートスイートの設定でイベント [!UICONTROL Unique Event Recording] のをに設 [!UICONTROL Use Event ID] 定する必要があります。 詳しくは、『管理者ユーザーガイド』の[成功イベント](/help/admin/admin/c-success-events/success-event.md)を参照してください。

イベント ID を使用する場合、重複除外は次のレベルで発生します。

* 各変数は、重複除外用に独自の表を使用します。例えば、`event1:ABC` と `event2:ABC` は両方ともレポートでカウントされます。
* 重複除外は、すべての訪問者に対してグローバルに実行されます。訪問者 A が `event1:ABC` を送信し、訪問者 B も `event1:ABC` を送信した場合、2 番目の訪問者 B のインスタンスは無視されます。
* 重複除外には期限がありません。訪問者が `event1:ABC` を送信して、2 年後に再度訪問し、再度 `event1:ABC` を送信した場合、2 番目のインスタンスは無視されます。

>[!TIP] [`purchase`](event-purchase.md) イベントの重複を排除する場合は、代わりに [`purchaseID`](../purchaseid.md) 変数を使用します。

## Adobe Experience Platform Launch でのイベント ID の使用

イベント ID フィールドは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. Locate the [!UICONTROL Events] section, where each event contains an [!UICONTROL Event ID] field.

有効な値は、20 バイトまでの英数字です。

## AppMeasurement と Launch カスタムコードエディターでのイベント ID の使用

イベントシリアル化は `s.events` 変数の一部です。文字列内にコロンを使用して、各イベントに ID を割り当てます。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

イベントでシリアル化が有効になっていて、シリアル化 ID が含まれていない場合、イベントは常にカウントされます。
