---
title: cookieLifetime
description: AppMeasurement で作成される Cookie の有効期限を上書きします。
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/Vnia0RzQf6S5-gbgwIlM0WOiSgm2ZOzL24pvIKNgMl4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 63%

---

# cookieLifetime

AppMeasurement によって設定される Cookie の有効期限は通常 2 年です。 `cookieLifetime` 変数を使用して、AppMeasurement によって設定された Cookie の有効期限を上書きします。

>[!NOTE]
>
>この変数は、ユニーク訪問者数と属性に影響を与えます。 この変数を設定する場合は注意が必要です。

## Web SDKを使用したCookieの有効期間

Web SDKでは、設定したCookieの有効期間に対するカスタマイズはまだ提供されていません。

## Adobe Analytics拡張機能を使用したCookieの有効期間

Cookie Lifetimeは、Adobe Analytics拡張機能を設定する際の[!UICONTROL Cookie] アコーディオンの下にあるドロップダウンリストです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL Cookie]」アコーディオンを展開すると、「[!UICONTROL Cookie Lifetime]」ドロップダウンリストが表示されます。

このドロップダウンリストには、次の値が含まれます。

* **デフォルト**：Cookie は 2 年後に期限切れになります。
* **なし**：AppMeasurement は Cookie を設定しません。
* **セッション**：Cookie は、訪問者のセッションの終了時に期限切れになります。
* **秒**：Cookie は、指定された秒数が経過すると有効期限が切れます。 例えば、このドロップダウンリストを[!UICONTROL 秒]に設定し、`86400`をカスタムフィールドに配置すると、Cookieは正確に24時間後に期限切れになります。

## AppMeasurementのs.cookieLifetimeとAnalytics拡張機能のカスタムコードエディター

`s.cookieLifetime` 変数は、AppMeasurement によって設定される Cookie の有効期限を決定する文字列です。

* `SESSION` に設定した場合、AppMeasurement によって設定された Cookie は、ブラウザーセッションが完了した後で期限切れになります。
* `NONE` に設定した場合、AppMeasurement は Cookie の設定を試みません。
* 整数文字列に設定した場合、AppMeasurement によって設定された Cookie は、指定された秒数が経過した後で期限切れになります。

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";
```
