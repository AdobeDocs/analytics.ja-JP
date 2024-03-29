---
title: linkTrackVars
description: リンクトラッキングイメージリクエストに含める変数を指定します。
feature: Variables
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 62%

---

# linkTrackVars

一部の実装では、すべての変数をすべてのリンクトラッキングイメージリクエストに含めたくない場合があります。`linkTrackVars` 変数と [`linkTrackEvents`](linktrackevents.md) 変数を使用して、[`tl()`](../functions/tl-method.md) の呼び出しにディメンションと指標を選択的に含めます。

この変数は、ページビュー呼び出し（[`t()`](../functions/t-method.md) メソッド）には使用されません。

## Web SDK を使用した XDM イベントに含める変数の決定

Web SDK は、リンクトラッキングコール用に特定のフィールドを除外しません。 ただし、 `onBeforeEventSend` データがAdobeに送信される前に、目的のフィールドをクリアまたは設定するコールバック。 詳しくは、 [イベントのグローバルな変更](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) （ Web SDK ドキュメント）を参照してください。

## Adobe Analytics拡張機能を使用したリンクトラッキングコールの変数

この変数は、インターフェイスで設定された変数に基づいて、バックエンドで自動的に設定されるので、Adobe Analytics拡張機能を使用した実装では常に設定されます。

>[!IMPORTANT]
>
>カスタムコードエディターを使用して変数を設定する場合、 `linkTrackVars` カスタムコードの使用もおこないます。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.linkTrackVars

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
