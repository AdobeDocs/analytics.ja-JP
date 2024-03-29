---
title: cookieLifetime
description: AppMeasurement で作成される Cookie の有効期限を上書きします。
feature: Variables
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 64%

---

# cookieLifetime

AppMeasurement によって設定される Cookie の有効期限は通常 2 年です。`cookieLifetime` 変数を使用して、AppMeasurement によって設定された Cookie の有効期限を上書きします。

>[!NOTE]
>
> この変数は、ユニーク訪問者数と属性に影響を与えます。この変数を設定する場合は注意が必要です。

## Web SDK を使用した Cookie の有効期間

Web SDK では、設定された Cookie の有効期間をカスタマイズすることはまだできません。

## Adobe Analytics拡張機能を使用した場合の cookie の有効期間

cookie の有効期間は、 [!UICONTROL Cookie] アコーディオンを使用してAdobe Analytics拡張機能を設定する際に使用します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. を展開します。 [!UICONTROL Cookie] アコーディオンは、 [!UICONTROL Cookie の有効期間] 」ドロップダウンリストから選択できます。

このドロップダウンリストには、次の値が含まれます。

* **デフォルト**：Cookie は 2 年後に期限切れになります。
* **なし**：AppMeasurement は Cookie を設定しません。
* **セッション**：Cookie は、訪問者のセッションの終了時に期限切れになります。
* **秒**：Cookie は、指定された秒数が経過すると有効期限が切れます。例えば、次のドロップダウンリストを [!UICONTROL 秒] および配置 `86400` をカスタムフィールドに入力すると、cookie の有効期限が 24 時間後に強制的に切れます。

## AppMeasurementの s.cookieLifetime と Analytics 拡張機能のカスタムコードエディター

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
