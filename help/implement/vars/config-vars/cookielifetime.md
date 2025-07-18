---
title: cookieLifetime
description: AppMeasurement で作成される Cookie の有効期限を上書きします。
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 64%

---

# cookieLifetime

AppMeasurement によって設定される Cookie の有効期限は通常 2 年です。`cookieLifetime` 変数を使用して、AppMeasurement によって設定された Cookie の有効期限を上書きします。

>[!NOTE]
>
> この変数は、ユニーク訪問者数と属性に影響を与えます。この変数を設定する場合は注意が必要です。

## Web SDKを使用した Cookie の有効期間

Web SDKは、設定された Cookie の有効期間に対するカスタマイズをまだ提供していません。

## Adobe Analytics拡張機能を使用した Cookie の有効期間

Cookie の有効期間は、Adobe Analytics拡張機能を設定する際の [!UICONTROL Cookies] アコーディオンの下にあるドロップダウンリストです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL Cookie]」アコーディオンを展開すると、「[!UICONTROL Cookie の有効期間 &#x200B;]」ドロップダウンリストが表示されます。

このドロップダウンリストには、次の値が含まれます。

* **デフォルト**：Cookie は 2 年後に期限切れになります。
* **なし**：AppMeasurement は Cookie を設定しません。
* **セッション**：Cookie は、訪問者のセッションの終了時に期限切れになります。
* **秒**：Cookie は、指定された秒数が経過すると有効期限が切れます。例えば、このドロップダウンリストを [!UICONTROL &#x200B; 秒 &#x200B;] に設定し、カスタムフィールドに `86400` を入力すると、Cookie は正確に 24 時間後に期限切れになります。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.cookieLifetime

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
