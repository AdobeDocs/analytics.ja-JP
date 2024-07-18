---
title: イベントのシリアル化
description: サイト上の指標の重複を除外するのに役立ちます。
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 83%

---

# イベント ID のシリアル化

イベントのシリアル化とは、Analytics レポートに重複したイベントが追加されないようにすることです。訪問者がページを更新して指標を水増ししたくない場合、イベントの重複を排除することが重要です。

>[!NOTE]
>
>データソースはイベントのシリアル化または重複排除をサポートしていません。

## イベントシリアル化の設定

まず、レポートスイートの設定で、イベントの[!UICONTROL 個別イベントの記録]を[!UICONTROL イベント ID を使用]に設定する必要があります。詳しくは、『管理者ユーザーガイド』の[成功イベント](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)を参照してください。

イベント ID を使用する場合、重複除外は次のレベルで発生します。

* 各変数は、重複除外用に独自の表を使用します。例えば、`event1:ABC` と `event2:ABC` は両方ともレポートでカウントされます。
* 重複除外は、すべての訪問者に対してグローバルに実行されます。訪問者 A が `event1:ABC` を送信し、訪問者 B も `event1:ABC` を送信した場合、2 番目の訪問者 B のインスタンスは無視されます。
* 重複除外には期限がありません。訪問者が `event1:ABC` を送信して、2 年後に再度訪問し、再度 `event1:ABC` を送信した場合、2 番目のインスタンスは無視されます。

>[!TIP]
>
> [`purchase`](event-purchase.md) イベントの重複を排除する場合は、代わりに [`purchaseID`](../purchaseid.md) 変数を使用します。

## Web SDK を使用したイベント ID の使用

[**XDM オブジェクト**](/help/implement/aep-edge/xdm-var-mapping.md) を使用する場合、イベントのシリアル化には、目的のイベントの XDM フィールド `id` が使用されます。 完全な XDM パスは、シリアル化するイベントによって異なります。

例えば、買い物かごへの追加指標をシリアル化したい場合、`xdm.commerce.productListAdds.id` を目的のシリアル化値に設定します。 カスタムイベント 20 をシリアル化したい場合、`xdm._experience.analytics.event1to100.event20` を目的のシリアル化値に設定します。

[**data オブジェクト**](/help/implement/aep-edge/data-var-mapping.md) を使用する場合、イベントのシリアル化には、AppMeasurement文字列の構文に従って `data.__adobe.analytics.events` が使用されます。

## Adobe Analytics 拡張機能を使用したイベント ID の使用

イベント ID フィールドは、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL  拡張機能 ]」ドロップダウンリストをAdobe Analyticsに設定し、「[!UICONTROL  アクションタイプ ]」を [!UICONTROL  変数を設定 ] に設定します。
6. [!UICONTROL イベント]セクションを探します。各イベントには「[!UICONTROL Event ID]」フィールドが含まれます。

有効な値は、20 バイトまでの英数字です。20 バイトを超える値を入力すると、最初の 20 バイトに切り捨てられます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターのイベント ID の使用

イベントシリアル化は `s.events` 変数の一部です。文字列内にコロンを使用して、各イベントに ID を割り当てます。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

イベントでシリアル化が有効になっていて、シリアル化 ID が含まれていない場合、イベントは常にカウントされます。
