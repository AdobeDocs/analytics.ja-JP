---
title: visitorNameSpace
description: cookieドメインを決定した古い変数。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorNamespace

> [!IMPORTANT] この変数は廃止されます。 代わりに、を `trackingServer` 使用します。

以前のバージョンのAdobe Analyticsでは、AppMeasurementは、訪問者のcookieが保存さ `visitorNameSpace` れるサブドメインを判断する際に `2o7.net` この変数を使用していました。  最新のブラウザーでプライバシーの慣行が増えると、サードパーティcookieの信頼性が低下します。 変数との導入に伴い、 `trackingServer` は `trackingServerSecure` 不要に `visitorNameSpace` なりました。

> [!TIP] アドビでは、サイトでファーストパーティcookieを使用することをお勧めします。 ファーストパーティcookieではこの変数は使用されません。

## Adobe Experience Platform Launchの訪問者名前空間

[!UICONTROL 訪問者名前空間] は、Adobe Analytics拡張機能を設定する際に [!UICONTROL 、Cookies] アコーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「 [!UICONTROL Cookies] 」アコーディオンを展開すると、「訪問者の名前空間  」フィールドが表示されます。

このフィールドの使用をお勧めします。 代わりに、 `trackingServer` およびを使 `trackingServerSecure` 用します。

## AppMeasurementのs.visitorNamespaceとカスタムコードエディターの起動

変数 `s.visitorNamespace` は、組織ごとの一意の値を含む文字列です。 以前のバージョンのAdobe Analyticsからダウンロードした場合、古いAppMeasurementライブラリによってこの一意の値が自動的に含まれていました。 現在のAppMeasurementライブラリは、が設定されていない限り、こ `trackingServer` の変数を `trackingServerSecure` 使用しません。

この変数が必要な場合は、組織を表す値を選択します。 この値は、ソリューションデザインドキュメント [に保存できます](../../prepare/solution-design.md)。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
