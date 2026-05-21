---
title: イベントのシリアル化
description: サイト上の指標の重複を除外するのに役立ちます。
feature: Appmeasurement Implementation
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
role: Admin, Developer
TQID: https://experienceleague.adobe.com/43YfbDVjSH7ZJ8kqlXwAnb8UsIEoG3Ei-NRnkLLW63Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 87%

---

# イベント ID のシリアル化

イベントのシリアル化とは、Analytics レポートに重複したイベントが追加されないようにすることです。 訪問者がページを更新して指標を水増ししたくない場合、イベントの重複を排除することが重要です。

>[!NOTE]
>
>データソースはイベントのシリアル化または重複排除をサポートしていません。

## イベントシリアル化の設定

まず、レポートスイートの設定で、イベントの[!UICONTROL 個別イベントの記録]を[!UICONTROL イベント ID を使用]に設定する必要があります。 詳しくは、『管理者ユーザーガイド』の[成功イベント](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)を参照してください。

イベント ID を使用する場合、重複除外は次のレベルで発生します。

* 各変数は、重複除外用に独自の表を使用します。 例えば、`event1:ABC` と `event2:ABC` は両方ともレポートでカウントされます。
* 重複除外は、すべての訪問者に対してグローバルに実行されます。 訪問者 A が `event1:ABC` を送信し、訪問者 B も `event1:ABC` を送信した場合、2 番目の訪問者 B のインスタンスは無視されます。
* 重複除外には期限がありません。 訪問者が `event1:ABC` を送信して、2 年後に再度訪問し、再度 `event1:ABC` を送信した場合、2 番目のインスタンスは無視されます。

>[!TIP]
>
>[`purchase`](event-purchase.md) イベントの重複を排除する場合は、代わりに [`purchaseID`](../purchaseid.md) 変数を使用します。

## Web SDK を使用したイベント ID の使用

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md)&#x200B;を使用する場合、イベントのシリアル化では、目的のイベントのXDM フィールド `id`が使用されます。 完全な XDM パスは、シリアル化するイベントによって異なります。

例えば、買い物かごの追加指標をシリアル化する場合は、`xdm.commerce.productListAdds.id`を目的のシリアル化値に設定します。 カスタムイベント 20をシリアル化する場合は、`xdm._experience.analytics.event1to100.event20.id`を目的のシリアル化値に設定します。

[**データオブジェクト**](/help/implement/aep-edge/data-var-mapping.md)&#x200B;を使用する場合、イベントのシリアル化では、AppMeasurement文字列構文に従って`data.__adobe.analytics.events`が使用されます。

## Adobe Analytics 拡張機能を使用したイベント ID の使用

イベント ID フィールドは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. [!UICONTROL イベント]セクションを探します。各イベントには「[!UICONTROL Event ID]」フィールドが含まれます。

有効な値は、20 バイトまでの英数字です。 20 バイトを超える値を入力すると、最初の 20 バイトに切り捨てられます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターのイベント ID の使用

イベントシリアル化は `s.events` 変数の一部です。 文字列内にコロンを使用して、各イベントに ID を割り当てます。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

イベントでシリアル化が有効になっていて、シリアル化 ID が含まれていない場合、イベントは常にカウントされます。
