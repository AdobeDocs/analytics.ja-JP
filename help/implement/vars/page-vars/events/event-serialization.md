---
title: イベントのシリアル化
description: サイト上の指標の重複を除外するのに役立ちます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# イベントIDのシリアル化

イベントのシリアル化とは、Analytics レポートに重複したイベントが追加されないようにすることです。訪問者がページを更新して指標を水増ししたくない場合、イベントの重複を排除することが重要です。

> [!NOTE]データソースはイベントのシリアル化または重複排除をサポートしていません。

## イベントシリアル化の設定

最初に、レポートスイートの設定でイベントを [!UICONTROL Unique Event Recording] に設 [!UICONTROL Use Event ID] 定する必要があります。 See [Success Events](/help/admin/admin/c-success-events/success-event.md) in the Admin user guide.

イベントIDを使用する場合、重複除外は次のレベルで発生します。

* 各変数は、重複除外のために独自のテーブルを使用します。 例えば、とは両方 `event1:ABC` ともレ `event2:ABC` ポートでカウントされます。
* 重複除外は、すべての訪問者に対してグローバルに実行されます。 訪問者Aが送信した後、訪 `event1:ABC` 問者Bも送信した場合、アドビ `event1:ABC`は訪問者Bの2番目のインスタンスを無視します。
* 重複除外の期限は切れません。 訪問者が2年後に `event1:ABC` 再度訪問し、再度送信した場合、2 `event1:ABC` 番目のインスタンスは無視されます。

> [!TIP] イベントの重複を排除する場合は、代 [`purchase`](event-purchase.md) わりに変数を使 [`purchaseID`](../purchaseid.md) 用します。

## Adobe Experience Platform LaunchでのイベントIDの使用

イベントIDフィールドは、Analytics拡張（グローバル変数）の設定時に、またはルール内のアクションとして設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. で、既 [!UICONTROL Actions]存のアクションをク [!UICONTROL Adobe Analytics - Set Variables] リックするか、「+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Set Variables]す。
6. 各イベントにフ [!UICONTROL Events] ィールドが含まれるセクションを見つ [!UICONTROL Event ID] けます。

有効な値は、20バイト以内の英数字です。

## AppMeasurementでのイベントIDの使用とカスタムコードエディターの起動

イベントシリアル化は変数の一部 `s.events` です。 文字列内のコロンを使用して、各イベントにIDを割り当てます。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

イベントでシリアル化が有効になっているが、シリアル化IDが含まれていない場合、イベントは常にカウントされます。
