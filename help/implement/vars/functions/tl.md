---
title: tl
description: リンクトラッキングコールをアドビに送信します。
translation-type: tm+mt
source-git-commit: 437f19c9b4def1ceae211662ed6785db62f80ba4

---


# tl

この方 `tl` 法は、Adobe Analyticsの重要なコアコンポーネントです。 ページで定義されているすべてのAnalytics変数を取得し、それらをイメージリクエストにコンパイルして、そのデータをAdobeデータ収集サーバーに送信します。 このメソッドはメソッドと同じよ `t` うに機能しますが、このメソッドではページビューが増分されません。 完全なページ読み込みとは見なされないリンクやその他の要素を追跡する場合に便利です。

またはが有 `trackDownloadLinks` 効な場 `trackExternalLinks` 合、AppMeasurementは自動的にメソッドを呼び出して、ダウ `tl` ンロードリンクと離脱リンクトラッキングデータを送信します。 組織で、追跡するリンクとその動作をより詳細に制御する必要がある場合は、手動でメソッドを呼び出すこと `tl` ができます。 カスタムリンクは手動でのみ追跡できます。

## Adobe Experience Platform Launchでのリンクトラッキングコール

「起動」には、専用の場所でリンクトラッキングコールを設定します。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
1. 「アク [!UICONTROL ション]」で「+」アイコンをクリックします
1. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクションタイプ [!UICONTROL 」を「送信ビーコン] 」に設定します。
1. Click the `s.tl()` radio button.

「起動」では、オプションの引数を設定できません。

## s.tl()メソッド（AppMeasurementおよびカスタムコードエディターの起動）

アドビにトラ `s.tl()` ッキングコールを送信する場合は、このメソッドを呼び出します。

```js
s.tl();
```

オプションで、このメソッドは次の引数を受け取ります。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### リンクオブジェクト

リンクオブジェクト引数は、ブラウザがページから移動する前に500 msまで待機するかどうかを決定します。 イメージリクエストが 500ミリ秒よりも前に送信されると、ページは直ちにクリックされたリンクに移動します。

> [!NOTE] AppMeasurementは離脱リンクの変数を自 `useBeacon` 動的に有効にするので、最新のブラウザーではこの引数は不要になりました。 この引数は、以前のバージョンのAppMeasurementでより一般的に使用されていました。

* `this`：AppMeasurement がイメージリクエストを送信するまで、最大 500ミリ秒待機します。デフォルト値。
* `true`：待機しない。

```JavaScript
// Include a 500ms delay
s.tl(this);

// Do not include a 500ms delay
s.tl(true);
```

### リンクタイプ

リンクタイプ引数は、リンクトラッキングコールのタイプを決定する1文字の文字列です。 変数の設定と同じで `linkType` す。

```js
// Send a custom link
s.tl(true,"o");

// Send a download link
s.tl(true,"d");

// Send an exit link
s.tl(true,"e");
```

### リンク名

link name引数は、リンクトラッキングディメンション値を決定する文字列です。 変数の設定と同じで `linkName` す。

```js
s.tl(true,"d","Example download link");
```

### 変数のオーバーライド

1 回の呼び出しに対する変数の値を変更できます。詳しくは [、変数のオーバーライド](../../js/overrides.md) を参照してください。

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## 例と使用例

HTMLリンク内に基本リンクトラッキングコールを直接送信します。

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

JavaScriptを使用して、基本的なリンクトラッキングコールを行います。

```JavaScript
s.tl(true,"o","Example Link");
```

### カスタム関数内でのリンクトラッキングコールの実行

ページやリンクされている JavaScript ファイルで定義されている、自己完結型の JavaScript 関数にリンクトラッキングコードを統合できます。次に、各リンクの onClick 関数で呼び出しをおこなうことができます。JavaScriptファイルで次の設定を行います。

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

### 重複リンクの追跡を避ける

またはが有 `trackDownloadLinks` 効な場 `trackExternalLinks` 合、正しいフィルターが一致すると、AppMeasurementは自動的にリンクトラッキングコールを行います。 また、これらのリンクのクリ `s.tl()` ックを手動で呼び出す場合は、重複したデータをアドビに送信できます。 重複したデータは、レポート番号を水増ししし、正確性を低下させます。

例えば、次の関数は、同じリンククリック（手動および自動ダウンロードリンク）に対して2つのリンクトラッキングコールを送信します。

```JavaScript
function trackDownload(obj) {
  s.tl(obj,"d","Example PDF download");
}
```

次の変更された関数を使用すると、リンクトラッキングコールの重複を防ぐことができます。 まず、リンクオブジェクトが存在するかどうかを確認し、リンクオブジェクトが空の文字列の場合にのみ手動のリンクトラッキングコールを送信します。

```JavaScript
function linkCode(obj) {
  var lt = obj.href != null ? s.lt(obj.href) : "";
  if (lt=="") {
    s.tl(obj,"d","Example PDF download");
  }
}
```
