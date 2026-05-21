---
title: プラグインの概要
description: サイトにコードを貼り付けて、新しい機能を導入します。
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ImzoBRU0DajPc99vRlu1698CteFNk9dOS2OZrN9DBZs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 328
ht-degree: 96%

---

# プラグインの概要

プラグインは、Analytics の実装に役立つ高度な機能を実行するコードのスニペットです。 これらのプラグインは、JavaScript ファイルの機能を拡張して、基本的な実装では利用できなかった機能を提供します。 アドビは他にも多数のプラグインを高度なソリューションの一部として提供しています。

{{plug-in}}

アドビでは、特定のプラグインをインストールする方法をいくつか提供しています。

* Adobe Analytics拡張機能を使用した「Common Analytics Plugins」拡張機能の使用
* カスタムコードエディターを使用したプラグインコードの貼り付け。
* `AppMeasurement.js` ファイルへのプラグインコードの貼り付け。

各組織には異なる実装ニーズがあるので、実装に組み込む方法を決定できます。 サイトにコードを含める際は、次の条件を満たしていることを確認してください。

1. まず、Analytics トラッキングオブジェクトをインスタンス化します（[`s_gi`](../functions/s-gi.md) を使用）。
   * タグが有効なサイトは、Adobe Analytics が読み込まれると、トラッキングオブジェクトを自動的にインスタンス化します。
   * `AppMeasurement.js` を使用した実装では、通常、JavaScript ファイルの先頭でトラッキングオブジェクトを初期化します。
2. 次に、プラグインコードを含めます。
   * 「Common Analytics Plugins」拡張機能には、プラグインを初期化できるアクション設定があります。
   * プラグインを使用しない場合は、Analytics 拡張機能の設定時にカスタムコードエディターにプラグインコードを貼り付けることができます。
   * 実装で Adobe Experience Platform のタグを使用しない場合は、トラッキングオブジェクトをインスタンス化した後、プラグインコードを `AppMeasurement.js` のどこにでも貼り付けることができます。
3. 3 番目にプラグインを呼び出します。
   * タグが有効なサイトの内部と外部の両方のすべての実装で、JavaScript を使用してプラグインを呼び出します。 プラグインのページに記載されている形式を使用してプラグインを呼び出します。
4. 実装を検証し、発行します。

多くの組織では、[`doPlugins`](../functions/doplugins.md) 関数を使用してプラグインを呼び出します。 この関数は必須ではありませんが、アドビでは、関数の使用をベストプラクティスと見なしています。 イメージリクエストをコンパイルして送信する直前に AppMeasurement がこの関数を呼び出します。これは、いくつかのプラグインが他の Analytics 変数に依存しているので理想的です。
