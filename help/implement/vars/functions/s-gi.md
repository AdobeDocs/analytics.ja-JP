---
title: s_gi()
description: AppMeasurement のインスタンスを作成し、追跡します。
feature: Variables
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: ht
source-wordcount: '494'
ht-degree: 100%

---

# s_gi

`s_gi()` 関数は、レポートスイート ID で AppMeasurement のインスタンスをインスタンス化するか、検索します。AppMeasurement は作成されるすべてのインスタンスを追跡して、`s_gi()` はレポートスイートに対応する既存のインスタンスがある場合にそれを返します。インスタンスが存在しなければ、新しいインスタンスが作成されます。

## Web SDK 拡張機能を使用したトラッキングオブジェクトのインスタンス化

Web SDK 拡張機能により、トラッキングオブジェクトがインスタンス化され、管理されます。ただし、拡張機能の設定でトラッキングオブジェクト名をカスタマイズできます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Experience Platform Web SDK」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL 名前]」フィールドを目的の値に変更します。デフォルト値は `alloy` です。

## Web SDK を手動で実装したトラッキングオブジェクトのインスタンス化

次のコードでは、Web SDK を読み込み、トラッキングオブジェクトをインスタンス化します。インラインスクリプトの末尾にある文字列 `"alloy"` を目的の値に変更することで、トラッキングオブジェクト名をカスタマイズできます。

```js
<script>
  !function(n,o){o.forEach(function(o){n[o]||((n.__alloyNS=n.__alloyNS||
  []).push(o),n[o]=function(){var u=arguments;return new Promise(
  function(i,l){n[o].q.push([i,l,u])})},n[o].q=[])})}
  (window,["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.6.4/alloy.min.js" async></script>
```

詳しくは、Web SDK ドキュメントの [SDK のインストール](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja)を参照してください。

## Adobe Analytics 拡張機能を使用したトラッキングオブジェクトのインスタンス化

Analytics 拡張機能により、追跡オブジェクトがインスタンス化され、管理されます。ただし、Adobe Analytics の拡張機能を設定する際に、「[!UICONTROL ライブラリ管理]」アコーディオンでグローバルトラッキングオブジェクトを設定することもできます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL ライブラリ管理]」アコーディオンを展開し、「[!UICONTROL 私に代わってライブラリを管理する]」以外のラジオボタンを選択します。

グローバル変数テキストフィールドでは、カスタムトラッキングオブジェクトを設定できます。デフォルト値は `s` です。

## AppMeasurement の s_gi() と Analytics 拡張機能のカスタムコードエディター

`s_gi()` 関数を呼び出して、トラッキングオブジェクトをインスタンス化します。その唯一の引数には、レポートスイート ID のコンマ区切り文字列が含まれます。レポートスイート ID 引数は必須です。

>[!TIP]
>
> `s` 変数は、トラッキングオブジェクトとして使用することをお勧めします。ドキュメント、実装例およびプラグインでは `s` を使用していますが、サイト全体で一貫性がある限り、任意の変数を使用できます。

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
> 以下の節と例では、複雑な実装に関するトピックを紹介します。実装を十分にテストし、組織の[ソリューションデザインドキュメント](../../prepare/solution-design.md)に重要なカスタマイズを追跡します。

## 異なるトラッキングオブジェクトを使用した複数の実装の管理

複数のトラッキングオブジェクトをインスタンス化する場合は、様々なデータを様々なレポートスイートに送信できます。これらの 2 つのトラッキングオブジェクトは、互いに独立して動作します。

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

## s オブジェクトを上書きした後の AppMeasurement 変数の復元

一部のサードパーティツールでは、JavaScript `s` オブジェクトを使用します。誤ってサイト上の `s` オブジェクトを上書きした場合は、同じ RSID 文字列引数を使用して `s_gi` を呼び出し、上書きされたすべての変数とメソッドを復元できます。

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

同じレポートスイートで同じ `s_gi()` 関数を参照している 2 つの変数は、両方とも同じ意味で使用できます。

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
