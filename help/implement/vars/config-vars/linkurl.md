---
title: linkURL
description: AppMeasurement がリンクトラッキングコールで使用する、自動生成されたリンク URL を上書きします。
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 8be75c04177e97949811c17c7a87b04cce7b3de4
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 65%

---

# linkURL

リンクトラッキングコールがアドビに送信されるたびに、データ収集サーバーは URL を自動的に検出します。`linkURL` 変数は、検出された URL を上書きするために使用します。

Analysis Workspaceには、この変数についてレポートするディメンションはありません。 が設定されます `page_event_var1` 列： [データフィード](/help/export/analytics-data-feed/data-feed-overview.md).

## Web SDK を使用した URL のリンク

リンク URL は、次の変数にマッピングされます。

* [XDM オブジェクト](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [データオブジェクト](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` または `data.__adobe.analytics.pev1`

## Adobe Analytics拡張機能を使用した URL のリンク

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの s.linkURL と Analytics 拡張機能のカスタムコードエディター

`s.linkURL` 変数は、リンクがクリックされたときのブラウザー URL を含む文字列です。この変数は、レポートで使用できるディメンションを入力しません。

```js
s.linkURL = "https://example.com";
```

[tl()](../functions/tl-method.md) メソッドの 3 番目の引数が設定されていない場合は、代わりに `linkURL` 変数が使用されます。
