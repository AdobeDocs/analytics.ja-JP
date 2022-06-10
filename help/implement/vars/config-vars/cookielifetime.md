---
title: cookieLifetime
description: AppMeasurement で作成される Cookie の有効期限を上書きします。
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 80%

---

# cookieLifetime

AppMeasurement によって設定される Cookie の有効期限は通常 2 年です。`cookieLifetime` 変数を使用して、AppMeasurement によって設定された Cookie の有効期限を上書きします。

>[!NOTE]
>
> この変数は、ユニーク訪問者数と属性に影響を与えます。この変数を設定する場合は注意が必要です。

## Web SDK を使用した Cookie の有効期間

Web SDK では、設定された Cookie の有効期間をカスタマイズすることはまだできません。

## Adobe Analytics拡張機能を使用した場合の cookie の有効期間

Cookie の有効期間は、Adobe Analytics 拡張機能を設定する際の「[!UICONTROL Cookies]」アコーディオンのドロップダウンです。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL Cookie の有効期間]」ドロップダウンが表示されます。

このドロップダウンには、次の値が含まれます。

* **デフォルト**：Cookie は 2 年後に期限切れになります。
* **なし**：AppMeasurement は Cookie を設定しません。
* **セッション**：Cookie は、訪問者のセッションの終了時に期限切れになります。
* **秒**：Cookie は、指定された秒数が経過すると有効期限が切れます。例えば、このドロップダウンを「[!UICONTROL 秒]」に設定して、`86400` カスタムフィールドに配置すると、Cookie の有効期限が 24 時間で切れます。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.cookieLifetime

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
