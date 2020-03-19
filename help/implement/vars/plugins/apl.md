---
title: apl (appendToList)
description: 複数の値をサポートする変数に値を追加します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：apl (appendToList)

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `apl` ラグインを使用すると、、、などのリスト区切りの変数に新しい値を安全に [`events`](../page-vars/events/events-overview.md)追加で [`linkTrackVars`](../config-vars/linktrackvars.md)き [`list`](../page-vars/list.md)ます。

* 追加する値が変数に存在しない場合は、文字列の末尾に値が追加されます。
* 追加する値が変数に既に存在する場合、このプラグインは値を変更しません。 この機能を使用すると、実装で値の重複を回避できます。
* 追加先の変数が空の場合、プラグインは変数を新しい値に設定します。

区切り文字付きの値の文字列を含む既存の変数に新しい値を追加する場合は、このプラグインの使用をお勧めします。 このプラグインは、区切り値を含む変数に文字列を連結する場合は不要です。

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
   * アクションタイプ：APLの初期化（リストに追加）
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `apl` ッドでは、次の引数を使用します。

* **`lv`** （必須、文字列）:新しい値を追加する項目の区切り形式のリストを含む変数
* **`vta`** （必須、文字列）:引数の値に追加する新しい値のコンマ区切りリ `lv` ストです。
* **`d1`** （オプション、文字列）:引数に既に含まれている個々の値を区切るために使用される区 `lv` 切り文字。  設定しない場合、デフォル`,`トはコンマ()です。
* **`d2`** （オプション、文字列）:出力の区切り文字。 デフォルト値は、未設定の場合と `d1` 同じ値です。
* **`cc`** （オプション、ブール値）:大文字と小文字を区別するチェックが使用されるかどうかを示すフラグ。 重複チェ `true`ックでは、大文字と小文字が区別されます。 設定され `false` ているかどうかに関係なく、重複チェックでは大文字と小文字が区別されません。 初期設定はで `false`す。

このメ `apl` ソッドは、引数の値 `lv` と、その引数内の重複しない値を返し `vta` ます。

## 呼び出しの例

### 例1

...

```js
s.events = "event22,event24";
```

...次のコードが実行されます。

```js
s.events = s.apl(s.events, "event23");
```

...s.eventsの最終的な値は次のとおりです。

```js
s.events = "event22,event24,event23";
```

### 例2

...

```js
s.events = "event22,event23";
```

...次のコードが実行されます。

```js
s.events = s.apl(s.events, "event23");
```

...s.eventsの最終値は、次のとおりです。

```js
s.events = "event22,event23";
```

この例では、s.eventsに既に「event23」が含まれているので、apl呼び出しでs.eventsが変更されていません。

### 例3

...

```js
s.events = ""; //blank value
```

...次のコードが実行されます。

```js
s.events = s.apl(s.events, "event23");
```

...s.eventsの最終値は次のようになります。

```js
s.events = "event23";
```

### 例4

...

```js
s.prop4 = "hello|people";
```

...次のコードが実行されます。

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

...s.prop4の最終値は、引き続き次のようになります。

```js
s.prop4 = "hello|people";
```

...しかし、s.eVar5の最終値は

```js
s.eVar5 = "hello|people|today";
```

プラグインが返す値は1つのみであることに注意してください。lv引数を通じて渡される変数は、必ずしも「リセット」されるわけではありません。

### 例5

...

```js
s.prop4 = "hello|people";
```

...次のコードが実行されます。

```js
s.prop4 = s.apl(s.prop4, "today");
```

...s.prop4の最終値は次のようになります。

```js
s.prop4 = "hello|people,today";
```

区切り文字は、lv引数の値とd1/d2引数の値の間で一貫性を保つようにしてください

### 例6

...

```js
s.events = "event22,event23";
```

...次のコードが実行されます。

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

...s.eventsの最終的な値は次のとおりです。

```js
s.events = "event22,event23,EVentT23";
```

この例は実用的ではありませんが、大文字と小文字を区別するフラグを使用する際は注意が必要です。

### 例7

...

```js
s.events = "event22,event23";
```

...次のコードが実行されます。

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

...s.eventsの最終的な値は次のとおりです。

```js
s.events = "event22,event23,event24,event25");
```

このプラグインは、「event23」をs.eventsに追加しません。これは、このプラグインが既にs.eventsに存在するためです。  ただし、以前はs.eventsにどちらも含まれていなかったので、event24とevent25の両方がs.eventsに追加されます。

### 例8

...

```js
s.linkTrackVars = "events,eVar1";
```

...次のコードが実行されます。

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

...s.linkTrackVarsの最終値は次のとおりです。

```js
s.linkTrackVars = "events,eVar1,campaign";
```

最後の3つの引数(このapl呼び出しの最後の&quot;,&quot;,&quot;, false)は、必ずしも必要ではありませんが、デフォルトの引数値と一致するので、&quot;何も傷つけない&quot;設定を行う必要はありません。

### 例9

...

```js
s.events = "event22,event24";
```

...次のコードが実行されます。

```js
s.apl(s.events, "event23");
```

...s.eventsの最終値は、次のとおりです。

```js
s.events = "event22,event24";
```

プラグインを（変数に戻り値を割り当てずに）単独で実行しても、lv引数を通じて渡された変数は実際には「リセット」されません。

### 例10

...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...次のコードが実行されます。

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

...s.list2の最終値は次のとおりです。

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

2つの区切り文字引数が異なるので、渡される値は最初の区切り文字引数(&quot;|&quot;)で区切られ、2番目の区切り文字引数(&quot;-&quot;)で結合されます

## バージョン履歴

### 3.2（2019年9月26日）

* 古いバージョンのプラグ `apl` インを使用する呼び出しの互換性の問題を修正しました。
* サイズを小さくするためにコンソールの警告を削除しました。
*  `inList 2.1`

### 3.1（2018年4月23日）

* `d2` 引数が設定されない場合、引数の値がデフォル `d1` トになりました。

### 3.0（2018年4月17日）

* プラグインの再分析/書き換えの完了
* 詳細なエラーチェックの追加
* 引数に `vta` 複数の値を同時に指定できるようになりました
* 戻り値の形 `d2` 式を設定する引数を追加しました。
* 引数をブール `cc` 値に変更しました。

### 2.5（2016年2月19日）

* 現在は、比較処理 `inList` にメソッドを使用します

### 2.0（2016年1月27日）

* `d` （区切り文字）引数がオプションに（デフォルトでコンマ）
* `u` （大文字と小文字の区別フラグ）引数がオプションに（デフォルトで大文字と小文字を区別しない）
* (大文字と小文字 `u` の区別のフラグ)引数に関係なく、値がリストに既に存在する場合に、その値がリストに追加されることはなくなりました