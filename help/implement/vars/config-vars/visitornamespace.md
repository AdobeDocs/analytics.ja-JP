---
title: visitorNameSpace
description: Cookie ドメインを決定した古い変数。
feature: Variables
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 100%

---

# visitorNamespace

>[!IMPORTANT]
>
> この変数は廃止されています。代わりに、[`trackingServer`](trackingserver.md) を使用してください。

以前のバージョンの Adobe Analytics では、AppMeasurement は `visitorNameSpace` 変数を使用して訪問者の Cookie が保存される `2o7.net` のサブドメインを判断していました。最新のブラウザーではプライバシー保護が強化されており、サードパーティ Cookie の信頼性が低下しています。`trackingServer` 変数と [`trackingServerSecure`](trackingserversecure.md) 変数の導入に伴い、`visitorNameSpace` は不要になりました。

>[!TIP]
>
> サイトでファーストパーティ Cookie を使用することをお勧めします。この変数はファーストパーティ Cookie では使用されません。

## Adobe Experience Platform のタグを使用した訪問者名前空間

「[!UICONTROL 訪問者名前空間]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL Cookies]」アコーディオンの下にあるフィールドです。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL Cookies]」アコーディオンを展開すると、「[!UICONTROL 訪問者名前空間]」フィールドが表示されます。

このフィールドの使用はお勧めしません。代わりに、`trackingServer` および `trackingServerSecure` を使用してください。

## AppMeasurement および カスタムコードエディターの s.visitorNamespace

`s.visitorNamespace` 変数は、組織ごとの一意の値を含む文字列です。以前のバージョンの Adobe Analytics からダウンロードした場合、古い AppMeasurement ライブラリによってこの一意の値が自動的に含まれていました。現在の AppMeasurement ライブラリでは、`trackingServer` および `trackingServerSecure` が設定されていない限り、この変数を使用しません。

この変数が必要な場合は、組織を表す値を選択します。この値は、[ソリューション設計ドキュメント](../../prepare/solution-design.md)に保存できます。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
