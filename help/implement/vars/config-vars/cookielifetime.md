---
title: cookieLifetime
description: AppMeasurementで作成されるcookieの有効期限を上書きします。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

AppMeasurementによって設定されるcookieの有効期限は通常2年です。 この変数を使 `cookieLifetime` 用して、AppMeasurementによって設定されたcookieの有効期限を上書きします。

> [!NOTE] この変数は、個別訪問者のカウントとアトリビューションに影響を与えます。 この変数を設定する場合は注意が必要です。

## Adobe Experience Platform LaunchでのCookieの有効期間

Cookieの有効期間は、Adobe Analytics拡張機能を設定する際の「 [!UICONTROL Cookies] 」アコーディオンのドロップダウンです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「 [!UICONTROL Cookies] 」アコーディオンを展開すると、「 [!UICONTROL Cookieの有効期間] 」ドロップダウンが表示されます。

このドロップダウンには、次の値が含まれます。

* **デフォルト**:cookieは2年後に期限切れになります。
* **なし**:AppMeasurementはcookieを設定しません。
* **セッション**:cookieは、訪問者のセッションの終了時に期限切れになります。
* **秒**:Cookieは、指定された秒数が経過すると有効期限が切れます。 例えば、このドロップダウンを「秒」に設定し [!UICONTROL て] 、カス `86400` タムフィールドに配置すると、cookieの有効期限が24時間で切れます。

## AppMeasurementのs.cookieLifetimeとカスタムコードエディターの起動

変数 `s.cookieLifetime` は、AppMeasurementによって設定されるcookieの有効期限を決定する文字列です。

* に設定した場合、AppMeasurementによ `SESSION`って設定されたcookieは、ブラウザーセッションが完了した後で期限切れになります。
* に設定した場 `NONE`合、AppMeasurementはcookieの設定を試みません。
* 整数文字列に設定した場合、AppMeasurementによって設定されたcookieは、指定された秒数が経過した後で期限切れになります。

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

