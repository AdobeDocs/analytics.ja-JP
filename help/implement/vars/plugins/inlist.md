---
title: inList
description: 値が別の文字区切り値に含まれているかどうかを確認します。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobeプラグイン：inList

> [!IMPORTANT] このプラグインは、Adobe Analyticsを使用してより多くの価値を得るために、アドビコンサルティングから提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `inList` ラグインを使用すると、区切り文字列またはJavaScript配列オブジェクト内に値が既に存在するかどうかを確認できます。 その他のプラグインの中には、動作するプラグイ `inList` ンに依存するものもあります。 このプラグインは、部分的な文字列と一致しないJavaScriptメソッド `indexOf()` よりも明確な利点を提供します。 例えば、このプラグインを使用してチェックを行った場 `"event2"`合、を含む文字列とは一致しません `"event25"`。 区切り文字付きの文字列や配列の値を確認する必要がない場合や、独自のロジックを使用する場合は、このプラグインは不要 `indexOf()` です。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. プラグインを使用する起動ルールに対して、次の設定を含むアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：addProductEvarの初期化
1. ルールへの変更を保存して発行します

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張」タブ [!UICONTROL に移動し] 、Adobe Analytics拡張機能の [!UICONTROL 下にある「設定] 」ボタンをクリックします。
1. 「カスタムコー [!UICONTROL ドを使用してトラッキングを設定] 」アコーディオンを展開すると、「エディターを開く  」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

Analyticsトラッキングオブジェクトをインスタンス化した後（を使用して）、AppMeasurementファイルの任意の場所に次のコードをコピーして貼り付 `s_gi`けます。 コードのコメントとバージョン番号を実装に保持しておくと、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `inList` ッドでは、次の引数を使用します。

* **`lv`**（必須、文字列または配列）:検索する値の区切りリストまたはJavaScript配列オブジェクト
* **`vtc`**（必須、文字列）:検索する値
* **`d`**（オプション、文字列）:引数内の個々の値を区切るために使用する区切`lv`り文字。 設定されていない場合は、デフォ`,`ルトでコンマ()が使用されます。
* **`cc`**（オプション、ブール値）:に設定した場`true`合、大文字と小文字が区別されます。 に設定するか、省`false`略すると、大文字と小文字が区別されないチェックが行われます。 初期設定はで`false`す。

このメソッドを呼び出す `true` と、一致が見つかった場合と見つからな `false` かった場合に返されます。

## 呼び出しの例

### 例1

...

```js
s.events="event22,event24";
```

...次のコードが実行されます。

```js
if(s.inList(s.events,"event22"))
```

...条件ifステートメントがtrueになる

### 例2

...

```js
s.events="event22,event24";
```

...次のコードが実行されます。

```js
if(s.inList(s.events,"event2"))
```

...inlist呼び出しでevent2とs.eventsの区切り文字付き値のいずれかが完全に一致しなかったので、条件付きifステートメントがfalseになる場合

### 例3

...

```js
s.events="event22,event24";
```

...次のコードが実行されます。

```js
if(!s.inList(s.events,"event23"))
```

...inlist呼び出しは、event23とs.eventsの区切り文字付き値のいずれかとの間で完全一致を行わなかったので、条件付きifステートメントがtrueになります（inList変数呼び出しの最初にある「NOT」演算子に注意してください）。

### 例4

...

```js
s.events = "event22,event23";
```

...次のコードが実行されます。

```js
if(s.inList(s.events,"EVenT23","",1))
```

...条件ifステートメントがfalseになる。  この例は実用的ではありませんが、大文字と小文字を区別するフラグを使用する際に注意が必要であることを示しています。

### 例5

...

```js
s.linkTrackVars = "events,eVar1";
```

...次のコードが実行されます。

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...条件ifステートメントがfalseになる。  呼び出しに渡されるd引数の値(&quot;|&quot;)は、s.linkTrackVars内の個々の値がパイプ文字で区切られていると想定しますが、実際には値がコンマで区切られています。  この場合、プラグインはs.linkTrackVarsの値全体(&quot;events,eVar1&quot;)と、検索する値(例：&quot;eVar1&quot;)。

## バージョン履歴

### v2.1（2019年9月27日）

* 引数をブール値にしな `cc` いオプションを追加しました。 例えば、は有 `1` 効なケースチェック値です。

### v2.0（2018年4月18日）

* ポイントリリース（再コンパイル、コードサイズが小さい）。

### v1.01（2017年9月27日）

* コードを最適化してサイズを縮小

### v1.0 (2009)

* 初回リリース。


