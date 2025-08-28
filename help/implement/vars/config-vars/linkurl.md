---
title: linkURL
description: AppMeasurement がリンクトラッキングコールで使用する、自動生成されたリンク URL を上書きします。
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 7176e068dd05c5589d741f3194d2ad5d795e017d
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 37%

---

# linkURL

リンクトラッキングコールがAdobeに送信されるたびに、AppMeasurementはクリックされた URL を検出します。 この URL は、ダウンロードリンクや離脱リンクなど、リンクタイプを判断するのに役立ちます。 `linkURL` 変数は、検出された URL を上書きするために使用します。

Analysis Workspaceには、この変数についてレポートするディメンションはありません。 `page_event_var1` データフィード [ の ](/help/export/analytics-data-feed/data-feed-overview.md) 列に入力されます。 クリックされたリンクの URL をトラッキングする場合、Adobeでは [Prop](../page-vars/prop.md) などのカスタム変数を使用することをお勧めします。

## Web SDKを使用した URL のリンク

リンク URL は、次の変数にマッピングされます。

* [XDM オブジェクト ](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Data オブジェクト ](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` または `data.__adobe.analytics.pev1`

## Adobe Analytics拡張機能を使用した URL のリンク

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.linkURL

`s.linkURL` 変数は、クリックされたリンクの完全な URL を含む文字列です。 この変数は、レポートで使用できるディメンションを入力しません。

```js
s.linkURL = "https://example.com";
```

[tl()](../functions/tl-method.md) メソッドの 3 番目の引数が設定されていない場合は、代わりに `linkURL` 変数が使用されます。
