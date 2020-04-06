---
title: cookieLifetime
description: AppMeasurement で作成される Cookie の有効期限を上書きします。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# cookieLifetime

AppMeasurement によって設定される Cookie の有効期限は通常 2 年です。`cookieLifetime` 変数を使用して、AppMeasurement によって設定された Cookie の有効期限を上書きします。

>[!NOTE] この変数は、個別訪問者のカウントと属性に影響を与えます。この変数を設定する場合は注意が必要です。

## Adobe Experience Platform Launch での Cookie の有効期間

Cookie の有効期間は、Adobe Analytics 拡張機能を設定する際の「[!UICONTROL Cookies]」アコーディオンのドロップダウンです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオ [!UICONTROL Cookies] ンを展開し、ドロップダウンを表 [!UICONTROL Cookie Lifetime] 示します。

このドロップダウンには、次の値が含まれます。

* **デフォルト**：Cookie は 2 年後に期限切れになります。
* **なし**：AppMeasurement は Cookie を設定しません。
* **セッション**：Cookie は、訪問者のセッションの終了時に期限切れになります。
* **秒**：Cookie は、指定された秒数が経過すると有効期限が切れます。For example, setting this dropdown to [!UICONTROL Seconds] and placing `86400` into the custom field forces cookies to expire after exactly 24 hours.

## AppMeasurement の s.cookieLifetime と Launch カスタムコードエディター

`s.cookieLifetime` 変数は、AppMeasurement によって設定される Cookie の有効期限を決定する文字列です。

* `SESSION` に設定した場合、AppMeasurement によって設定された Cookie は、ブラウザーセッションが完了した後で期限切れになります。
* `NONE` に設定した場合、AppMeasurement は Cookie の設定を試みません。
* 整数文字列に設定した場合、AppMeasurement によって設定された Cookie は、指定された秒数が経過した後で期限切れになります。

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

