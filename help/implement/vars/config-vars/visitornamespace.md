---
title: visitorNameSpace
description: （退職済み）サードパーティのCookie ドメインの決定に役立ちました。
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/RHVRufQsrgYigyj0n348-xAZqrDyvpiV83G7fhpo5Q0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 89%

---

# visitorNamespace

>[!IMPORTANT]
>
>この変数は廃止されています。 代わりに、[`trackingServer`](trackingserver.md) を使用してください。

以前のバージョンの Adobe Analytics では、AppMeasurement は `visitorNameSpace` 変数を使用して訪問者の Cookie が保存される `2o7.net` のサブドメインを判断していました。 最新のブラウザーではプライバシー保護が強化されており、サードパーティ Cookie の信頼性が低下しています。 `trackingServer` 変数と [`trackingServerSecure`](trackingserversecure.md) 変数の導入に伴い、`visitorNameSpace` は不要になりました。

>[!TIP]
>
>サイトでファーストパーティ Cookie を使用することをお勧めします。 この変数はファーストパーティ Cookie では使用されません。

## Adobe Analytics拡張機能を使用した訪問者名前空間

「[!UICONTROL 訪問者名前空間]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL 訪問者名前空間]」フィールドが表示されます。

このフィールドの使用はお勧めしません。 代わりに、`trackingServer` および `trackingServerSecure` を使用してください。

## AppMeasurementのs.visitorNamespaceとAnalytics拡張機能のカスタムコードエディター

`s.visitorNamespace` 変数は、組織ごとの一意の値を含む文字列です。 以前のバージョンの Adobe Analytics からダウンロードした場合、古い AppMeasurement ライブラリによってこの一意の値が自動的に含まれていました。 現在の AppMeasurement ライブラリでは、`trackingServer` および `trackingServerSecure` が設定されていない限り、この変数を使用しません。

この変数が必要な場合は、組織を表す値を選択します。 この値は、[ソリューション設計ドキュメント](../../prepare/solution-design.md)に保存できます。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
