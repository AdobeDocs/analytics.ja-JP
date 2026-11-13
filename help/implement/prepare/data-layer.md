---
title: データレイヤーの作成
description: データ層がAnalyticsの実装をどのようにサポートしているか、AdobeがAdobe Client Data Layerを推奨する理由、および各実装方法でデータ層の値を読み取る方法について説明します。
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/JmxM3-AVA5--7Xt4kuES35KFtYbicdGO9JZXsygzuuE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7151dca7425bfb99271db71a3132485f85941a5e
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 7%
---
# データレイヤーの作成

データ層とは、ページ名、商品詳細、注文IDなど、Adobe Analyticsを使用して収集したデータをサイト上に公開するJavaScriptの構造のことです。 サイトコードはデータレイヤーに書き込まれ、実装はそれから読み取ってAnalytics変数を設定します。 実装はページのHTMLに依存しないため、データ収集に影響を与えることなく、サイトを再設計できます。

## 前提条件

[ ソリューション デザイン ドキュメントを作成](solution-design.md)：組織がトラッキング要件に合わせて調整することが重要です。 組織の開発チームに連絡する前に、ソリューションデザインドキュメントの準備が整っていることを確認します。 ソリューションの設計に必要なデータによって、データレイヤーに含まれるデータが決まります。

## データレイヤーの仕様の選択 {#specifications}

Adobeでは、新しい実装または再構築された実装に対して、[Adobe Client Data Layer](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview) （ACDL）をお勧めします。 ACDLは、データとイベントをグローバル `adobeDataLayer`配列にプッシュする標準的な方法をサイトに提供するオープンソースのJavaScript ライブラリです。 タグ、Web SDK、AppMeasurementはすべて、タグから読み取ることができ、Adobe Experience Managerコアコンポーネントは、タグに自動的に入力できます。

組織は、グローバル `digitalData` オブジェクトにデータを保存する[Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) （CEDDL）やカスタム仕様など、その他の仕様を自由に使用できます。 最も重要なことは、組織がニーズを満たす仕様に沿っていることです。

次の表は、ACDLとCEDDLなどのオブジェクトベースのデータレイヤーを比較したものです。

| | Adobe Client Data Layer （`adobeDataLayer`） | CEDDL （`digitalData`）などのオブジェクト ベースのデータ レイヤー |
| --- | --- | --- |
| サイトコードによるデータの書き込み方法 | プッシュオブジェクト：`adobeDataLayer.push({ page: { name: "Home" } })` | プロパティを設定：`digitalData.page.pageInfo.pageName = "Home"` |
| 実装での値の読み込み方法 | `adobeDataLayer.getState("page.name")`、または&#x200B;**データレイヤーの計算済みステート** データ要素（Adobe Client Data Layer タグ拡張機能から） | `digitalData.page.pageInfo.pageName`、またはコアタグ拡張機能の&#x200B;**JavaScript Variable** data element |
| データの準備が整ったことを実装が把握する方法 | サイトコードが`{ event: "page view" }`などのイベントをプッシュし、実装がそれをリッスンします。 また、リスナーは、追加される前にプッシュされたイベントに対しても実行されます。 | 直接呼び出しルールを使用するなどして、サイトコードの入力が完了した後、実装でオブジェクトを読み取る必要があります。 |

## データレイヤーの例 {#example}

ACDLには特定のデータ構造は必要ありません。 ソリューション設計ドキュメントを中心に構造を設計し、データレイヤーへの書き込みやデータレイヤーからの読み取り用に文書化します。 このガイドの例では、次の構造を使用しています。

ページが読み込まれると、サイトコードによってページのデータとページビューイベントがプッシュされます。

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push({
  event: "page view",
  page: {
    name: "Home",
    section: "Products",
    url: "https://example.com/products",
    referrer: "https://example.com/"
  }
});
```

訪問者が購入を完了すると、サイトコードによって注文の詳細と購入イベントがプッシュされます。

```js
window.adobeDataLayer.push({
  event: "purchase",
  transaction: { id: "ABC123" },
  products: [
    { name: "Example product", category: "Example category", quantity: 1, price: 25 }
  ]
});
```

ACDLは、すべてのプッシュを、実装で読み込む計算状態と呼ばれる単一のオブジェクトにマージします。 イベントオブジェクトは、実装に読み込むタイミングを指示します。 [ データと計算状態](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/computed-state)および[ イベント ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/concepts/events)を参照してください。

## ワークフロー {#workflow}

データレイヤーを使用して Adobe Analytics を実装する場合は、通常次の手順に従います。

1. **サイト開発チームと協力してデータレイヤーを実装する**: サイト開発チームは、主に、データレイヤーに正しい値が含まれていることを確認する責任があります。 このページをサイト開発チームと共に確認し、チーム間で期待値が一致することを確認します。 [Adobe Client Data Layerのインストール ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install)を参照してください。
1. **ブラウザーコンソールを使用してデータレイヤーを検証する**: ブラウザーの開発者コンソールを開きます。このコンソールは、`F12` キーを使用してほとんどのブラウザーで実行できます。 `adobeDataLayer.getState()`を実行して計算状態を確認するか、`adobeDataLayer.getState("page.name")`を実行して単一の値を確認します。 [ インストールの確認](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/install#verify)を参照してください。
1. **データレイヤーをAdobe Analyticsに接続**：この手順は、組織の実装方法によって異なります。 [ データレイヤーをAdobe Analytics](#connect)に接続するを参照してください。

## データレイヤーとAdobe Analyticsの連携 {#connect}

次の表に、各実装メソッドがAdobe Client Data Layerからどのように読み取るかを示します。

| 実装方法 | データレイヤーの読み方 | 詳細情報 |
| --- | --- | --- |
| Web SDK タグ拡張機能 | Adobe Client Data Layer拡張機能から&#x200B;**データレイヤープッシュ** トリガーを使用したイベントルール。 データ層の値をXDM フィールドまたは`data` オブジェクトにマッピングし、Web SDK **変数を更新** アクションを実行してから、**イベントを送信** アクションを実行してデータ層の値を送信します。 | [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk)、[XDM オブジェクトフィールドマッピング ](../aep-edge/xdm-var-mapping.md)および[ データオブジェクトフィールドマッピング ](../aep-edge/data-var-mapping.md)を使用して、Adobe Client Data Layer データを送信します |
| Web SDK JavaScriptライブラリ | `addEventListener()`でデータレイヤーイベントをリッスンし、`sendEvent`を呼び出すときにデータレイヤーからXDMまたは`data` フィールドを設定します。 | [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/web-sdk)、[XDM オブジェクトフィールドマッピング ](../aep-edge/xdm-var-mapping.md)および[ データオブジェクトフィールドマッピング ](../aep-edge/data-var-mapping.md)を使用して、Adobe Client Data Layer データを送信します |
| Analytics 拡張機能 | **データレイヤーのプッシュ** イベントを使用してルールをトリガーし、Adobe Client Data Layer拡張機能から&#x200B;**データレイヤーの計算状態** データ要素を作成します。 データ要素を&#x200B;**変数を設定** アクションでAnalytics変数に割り当ててから、**ビーコンを送信** アクションでデータを送信します。 | [ データ層オブジェクトのデータ要素へのマッピング ](../launch/layer-to-elements.md)および[ データ要素のAnalytics変数へのマッピング ](../launch/elements-to-variable.md) |
| AppMeasurement | ACDLの読み込み後に`getState()`の値を読み取り、`s.t()`を呼び出します。 | [AppMeasurementでデータレイヤーを読み取る](#appmeasurement) |

### AppMeasurementでデータレイヤーを読む {#appmeasurement}

ACDLは、ライブラリの読み込み時に`getState()` メソッドを`adobeDataLayer`配列に追加します。 ライブラリが読み込まれ、計算状態に最新のデータが含まれていることを確認するには、イベントリスナー内の値を読み取ります。

```js
window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function(dl) {
  dl.addEventListener("page view", function(event) {
    s.pageName = dl.getState("page.name");
    s.channel = dl.getState("page.section");
    s.t();
  });
});
```

リスナーは、リスナーが追加される前にプッシュされたイベントを含む、`page view` イベントごとに1回実行されます。 このガイドの変数ページ（[`pageName`](../vars/page-vars/pagename.md)など）では、`getState()`を使用して個々の値を読み取る方法を説明します。 このような例は、リスナー内や、**データレイヤーのプッシュ** イベントトリガーを含むAnalytics拡張機能ルールのカスタムコードエディターで使用できます。

単一ページアプリケーションなど、実装でページごとに複数のヒットを送信する場合は、[`clearVars()`](../vars/functions/clearvars.md)を使用して、1つのヒットの値が次のヒットに保持されないようにします。

## 次の手順

* [ データレイヤーオブジェクトをデータ要素にマッピング ](../launch/layer-to-elements.md): Adobe Experience Platform タグでサイトのデータレイヤーを使用します。
* [Adobe Client Data Layer ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/collection/acdl/overview)：すべてのACDL メソッド、イベント、ベストプラクティスについて説明します。
