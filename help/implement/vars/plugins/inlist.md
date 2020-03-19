---
title: inList
description: 値が別の文字区切り値に含まれているかどうかを確認します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：inList

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `inList` ラグインを使用すると、区切り文字付きの文字列またはJavaScript配列オブジェクト内に値が既に存在するかどうかを確認できます。 その他のプラグインの中には、動作するプラグイ `inList` ンに依存するものもあります。 このプラグインは、部分的な文字列と一致しないJavaScriptメソッドに `indexOf()` 対して明確な利点を提供します。 例えば、このプラグインを使用してチェックを行った場 `"event2"`合、を含む文字列とは一致しません `"event25"`。 このプラグインは、区切り文字付きの文字列や配列の値を確認する必要がない場合や、独自のロジックを使用する場合には必要ありま `indexOf()` せん。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最もよく使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、ボタンをクリックしま [!UICONTROL Catalog] す。
1. 拡張機能のインストールと公 [!UICONTROL Common Analytics Plugins] 開
1. まだ設定していない場合は、「Initialize Plug-ins」というラベルの付いたルールを次の設定で作成します。
   * 条件：なし
   * イベント：コア — ライブラリ読み込み済み（ページの上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：inListの初期化
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、Adobe Analytics拡張機能の下 [!UICONTROL Configure] にあるボタンをクリックします。
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

次のコードを、Analyticsトラッキングオブジェクトのインスタンス化（を使用）後に、AppMeasurementファイルの任意の場所にコピーして貼り付 [`s_gi`](../functions/s-gi.md)けます。 導入時にコードのコメントとバージョン番号を保持すると、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `inList` ッドでは、次の引数を使用します。

* **`lv`** （必須、文字列または配列）:検索する値の区切りリストまたはJavaScript配列オブジェクト
* **`vtc`** （必須、文字列）:検索する値
* **`d`** （オプション、文字列）:引数内の個々の値を区切るために使用する区 `lv` 切り文字。 設定しない場合、デフォル`,`トはコンマ()です。
* **`cc`** （オプション、ブール値）:に設定すると、大文 `true`字と小文字が区別されるチェックが行われます。 に設定するか、省 `false` 略すると、大文字と小文字が区別されないチェックが行われます。 初期設定はで `false`す。

このメソッドを呼び出 `true` すと、一致が見つかった場合と、一致 `false` が見つからなかった場合が返されます。

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

...inlistの呼び出しでevent2とs.eventsの区切り文字付き値のいずれかが完全に一致しなかったので、条件ifステートメントがfalseになる場合

### 例3

...

```js
s.events="event22,event24";
```

...次のコードが実行されます。

```js
if(!s.inList(s.events,"event23"))
```

...inlistの呼び出しで、event23とs.eventsの区切られた値のいずれかが完全に一致しなかったので、条件ifステートメントがtrueになります（inList変数の呼び出しの最初にある「NOT」演算子に注意してください）。

### 例4

...

```js
s.events = "event22,event23";
```

...次のコードが実行されます。

```js
if(s.inList(s.events,"EVenT23","",1))
```

...条件ifステートメントがfalseになる場合。  この例は実用的ではありませんが、大文字と小文字を区別するフラグを使用する際は注意が必要です。

### 例5

...

```js
s.linkTrackVars = "events,eVar1";
```

...次のコードが実行されます。

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...条件ifステートメントがfalseになる場合。  呼び出しに渡されるd引数の値(&quot;|&quot;)は、s.linkTrackVarsの個々の値がパイプ文字で区切られていると想定しますが、実際の値はコンマで区切られています。  この場合、プラグインはs.linkTrackVarsの値全体(&quot;events,eVar1&quot;)と、検索する値(&quot;eVar1&quot;)を参照してください。

## バージョン履歴

### v2.1（2019年9月27日）

* 引数がブール値でないよ `cc` うにするオプションを追加。 例えば、は有 `1` 効なケースチェック値です。

### v2.0（2018年4月18日）

* ポイントリリース（再コンパイルされ、コードサイズが小さくなりました）。

### v1.01（2017年9月27日）

* コードの最適化によるサイズ縮小

### v1.0 (2009)

* 初回リリース。


