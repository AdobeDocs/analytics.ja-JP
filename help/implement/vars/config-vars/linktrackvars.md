---
title: linkTrackVars
description: リンクトラッキングイメージリクエストに含める変数を指定します。
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 62%

---

# linkTrackVars

一部の実装では、すべての変数をすべてのリンクトラッキングイメージリクエストに含めたくない場合があります。`linkTrackVars` 変数と [`linkTrackEvents`](linktrackevents.md) 変数を使用して、[`tl()`](../functions/tl-method.md) の呼び出しにディメンションと指標を選択的に含めます。

この変数は、ページビュー呼び出し（[`t()`](../functions/t-method.md) メソッド）には使用されません。

## Web SDKを使用して、XDM イベントに含める変数を決定します

Web SDKは、リンクトラッキングコールの特定のフィールドを除外しません。 ただし、`onBeforeEventSend` コールバックを使用して、データがAdobeに送信される前に目的のフィールドをクリアまたは設定できます。 詳しくは、Web SDK ドキュメントの [&#x200B; イベントのグローバルな変更 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=ja#modifying-events-globally) を参照してください。

## Adobe Analytics拡張機能を使用したリンクトラッキング呼び出しの変数

この変数は、インターフェイスで設定された変数に基づいてバックエンドで自動入力されるので、Adobe Analytics拡張機能を使用した実装では常に設定されます。

>[!IMPORTANT]
>
>カスタムコードエディターを使用して変数を設定する場合は、カスタムコードを使用して `linkTrackVars` にも変数を含める必要があります。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.linkTrackVars

`s.linkTrackVars` 変数は、リンクトラッキングイメージリクエスト（`tl()` メソッド）に含める変数のコンマ区切りリストを含む文字列です。リンクトラッキングヒットにディメンションを含めるには、次の両方の条件を満たす必要があります。

* 目的の変数値を設定します。例：`s.eVar1 = "Example value";`。
* 目的の変数を `linkTrackVars` 変数に設定します。例：`s.linkTrackVars = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

この変数のデフォルト値は空の文字列です。ただし、Code Manager では、この変数が `"None"` に設定されている AppMeasurement コードを提供しています。有効な値は、ディメンションを入力するページレベルの変数です。

* この変数を定義しない場合、または空の文字列に設定した場合、*すべての*&#x200B;変数がリンクトラッキングイメージリクエストに含まれます。
* この変数を `"None"` に設定した場合、リンクトラッキングイメージリクエストには変数が含まれ&#x200B;*ません*。

>[!TIP]
>
> この変数で変数を指定する場合は、Analytics オブジェクト識別子（`s.`）を使用しないでください。例えば、`s.linkTrackVars = "eVar1";` は正しいですが、`s.linkTrackVars = "s.eVar1";` は正しくありません。

## 例

次のリンクトラッキング関数は、アドビに送信されるイメージリクエストに `eVar1` のみを含みます（`eVar2` は含みません）。

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
