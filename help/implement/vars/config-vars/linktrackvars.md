---
title: linkTrackVars
description: リンクトラッキングイメージリクエストに含める変数を指定します。
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
TQID: https://experienceleague.adobe.com/B3So-VtGCz2klaFJT2a1zA3-AzSPaM9R-0jafXNsrVE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 344
ht-degree: 60%

---

# linkTrackVars

一部の実装では、すべての変数をすべてのリンクトラッキングイメージリクエストに含めたくない場合があります。 `linkTrackVars` 変数と [`linkTrackEvents`](linktrackevents.md) 変数を使用して、[`tl()`](../functions/tl-method.md) の呼び出しにディメンションと指標を選択的に含めます。

この変数は、ページビュー呼び出し（[`t()`](../functions/t-method.md) メソッド）には使用されません。

## Web SDKを使用して、XDM イベントに含める変数を決定します

Web SDKでは、リンクトラッキング呼び出しの特定のフィールドは除外されません。 ただし、`onBeforeEventSend` コールバックを使用して、データをAdobeに送信する前に、目的のフィールドをクリアまたは設定できます。 詳しくは、Web SDK ドキュメントの「[&#x200B; グローバルにイベントを変更する](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=ja#modifying-events-globally)」を参照してください。

## Adobe Analytics拡張機能を使用したリンクトラッキング呼び出しの変数

この変数は、インターフェイスで設定された変数に基づいてバックエンドに自動的に入力されるので、常にAdobe Analytics拡張機能を使用した実装で設定されます。

>[!IMPORTANT]
>
>カスタムコードエディターを使用して変数を設定する場合は、カスタムコードも使用して`linkTrackVars`に変数を含める必要があります。

## AppMeasurementのs.linkTrackVarsとAnalytics拡張機能のカスタムコードエディター

`s.linkTrackVars` 変数は、リンクトラッキングイメージリクエスト（`tl()` メソッド）に含める変数のコンマ区切りリストを含む文字列です。 リンクトラッキングヒットにディメンションを含めるには、次の両方の条件を満たす必要があります。

* 目的の変数値を設定します。 例：`s.eVar1 = "Example value";`。
* 目的の変数を `linkTrackVars` 変数に設定します。 例：`s.linkTrackVars = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

この変数のデフォルト値は空の文字列です。 ただし、Code Manager では、この変数が `"None"` に設定されている AppMeasurement コードを提供しています。 有効な値は、ディメンションを入力するページレベルの変数です。

* この変数を定義しない場合、または空の文字列に設定した場合、*すべての*&#x200B;変数がリンクトラッキングイメージリクエストに含まれます。
* この変数を `"None"` に設定した場合、リンクトラッキングイメージリクエストには変数が含まれ&#x200B;*ません*。

>[!TIP]
>
>この変数で変数を指定する場合は、Analytics オブジェクト識別子（`s.`）を使用しないでください。 例えば、`s.linkTrackVars = "eVar1";` は正しいですが、`s.linkTrackVars = "s.eVar1";` は正しくありません。

## 例

次のリンクトラッキング関数は、アドビに送信されるイメージリクエストに `eVar1` のみを含みます（`eVar2` は含みません）。

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
