---
description: ファイルのダウンロード数と離脱リンクは、JavaScript 版 AppMeasurement ファイルで設定されたパラメーターに基づいて、自動的に追跡することができます。
keywords: Analytics の実装
seo-description: ファイルのダウンロード数と離脱リンクは、JavaScript 版 AppMeasurement ファイルで設定されたパラメーターに基づいて、自動的に追跡することができます。
seo-title: s.tl() 関数 - リンクトラッキング
solution: Analytics
subtopic: リンクトラッキング
title: s.tl() 関数 - リンクトラッキング
topic: 開発者と実装
uuid: f28f071a-8820-4f74-89cd-fd2333a21f22
translation-type: tm+mt
source-git-commit: 1ed1c6cd3fd6d29fa156cd4b2c4bdfe9120b3c61

---


# s.tl() 関数 - リンクトラッキング

組織で追跡するリンクとその動作をより詳細に制御する必要がある場合は、手動リンクトラッキングをお勧めします。 s.tl()関数を使用して、目的のコンテンツを含むリンクトラッキングイメージリクエストを手動で送信します。 基本的なリンクトラッキングが必要な場合は、「設定変数」の `s.trackDownloadLinks` とを参 `s.trackExitLinks` 照し [てください](c-variables/configuration-variables.md)。 カスタムリンクは自動的に追跡できません。

> [!NOTE] リンクトラッキングコードは、多くの場合、サイトやレポートのニーズに非常に特化したコードです。 ビジネスニーズに基づいてこの機能の使用方法を理解するには、事前の導入経験または導入コンサルタントをお勧めします。

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

最初の引数は、ブラウザがページから移動する前に500 msまで待機するかどうかを指定します。 イメージリクエストが500 msよりも早く送信されると、ページは直ちにクリックされたリンクに移動します。

* `this`:AppMeasurementがイメージリクエストを送信するまで、最大500 ms待機します。 デフォルト値。
* `true`:待つな。 リンクがページから離れた場合、イメージリクエストが送信されない可能性があります。

遅延は、リンクがページを離れた場合にのみ必要です。

```JavaScript
// Include 500ms delay
s.tl(this,'o','Example link');

// Do not include 500ms delay
s.tl(true,'o','Example link');
```

### linkType（必須）

2番目の引数には、取り込むリンクのタイプに応じて3つの有効な値があります。 これにより、イメージリクエストが入力するAdobe Analyticsのディメンションが決まります。

* `d`: ファイルのダウンロード数
* `e`: 離脱リンク
* `o`:カスタムリンク

```JavaScript
// Populates the File Downloads dimension
s.tl(this,'d','Example link');

// Populates the Exit Links dimension
s.tl(this,'e','Example link');

// Populates the Custom Links dimension
s.tl(this,'o','Example link');
```

### linkName（必須）

この引数には、100バイトまでの任意のカスタム値を指定できます。 レポートでディメンション値を決定します。

```JavaScript
// Populates the Custom Link dimension with "Referral click to example.com"
s.tl(this,'o','Referral click to example.com');

// Populates the Download link dimension with "Last quarter performance PDF"
s.tl(this,'d','Last quarter performance PDF');
```

### variableOverrides（オプション）

1回の呼び出しで変数の値を変更できます。 doneAction引数を使用し、変数のオーバーライドがない場合は、を使用しま `null`す。

### doneAction（オプション）

リンクトラッキングの完了後に実行するナビゲーションアクションを指定します。 とを使用する必要があ `s.useForcedLinkTracking` ります `s.forcedLinkTrackingTimeout`。 The doneAction variable can be the string `navigate`, which causes the method to set `document.location` to the href attribute of `linkObject`. また、doneAction 変数に関数を指定し、高度なカスタマイズをおこなうこともできます。

アンカーの イベントの `onClick``false`doneAction に値を指定する場合は、`s.tl` の呼び出し後に を返すようにし、デフォルトのブラウザーナビゲーションがおこなわれないようにする必要があります。To mirror the default behavior and follow the URL specified by the href attribute, provide a string of `navigate` as the doneAction. オプションとして、ナビゲーションイベントを処理するために独自の関数を指定するには、この関数を doneAction として渡すことができます。

```JavaScript
s.tl(this,'e','Example link',null,'navigate');return false;
```

## リンクトラッキングでのJavaScript関数の使用

リンクトラッキングコードは、ページ上またはリンクされたJavaScriptファイル内で定義された独立したJavaScript関数に統合できます。 その後、各リンクのonClick関数で呼び出しを行うことができます。

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

リンクが自動ファイルダウンロードまたは離脱リンクトラッキングで取り込まれる状況では、リンクが2倍にカウントされる可能性があります。 For example, if you are tracking PDF downloads automatically, an `s.tl` call results in a duplicate download count:

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
