---
title: rfl
description: 文字区切り文字列から特定の値を削除します。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobeプラグイン：rfl（リストから削除）

> [!IMPORTANT] このプラグインは、Adobe Analyticsを使用してより多くの価値を得るために、アドビコンサルティングから提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `rfl` ラグインを使用すると、区切られた文字列（例：、リスト変数など）から値を「安全に」 `events`に削 `products`除することができます。 このプラグインは、区切り文字を気にせずに、区切り文字列から特定の値を削除する場合に便利です。 その他のプラグインの一部は、正しく実行するために、このコードに依存しています。 一度に複数のAnalytics変数に対して特定の関数を実行する必要がない場合や、依存するプラグインを使用しない場合は、このプラグインは必要ありません。

プラグインは次のロジックを使用します。

* 削除する値が存在する場合、プラグインは、削除する値を除くすべての値を変数に保持します。
* 削除する値が存在しない場合、プラグインは元の文字列をそのまま保持します。

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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `rfl` ッドでは、次の引数を使用します。

* **`lv`**（必須、文字列）:区切られた値のリストを含む変数（または文字列）
* **`vr`**（必須、文字列）:引数から削除する値`lv`です。 1回の呼び出しで複数の値を削除することをお勧め`rfl`します。
* **`d1`**（オプション、文字列）:引数で使用する`lv`区切り文字。 デフォルトはコンマ(`,`)です。
* **`d2`**（オプション、文字列）:戻り文字列で使用する区切り文字です。 デフォルトでは、引数と同じ値にな`d1`ります。
* **`df`**（オプション、ブール値）:の場合、`true`すべてのインスタンスではなく、引数から引`vr`数のインスタンス`lv`のみが強制的に複製されます。 未設定の場`false`合はデフォルトです。

このメソッドを呼び出すと、引数を含み、引数で指定さ `lv` れた値のインスタンス（または重複インスタンス）を一切含まない、変更された文字列が返さ `vr` れます。

## 呼び出しの例

### 例1

...

```js
s.events = "event22,event24,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event24");
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event25";
```

### 例2

...

```js
s.events = "event22,event24,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event26");
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event24,event25";
```

この例では、s.eventsに「event26」が含まれていないので、rfl呼び出しでs.eventsに変更が加えられていません。

### 例3

...

```js
s.events = "event22,event24,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events);
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "";
```

s.rfl呼び出しでlv引数またはvr引数が空白の場合、プラグインは何も返しません

### 例4

...

```js
s.prop4 = "hello|people|today";
```

...次のコードが実行されます。

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

...s.prop4の最終値は、引き続き次のようになります。

```js
s.prop4 = "hello|people|today";
```

...s.eVar5の最終値は次のようになります。

```js
s.eVar5 = "hello|today";
```

プラグインは値を返すだけであることに注意してください。lv引数を使用して渡された変数は、実際には「リセット」されません。

### 例5

...

```js
s.prop4 = "hello|people|today";
```

...次のコードが実行されます。

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...s.prop4の最終値は、引き続き次のようになります。

```js
s.prop4 = "hello|people|today";
```

lv引数の値にデフォルト値と異なる区切り文字（コンマなど）が含まれている場合は、d1引数を必ず設定してください。

### 例6

...

```js
s.events = "event22,event23,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"EVenT23");
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event23,event25";
```

この例は実用的ではありませんが、大文字と小文字を区別する値を渡す必要があることを示しています。

### 例7

...

```js
s.events = "event22,event23:12345,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event23");
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event25";
```

### 例8

...

```js
s.events = "event22,event23:12345,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event23:12345");
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event23:12345,event25";
```

シリアル化や数値/通貨の構文を使用するイベントを削除する必要がある場合は、s.rfl呼び出しでイベント自体（シリアル化/数値/通貨の値を除く）のみを指定する必要があります。

### 例9

...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event23");
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event24,event25");
```

### 例10

...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event23,event24,event25");
```

### 例11

...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22|event23|event24|event25");
```

### 例12

...

```js
s.events = "event22,event23,event24,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event23,event24");
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event23,event24,event25";
```

vr引数に複数の値を設定することはできません。 上の例のrflロジックは、最初にlv引数（s.eventsなど）内の値を分割し、各区切り値がvr引数の完全な値(&quot;event23,event24&quot;)。

### 例13

...

```js
s.events = "event22,event23,event24,event25";
```

...次のコードが実行されます。

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...s.eventsの最終値は次のとおりです。

```js
s.events = "event22,event25");
```

リストから削除する各値は、それぞれ独自のs.rfl呼び出し内に含まれている必要があります。

### 例14

...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...次のコードが実行されます。

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...s.linkTrackVarsの最終値は次のとおりです。

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

最後の3つの引数(このs.rfl呼び出しの最後に「,」、「,」、「false」と表示される場合は必須ではありませんが、デフォルト設定と一致するので、このファイルが存在することによって「何も害を与えません」。

### 例15

...

```js
s.events = "event22,event23,event24";
```

...次のコードが実行されます。

```js
s.rfl(s.events,"event23");
```

...s.eventsの最後の値は、次のとおりです。

```js
s.events = "event22,event23,event24";
```

この場合も、プラグインが返す値は1つのみであることに注意してください。lv引数を使用して渡された変数は、実際には「リセット」されません。

## バージョン履歴

### 2.01（2019年9月17日）

* デフォルトの区切り文字値に関するマイナーなバグ修正

### 2.0（2018年4月17日）

* ポイントリリース（再コンパイル、コードサイズが小さい）。
* プラグインの必要性を `join` 削除しました。

### 1.0（2016年7月19日）

* 初回リリース。
