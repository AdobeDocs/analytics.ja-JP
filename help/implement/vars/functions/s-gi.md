---
title: s_gi()
description: AppMeasurementのインスタンスを作成し、追跡します。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# s_gi

この関 `s_gi()` 数は、レポートスイートIDでAppMeasurementのインスタンスをインスタンス化するか、検索します。 AppMeasurement keeps track of every instance created, and `s_gi()` returns the existing instance for a report suite if one exists. インスタンスが存在しない場合は、新しいインスタンスが作成されます。

## s_gi() in Adobe Experience Platform Launch

Analytics拡張機能により、追跡オブジェクトがインスタンス化され、管理されます。 ただし、Adobe Analyticsの拡張機能を設定する際に、ライブラリ管理アコーディ  オンでグローバルトラッキングオブジェクトを設定することもできます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. ライブラリ管 [!UICONTROL 理アコーディオンを展開し] 、「ライブラリを管理するユーザー用」以外のラ [!UICONTROL ジオボタンを選択します]。

グローバル変数テキストフィールドでは、カスタムトラッキングオブジェクトを設定できます。 Its default value is `s`.

## s_gi()（AppMeasurementおよびカスタムコードエディターの起動）

この関数を呼び出し `s_gi()` て、トラッキングオブジェクトをインスタンス化します。 その唯一の引数には、レポートスイートIDのコンマ区切り文字列が含まれます。 レポートスイートID引数は必須です。

> [!TIP] この変数は、トラッキングオブジ `s` ェクトとして使用することをお勧めします。 アドビでは、ド `s` キュメント、導入例およびプラグインを使用しています。 ただし、サイト全体で一貫性がある限り、任意の変数を使用できます。

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

> [!WARNING] 以下の節と例では、複雑な導入に関するトピックを紹介します。 導入を十分にテストし、組織のソリューションデザインドキュメント内の重要なカス [タマイズを追跡します](../../prepare/solution-design.md)。

## 異なるトラッキングオブジェクトを使用した複数の実装の管理

複数のトラッキングオブジェクトをインスタンス化する場合は、様々なデータを様々なレポートスイートに送信できます。 これらの2つのトラッキングオブジェクトは、互いに独立して動作します。

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## sオブジェクトを上書きした後にAppMeasurement変数を復元する

サードパーティのツールによっては、JavaScriptオブジェクトを使用する場合もあ `s` ります。 誤ってサイト上のオブジェクト `s` を上書きした場合は、同じRSID文字列引数を `s_gi` 使用してを呼び出し、上書きされたすべての変数とメソッドを復元できます。

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## 複数の変数を使用した同じトラッキングオブジェクトの参照

2つの変数が同じレポートスイー `s_gi()` トで同じ関数を参照している場合は、同じ方法で変数を使用できます。

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
