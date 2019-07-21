---
description: カスタムイベントを使用して、追跡する成功のタイプを定義できます。
keywords: Analyticsの導入;カスタムイベント
seo-description: カスタムイベントを使用して、追跡する成功のタイプを定義できます。
seo-title: カスタムイベントとは何ですか。
solution: Analytics
title: カスタムイベントとは何ですか。
topic: 開発者と導入
uuid: 8e78ba04-9b4c-4566-980c- c24dd9d82236
translation-type: tm+mt
source-git-commit: d7056c233e784a073c75c55f396ff43c9e0d1c71

---


# カスタムイベントとは何ですか。

カスタムイベントを使用して、追跡する成功のタイプを定義できます。

[!UICONTROL 事前定義された]イベントに似ていますが、[!UICONTROL カスタム]イベントでは独自の成功指標を定義できます。For example, if you have a newsletter, your success event could be _Registration_. Clearly, _Registration_ is not part of the [!UICONTROL predefined] events. [!UICONTROL カスタム]イベントを使用することによって、ニュースレターに登録した訪問者の数を追跡できます。[!UICONTROL カスタム]イベントの標準の構文を次に示します。

```js
s.events="event3"
```

このコードは、_events_ 変数を使用します。If you do not modify the event name in the interface, _event3_ would display in the interface.

デフォルトでは、成功イベントはカウンター&#x200B;__&#x200B;イベントとして設定されます。カウンターイベントは、成功イベントが設定された回数をカウントします。成功イベントによっては、イベントをカスタム金額で増分する必要があります。These events can be set either as _numeric_ events or _currency_ events. イベントタイプは管理コンソールで変更できます。
