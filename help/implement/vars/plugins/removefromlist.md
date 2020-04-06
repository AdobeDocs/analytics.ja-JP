---
title: rfl
description: 区切り文字で区切られた文字列から特定の値を削除します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：rfl（Remove From List）

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

The `rfl` plug-in allows you to &quot;safely&quot; remove values from delimited strings, such as [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md), and others. このプラグインは、区切り文字を気にせずに、区切り文字列から特定の値を削除する場合に便利です。その他のプラグインの一部は、正しく実行するために、このコードに依存しています。一度に複数の Analytics 変数に対して特定の関数を実行する必要がない場合や、依存するプラグインを使用しない場合は、このプラグインは必要ありません。

プラグインでは次のロジックを使用します。

* 削除する値が存在する場合は、削除する値を除くすべての値を変数に保持します。
* 削除する値が存在しない場合は、元の文字列をそのまま保持します。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize RFP（Remove From List）
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`rfl` メソッドでは、次の引数を使用します。

* **`lv`**（必須、文字列）：区切られた値のリストを含む変数（または文字列）です。
* **`vr`**（必須、文字列）：`lv` 引数から削除する値です。`rfl` を 1 回呼び出して複数の値を削除することをお勧めします。
* **`d1`**（オプション、文字列）：`lv` 引数で使用する区切り文字です。デフォルトはコンマ（`,`）です。
* **`d2`**（オプション、文字列）：戻り文字列で使用する区切り文字です。デフォルトでは、`d1` 引数と同じ値になります。
* **`df`**（オプション、ブール値）：`true` の場合、すべてのインスタンスではなく、`lv` 引数から `vr` 引数のインスタンスのみが強制的に複製されます。未設定の場合のデフォルト値は `false` です。

このメソッドを呼び出すと、`lv` 引数を含み、`vr` 引数で指定された値のインスタンス（または重複インスタンス）を一切含まない、変更された文字列が返されます。

## 呼び出しの例

### 例 1

以下で、

```js
s.events = "event22,event24,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event24");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event25";
```

### 例 2

以下で、

```js
s.events = "event22,event24,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event26");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event24,event25";
```

この例では、s.events に「event26」が含まれていないので、rfl の呼び出しでは s.events に変更が加えられていません。

### 例 3

以下で、

```js
s.events = "event22,event24,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events);
```

s.events の最終値は次のとおりです。

```js
s.events = "";
```

s.rfl の呼び出しで lv 引数または vr 引数が空白の場合、プラグインは何も返しません。

### 例 4

以下で、

```js
s.prop4 = "hello|people|today";
```

次のコードが実行された場合、

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

s.prop4 の最終値は、引き続き次のようになります。

```js
s.prop4 = "hello|people|today";
```

s.eVar5 の最終値は次のようになります。

```js
s.eVar5 = "hello|today";
```

プラグインは値を返すだけであることに注意してください。lv 引数を使用して渡された変数は、実際には「リセット」されません。

### 例 5

以下で、

```js
s.prop4 = "hello|people|today";
```

次のコードが実行された場合、

```js
s.prop4 = s.rfl(s.prop4,"people");
```

s.prop4 の最終値は、引き続き次のようになります。

```js
s.prop4 = "hello|people|today";
```

lv 引数の値にデフォルト値と異なる区切り文字（コンマなど）が含まれている場合は、d1 引数を必ず設定してください。

### 例 6

以下で、

```js
s.events = "event22,event23,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"EVenT23");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event23,event25";
```

この例は実用的ではありませんが、大文字と小文字を区別する値を渡す必要があることを示しています。

### 例 7

以下で、

```js
s.events = "event22,event23:12345,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event23");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event25";
```

### 例 8

以下で、

```js
s.events = "event22,event23:12345,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event23:12345");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event23:12345,event25";
```

シリアル化や数値／通貨の構文を使用するイベントを削除する必要がある場合は、s.rfl の呼び出しでイベント自体（シリアル化／数値／通貨の値を除く）のみを指定する必要があります。

### 例 9

以下で、

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event23");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event24,event25");
```

### 例 10

以下で、

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event23,event24,event25");
```

### 例 11

以下で、

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

s.events の最終値は次のとおりです。

```js
s.events = "event22|event23|event24|event25");
```

### 例 12

以下で、

```js
s.events = "event22,event23,event24,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event23,event24");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event23,event24,event25";
```

vr 引数に複数の値を設定することはできません。上の例の rfl ロジックは、最初に lv 引数（「s.events」）内の値を分割し、各区切り値を完全な vr 引数値（「event23,event24」）に一致させようとします。

### 例 13

以下で、

```js
s.events = "event22,event23,event24,event25";
```

次のコードが実行された場合、

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event25");
```

リストから削除する各値は、それぞれ独自の s.rfl 呼び出し内に含まれている必要があります。

### 例 14

以下で、

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

次のコードが実行された場合、

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

s.linkTrackVars の最終値は次のとおりです。

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

この s.rfl 呼び出しの最後の 3 つの引数（&quot;,&quot;,&quot;,&quot;,false）は、デフォルトの引数値と一致するので、設定する必要はありませんが、「無害」です。

### 例 15

以下で、

```js
s.events = "event22,event23,event24";
```

次のコードが実行された場合、

```js
s.rfl(s.events,"event23");
```

s.events の最終値は、次のとおりです。

```js
s.events = "event22,event23,event24";
```

この場合も、プラグインが返す値は 1 つのみであることに注意してください。lv 引数を使用して渡された変数は、実際には「リセット」されません。

## バージョン履歴

### 2.01（2019 年 9 月 18 日）

* デフォルトの区切り文字値に関するマイナーなバグ修正

### 2.0（2018 年 4 月 17 日）

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* `join` プラグインの必要性を削除しました。

### 1.0（2016 年 7 月 19 日）

* 初回リリース。
