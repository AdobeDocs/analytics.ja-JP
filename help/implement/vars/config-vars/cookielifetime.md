---
title: cookieLifetime
description: AppMeasurement で作成される Cookie の有効期限を上書きします。
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '229'
ht-degree: 100%

---

# cookieLifetime

AppMeasurement によって設定される Cookie の有効期限は通常 2 年です。`cookieLifetime` 変数を使用して、AppMeasurement によって設定された Cookie の有効期限を上書きします。

>[!NOTE]
>
> この変数は、ユニーク訪問者数と属性に影響を与えます。この変数を設定する場合は注意が必要です。

## Adobe Experience Platform Launch での Cookie の有効期間

Cookie の有効期間は、Adobe Analytics 拡張機能を設定する際の「[!UICONTROL Cookies]」アコーディオンのドロップダウンです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL Cookie の有効期間]」ドロップダウンが表示されます。

このドロップダウンには、次の値が含まれます。

* **デフォルト**：Cookie は 2 年後に期限切れになります。
* **なし**：AppMeasurement は Cookie を設定しません。
* **セッション**：Cookie は、訪問者のセッションの終了時に期限切れになります。
* **秒**：Cookie は、指定された秒数が経過すると有効期限が切れます。例えば、このドロップダウンを「[!UICONTROL 秒]」に設定して、`86400` カスタムフィールドに配置すると、Cookie の有効期限が 24 時間で切れます。

## AppMeasurement および Launch カスタムコードエディターの s.cookieLifetime

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
