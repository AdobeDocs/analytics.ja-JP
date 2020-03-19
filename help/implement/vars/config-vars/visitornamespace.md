---
title: visitorNameSpace
description: cookieドメインを決定した古い変数。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# visitorNamespace

> [!IMPORTANT] この変数は廃止されます。 代わりに、を [`trackingServer`](trackingserver.md) 使用します。

以前のバージョンのAdobe Analyticsでは、AppMeasurementは、訪問者のcookieが `visitorNameSpace` 保存されるサブドメインを特定するのに `2o7.net` 役立つ変数を使用していました。 最新のブラウザーでプライバシーの慣行が増えると、サードパーティcookieの信頼性が低下します。 と変数の導入により、 `trackingServer` は [`trackingServerSecure`](trackingserversecure.md) 不要に `visitorNameSpace` なりました。

> [!TIP] アドビでは、ファーストパーティcookieをサイトで使用することをお勧めします。 ファーストパーティCookieでは、この変数は使用されません。

## Adobe Experience Platform Launchの訪問者名前空間

[!UICONTROL Visitor Namespace] は、Adobe Analytics拡張を設定する際に、ア [!UICONTROL Cookies] コーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオ [!UICONTROL Cookies] ンを展開すると、フィールドが表示 [!UICONTROL Visitor Namespace] されます。

このフィールドの使用を避けることをお勧めします。 代わりに、 `trackingServer` およびを使 `trackingServerSecure` 用します。

## AppMeasurementのs.visitorNamespaceとカスタムコードエディターの起動

変数 `s.visitorNamespace` は、組織ごとに一意の値を含む文字列です。 以前のバージョンのAdobe Analyticsからダウンロードした場合、古いAppMeasurementライブラリによってこの一意の値が自動的に含まれていました。 現在のAppMeasurementライブラリは、が設定されていない限り、こ `trackingServer` の変数を `trackingServerSecure` 使用しません。

組織でこの変数が必要な場合は、組織を表す値を選択します。 この値は、ソリューションデザインドキュメ [ントに保存できます](../../prepare/solution-design.md)。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
