---
title: tl
description: リンクトラッキングコールをアドビに送信します。
feature: Variables
exl-id: 470662b2-ce07-4432-b2d5-a670fbb77771
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 76%

---

# tl

`tl()` メソッドは、Adobe Analytics の重要なコアコンポーネントです。ページで定義されているすべての Analytics 変数を取得し、それらをイメージリクエストにコンパイルして、そのデータをアドビのデータ収集サーバーに送信します。このメソッドは [`t()`](t-method.md) メソッドと同じように機能しますが、このメソッドではページビューが増分されません。完全なページ読み込みとは見なされないリンクやその他の要素を追跡する場合に便利です。

[`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) または [`trackExternalLinks`](../config-vars/trackexternallinks.md) が有効な場合、AppMeasurement は自動的に `tl()` メソッドを呼び出して、ダウンロードリンクと離脱リンクトラッキングデータを送信します。組織で、追跡するリンクとその動作をより詳細に制御する必要がある場合は、手動で `tl()` メソッドを呼び出すことができます。カスタムリンクは手動でのみ追跡できます。

## Web SDK を使用したリンクトラッキング

Web SDK は、ページビュー呼び出しとリンクトラッキング呼び出しを区別しません。両方の `sendEvent` コマンドを使用します。

XDM オブジェクトを使用し、Adobe Analyticsで特定のイベントをリンクトラッキングコールとしてカウントする場合は、XDM データに以下が含まれていることを確認します。

* リンク名：マッピング先 `xdm.web.webInteraction.name`.
* リンク URL：にマッピング済み `xdm.web.webInteraction.URL`.
* リンクタイプ：マッピング先 `xdm.web.webInteraction.type`. 有効な値は `other`（カスタムリンク）、`download`（ダウンロードリンク）、`exit`（離脱リンク）です。

```js
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webInteraction": {
        "name": "My Custom Link",
        "URL": "https://example.com",
        "type": "other"
      }
    }
  }
});
```

データオブジェクトを使用し、Adobe Analyticsで特定のイベントをリンクトラッキングコールとしてカウントする場合は、データオブジェクトに以下が含まれていることを確認してください。

* リンク名：マッピング先 `data.__adobe.analytics.linkName`.
* リンク URL：にマッピング済み `data.__adobe.analytics.linkURL`.
* リンクタイプ：マッピング先 `data.__adobe.analytics.linkType`. 有効な値は `o`（カスタムリンク）、`d`（ダウンロードリンク）、`e`（離脱リンク）です。

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "linkName": "My custom link",
        "linkURL": "https://example.com",
        "linkType": "o"
      }
    }
  }
});
```

## Adobe Analytics拡張機能を使用したリンクトラッキング

Adobe Analytics拡張機能には、リンクトラッキングコールを設定するための専用の場所があります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
1. の下 [!UICONTROL アクション]、目的のアクションをクリックするか、 **&#39;+&#39;** アイコンをクリックしてアクションを追加します。
1. を設定します。 [!UICONTROL 拡張] ドロップダウンリスト **[!UICONTROL Adobe Analytics]**、および [!UICONTROL アクションタイプ] から **[!UICONTROL ビーコンを送信]**.
1. 「`s.tl()`」ラジオボタンをクリックします。

Analytics 拡張機能では、オプションの引数を設定できません。

## AppMeasurementの s.tl() メソッドと Analytics 拡張機能のカスタムコードエディター

アドビにトラッキングコールを送信する場合は、`s.tl()` メソッドを呼び出します。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### リンクオブジェクト（必須）

リンクオブジェクトの引数は、ブラウザーがページから移動するまでに最大 500 ミリ秒待機するかどうかを指定します。イメージリクエストが 500 ミリ秒以内に送信されると、ページは直ちにクリックされたリンクに移動します。

>[!NOTE]
>
> AppMeasurement は離脱リンク用の [`useBeacon`](../config-vars/usebeacon.md) 変数を自動的に有効にするので、最新のブラウザーではこの引数は不要になりました。この引数は、以前のバージョンの AppMeasurement でより一般的に使用されていました。

* `this`：AppMeasurement がイメージリクエストを送信するまで、最大 500 ミリ秒待機します。デフォルト値。
* `true`：待機しない。

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### リンクタイプ（必須）

リンクタイプ引数は、リンクトラッキングコールのタイプを決定する 1 文字の文字列です。有効な値は 3 つです。

* `o`：リンクは[カスタムリンク](/help/components/dimensions/custom-link.md)です。
* `d`：リンクは [ダウンロードリンク](/help/components/dimensions/download-link.md)です。
* `e`：リンクは [離脱リンク](/help/components/dimensions/exit-link.md)です。

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### リンク名（推奨）

リンク名引数は、リンクトラッキングディメンション項目を決定する文字列です。レポートで[カスタムリンク](/help/components/dimensions/custom-link.md)、[ダウンロードリンク](/help/components/dimensions/download-link.md)、または[離脱リンク](/help/components/dimensions/exit-link.md)を使用する場合、この文字列にはディメンション項目が含まれます。この引数が設定されていない場合は、[linkURL](../config-vars/linkurl.md) 変数が使用されます。

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### 変数のオーバーライド（任意）

1 回の呼び出しに対する変数の値を変更できます。詳しくは、[変数のオーバーライド](../../js/overrides.md)を参照してください。

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## サンプルと使用例

HTML リンク内で基本的なリンクトラッキングコールを直接送信します。

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

JavaScript で、メソッド引数を使用した基本的なリンクトラッキングコールを作成します。

```JavaScript
s.tl(true,"o","Example link");
```

### カスタム関数内でリンクトラッキングコールを実行します

ページやリンクされている JavaScript ファイルで定義されている、自己完結型の JavaScript 関数にリンクトラッキングコードを統合できます。次に、各リンクの onClick 関数で呼び出しを行うことができます。JavaScript ファイルで次の設定を行います。

```JavaScript
function trackClickInteraction(name){
  s.linkTrackVars = "eVar1,eVar2";
  s.eVar1 = name;
  s.eVar2 = s.pageName;
  s.tl(true,"o",name);
}
```

この関数は、特定のリンクを追跡する必要が生じたときに呼び出すことができます。

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

### 重複リンクの追跡を避けます

`trackDownloadLinks` または `trackExternalLinks` が有効な場合、正しいフィルターが一致すると、AppMeasurement は自動的にリンクトラッキングコールを行います。これらのリンククリックに対して `s.tl()` を手動でも呼び出すと、重複したデータをアドビに送信する場合があります。重複したデータは、レポート数を水増しし、正確性を低下させます。

例えば、次の関数は、同じリンククリックに対して 2 つのリンクトラッキングコール（手動および自動ダウンロードリンク）を送信します。

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

次の変更された関数を使用すると、リンクトラッキングコールの重複を防ぐことができます。まず、リンクオブジェクトが存在するかどうかを確認し、リンクオブジェクトが空の文字列の場合にのみ手動のリンクトラッキングコールを送信します。

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
