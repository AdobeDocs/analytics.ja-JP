---
description: ファイルのダウンロード数と離脱リンクは、JavaScript 版 AppMeasurement ファイルで設定されたパラメーターに基づいて、自動的に追跡することができます。
keywords: Analytics Implementation
subtopic: Link tracking
title: s.tl() 関数 - リンクトラッキング
topic: Developer and implementation
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# s.tl() 関数 - リンクトラッキング

お客様の組織で、追跡するリンクとその動作をより詳細に制御する必要がある場合は、手動リンクトラッキングをお勧めします。s.tl() 関数を使用して、目的のコンテンツを含むリンクトラッキングイメージリクエストを手動で送信します。基本的なリンクトラッキングが必要な場合は、「[設定変数](c-variables/configuration-variables.md)」の `s.trackDownloadLinks` と `s.trackExternalLinks` を参照してください。カスタムリンクは自動追跡できません。

> [!NOTE] リンクトラッキングコードは、多くの場合、サイトやレポートのニーズに特化したコードです。ビジネスニーズに基づいたこの機能の使用方法を理解できるよう、実装前のエクスペリエンスまたは実装の相談の利用をお勧めします。

## 構文と例

基本構文：

`s.tl(`**`this`**`,`**`linkType`**`,`**`linkName`**`,`**`variableOverrides`**`,`**`doneAction`**`);`

基本的な例：

```HTML
<!-- Basic HTML link example-->
<a href="example.html" onClick="s.tl(this,'o','Example link');">Click here</a>
```

```JavaScript
// Basic JavaScript link example
s.tl(this,'o','Example Link');
```

### this/true（必須）

最初の引数は、ブラウザーがページから移動するまでに最大 500 ミリ秒待機するかどうかを指定します。イメージリクエストが 500ミリ秒よりも前に送信されると、ページは直ちにクリックされたリンクに移動します。

* `this`：AppMeasurement がイメージリクエストを送信するまで、最大 500ミリ秒待機します。デフォルト値。
* `true`：待機しない。リンクがページから離れた場合、イメージリクエストが送信されない可能性があります。

遅延は、リンクがページを離れた場合にのみ必要です。

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType（必須）

2 番目の引数には、取り込むリンクのタイプに従って 3 つの有効な値があります。これにより、イメージリクエストで生成される Adobe Analytics のディメンションが決まります。

* `d`：ファイルのダウンロード数
* `e`：離脱リンク
* `o`：カスタムリンク

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName（必須）

この値には、100 文字までのカスタム値を使用できます。レポートでディメンション値を決定します。

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides（オプション）

1 回の呼び出しに対する変数の値を変更できます。doneAction 引数を使用し、変数のオーバーライドがない場合は、`null` を使用します。

### doneAction（オプション）

リンクトラッキングの完了後に実行するナビゲーションアクションを指定します。`s.useForcedLinkTracking` と `s.forcedLinkTrackingTimeout` を使用する必要があります。doneAction 変数に `navigate` という文字列を指定すると、このメソッドによって `document.location` に `linkObject` の href 属性が設定されます。また、doneAction 変数に関数を指定し、高度なカスタマイズをおこなうこともできます。

アンカーの `onClick` イベントの doneAction に値を指定する場合は、`s.tl` の呼び出し後に `false` を返すようにし、デフォルトのブラウザーナビゲーションがおこなわれないようにする必要があります。デフォルトの動作を反映し、href 属性で指定された URL に移動するには、doneAction に `navigate` の文字列を指定します。オプションとして、ナビゲーションイベントを処理するために独自の関数を指定するには、この関数を doneAction として渡すことができます。

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## リンクトラッキングとともに JavaScript 関数を使用します。

ページやリンクされている JavaScript ファイルで定義されている、自己完結型の JavaScript 関数にリンクトラッキングコードを統合できます。次に、各リンクの onClick 関数で呼び出しをおこなうことができます。

```JavaScript
// Set in AppMeasurement file or page code
function trackClickInteraction(name){
    s.linkTrackVars='eVar16,eVar17';
    s.eVar16 = name;
    s.eVar17 = s.pageName;
    s.tl(true,'o',name);
}
```

```HTML
<!-- Use wherever you want to track links -->
<a href="example.html" onClick="trackClickInteraction('Example link');">Click here</a>
```

## リンクの二重カウントの防止 {#section_9C3F73DE758F4727943439DED110543C}

リンクが自動ファイルダウンロードまたは離脱リンクの自動トラッキングで取り込まれる状況下で、リンクが二重にカウントされる可能性があります。例えば、PDF ダウンロードを自動トラッキングしている場合、`s.tl` 呼び出しを使用すると、ダウンロードが二重にカウントされます。

```JavaScript
function trackDownload(obj) {}
    s.tl(obj,'d','PDF Document');
}
```

リンクの二重カウントが発生しないようにするには、次の変更された JavaScript 関数を使用します。

```JavaScript
function linkCode(obj) {
    var lt = obj.href != null ? s.lt(obj.href) : "";
    if (lt=="") {
        s.tl(obj,'d','PDF Document');
    }
}
```
