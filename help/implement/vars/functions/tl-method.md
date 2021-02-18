---
title: tl
description: リンクトラッキングコールをアドビに送信します。
translation-type: ht
source-git-commit: 5bdd07b147d1ea5ef80336a893c02057e7bf5785
workflow-type: ht
source-wordcount: '606'
ht-degree: 100%

---


# tl

`tl()` メソッドは、Adobe Analytics の重要なコアコンポーネントです。ページで定義されているすべての Analytics 変数を取得し、それらをイメージリクエストにコンパイルして、そのデータをアドビのデータ収集サーバーに送信します。このメソッドは [`t()`](t-method.md) メソッドと同じように機能しますが、このメソッドではページビューが増分されません。完全なページ読み込みとは見なされないリンクやその他の要素を追跡する場合に便利です。

[`trackDownloadLinks`](../config-vars/trackdownloadlinks.md) または [`trackExternalLinks`](../config-vars/trackexternallinks.md) が有効な場合、AppMeasurement は自動的に `tl()` メソッドを呼び出して、ダウンロードリンクと出口リンクトラッキングデータを送信します。組織で、追跡するリンクとその動作をより詳細に制御する必要がある場合は、手動で `tl()` メソッドを呼び出すことができます。カスタムリンクは手動でのみ追跡できます。

## Adobe Experience Platform Launch でのリンクトラッキングコール

Launch には、リンクトラッキングコールを設定する専用の場所があります。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
1. 「[!UICONTROL アクション]」で「+」アイコンをクリックします。
1. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「ビーコンを送信」に設定します。
1. 「`s.tl()`」ラジオボタンをクリックします。

Launch では、オプションの引数を設定できません。

## AppMeasurement および Launch カスタムコードエディターの s.tl() メソッド

アドビにトラッキングコールを送信する場合は、`s.tl()` メソッドを呼び出します。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

### リンクオブジェクト（必須）

リンクオブジェクトの引数は、ブラウザーがページから移動するまでに最大 500 ミリ秒待機するかどうかを指定します。イメージリクエストが 500 ミリ秒以内に送信されると、ページは直ちにクリックされたリンクに移動します。

>[!NOTE]
>
> AppMeasurement は出口リンク用の [`useBeacon`](../config-vars/usebeacon.md) 変数を自動的に有効にするので、最新のブラウザーではこの引数は不要になりました。この引数は、以前のバージョンの AppMeasurement でより一般的に使用されていました。

* `this`：AppMeasurement がイメージリクエストを送信するまで、最大 500 ミリ秒待機します。デフォルト値。
* `true`：待機しない。

```JavaScript
// Include a 500ms delay with an exit link
s.tl(this,"e","Example exit link");

// Do not include a 500ms delay with an exit link
s.tl(true,"e","Example exit link");
```

### リンクタイプ (必須)

リンクタイプ引数は、リンクトラッキングコールのタイプを決定する 1 文字の文字列です。有効な値は 3 つです。

* `o`：リンクは[カスタムリンク](/help/components/dimensions/custom-link.md)です。
* `d`：リンクは [ダウンロードリンク](/help/components/dimensions/download-link.md)です。
* `e`：リンクは [出口リンク](/help/components/dimensions/exit-link.md)です。

```js
// Send a custom link
s.tl(true,"o","Example custom link");

// Send a download link
s.tl(true,"d","Example download link");

// Send an exit link
s.tl(true,"e","Example exit link");
```

### リンク名（推奨）

リンク名引数は、リンクトラッキングディメンション項目を決定する文字列です。レポートで[カスタムリンク](/help/components/dimensions/custom-link.md)、[ダウンロードリンク](/help/components/dimensions/download-link.md)、または[出口リンク](/help/components/dimensions/exit-link.md)を使用する場合、この文字列にはディメンション項目が含まれます。 この引数が設定されていない場合は、[linkURL](../config-vars/linkurl.md) 変数が使用されます。

```js
// When using the Download link dimension, this method call increases the occurrences metric for "Sea turtle PDF report" by 1.
s.tl(true,"d","Sea turtle PDF report");
```

### 変数の上書き（オプション）

1 回の呼び出しに対する変数の値を変更できます。詳しくは、[変数のオーバーライド](../../js/overrides.md)を参照してください。

```js
var y = new Object();
y.eVar1 = "Override value";
y.linkTrackVars = "eVar1";
s.tl(true,"o","Example custom link",y);
```

## 例と使用例

HTML リンク内で基本的なリンクトラッキングコールを直接送信します。

```HTML
<a href="example.html" onClick="s.tl(true,'o','Example link');">Click here</a>
```

JavaScript で、メソッド引数を使用した基本的なリンクトラッキングコールを作成します。

```JavaScript
s.tl(true,"o","Example link");
```

### カスタム関数内でリンクトラッキングコールを実行します

ページやリンクされている JavaScript ファイルで定義されている、自己完結型の JavaScript 関数にリンクトラッキングコードを統合できます。次に、各リンクの onClick 関数で呼び出しをおこなうことができます。JavaScript ファイルで次の設定をおこないます。

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

`trackDownloadLinks` または `trackExternalLinks` が有効な場合、正しいフィルターが一致すると、AppMeasurement は自動的にリンクトラッキングコールをおこないます。これらのリンククリックに対して `s.tl()` を手動でも呼び出すと、重複したデータをアドビに送信する場合があります。重複したデータは、レポート数を水増しし、正確性を低下させます。

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
