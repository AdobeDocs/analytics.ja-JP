---
title: イベントのシリアル化
description: サイト上の指標の重複を除外するのに役立ちます。
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# イベントIDのシリアル化

イベントのシリアル化とは、Analytics レポートに重複したイベントが追加されないようにすることです。訪問者がページを更新して指標を水増ししたくない場合、イベントの重複を排除することが重要です。

> [!NOTE]データソースはイベントのシリアル化または重複排除をサポートしていません。

## イベントシリアル化の設定

最初に、イベントの個別イベントの記録を [!UICONTROL 「イベントIDを使用] 」に設 [!UICONTROL 定する必要があります] 。 See [Success Events](../../../../admin/admin/c-success-events/success-event.md) in the Admin user guide.

イベントIDを使用する場合、重複除外は次のレベルで発生します。

* 各変数は、重複除外用に独自のテーブルを使用します。 例えば、とは両方 `event1:ABC` ともレ `event2:ABC` ポートでカウントされます。
* 重複除外は、すべての訪問者に対してグローバルに実行されます。 訪問者Aが送信し、訪 `event1:ABC` 問者Bも送信する場合、ア `event1:ABC`ドビは訪問者Bの2番目のインスタンスを無視します。
* 重複除外の期限は切れません。 訪問者が2年後に再 `event1:ABC` 度訪問し、再度送信した場合、2 `event1:ABC` 番目のインスタンスは無視されます。

> [!TIP] イベントの重複を排除する場合は、代 `purchase` わりに変数を使 `purchaseID` 用します。

## Adobe Experience Platform LaunchでのイベントIDの使用

イベントIDフィールドは、Analytics拡張の設定時（グローバル変数）に、またはルール内のアクションとして設定できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で、既存の [!UICONTROL Adobe Analytics — 変数の設定アクションをクリックするか] 、「+」アイコンをクリックします。
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「変数 [!UICONTROL を設定」に設定します]。
6. 「 [!UICONTROL Events] 」セクションを探します。各イベントには「 [!UICONTROL Event ID] 」フィールドが含まれます。

有効な値は、20バイトまでの英数字です。

## AppMeasurementでのイベントIDの使用とカスタムコードエディターの起動

イベントシリアル化は変数の一部 `s.events` です。 文字列内にコロンを使用して、各イベントにIDを割り当てます。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

イベントでシリアル化が有効になっていて、シリアル化IDが含まれていない場合、イベントは常にカウントされます。
