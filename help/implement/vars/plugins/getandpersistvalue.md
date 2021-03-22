---
title: getAndPersistValue
description: 後でいつでも取得できる値を格納します。
translation-type: tm+mt
source-git-commit: a2970e05abf0d1f963175db6e3554aa0e3034a70
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 99%

---


# アドビプラグイン：getAndPersistValue

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getAndPersistValue` プラグインを使用すると、Cookie に値を保存して後で訪問中に取得できます。これは、Adobe Experience Platform Launch の[!UICONTROL ストレージ期間]機能と同様の役割を果たします。変数の設定後の後続のヒットで Analytics 変数を自動的に同じ値に保持する場合は、このプラグインを使用することをお勧めします。Launch の[!UICONTROL ストレージ期間]機能で十分な場合や、後続のヒットで変数を同じ値に設定して永続化する必要がない場合は、このプラグインは必要ありません。組み込み型の eVar の永続性は、アドビがサーバー側で保持するので、このプラグインを使用する必要はありません。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getAndPersistValue
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「[!UICONTROL 設定]」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getAndPersist` メソッドでは、次の引数を使用します。

* **`vtp`**（必須）：ページ間で保持する値です。
* **`cn`**（オプション）：値を保存する Cookie の名前です。この引数が設定されていない場合、Cookie の名前は `"s_gapv"` です。
* **`ex`**（オプション）：Cookie の有効期限が切れるまでの日数です。この引数が `0` であるまたは設定されていない場合、Cookie は訪問の終了時（無操作状態が 30 分間続く）に期限切れになります。

`vtp` 引数内の変数が設定されている場合、プラグインは Cookie を設定し、その Cookie の値を返します。`vtp` 引数内の変数が設定されていない場合、プラグインは Cookie の値のみを返します。

## 例

### 例 1

次のコードは、eVar21 を「hello」の値に設定します。次に、コードは「ev21gapv」Cookie を設定します。これは、28 日で有効期限が切れ、eVar21 の値（つまり「hello」）に等しくなります。次に、コードは eVar21 を「ev21gapv」Cookie の値と等しく設定（またはリセット）します。

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 2

eVar21 が現在のページに設定されていないが、過去 28 日間に前のページで「hello」に設定されたとします。次のコードは単に、eVar21 を「ev21gapv」Cookie の値（「hello」）と等しく設定します。関数が呼び出される前に eVar21 が現在のページに設定されていなかったので、「ev21gapv」Cookie はリセットされません。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 3

eVar21 が現在のページに設定されていないが、過去 28 日間に前のページで「hello」に設定されたとします。次のコードは単に、prop35 を「ev21gapv」Cookie の値（「hello」）と等しく設定します。eVar21 は設定されません。

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 4

次のコードは、eVar21 を「howdy」の値に設定します。次に、コードは「ev21gapv」Cookie を設定（またはリセット）します。28 日で有効期限が切れ、eVar21 の値（つまり「howdy」）に等しくなります。次に、コードは prop35 を「ev21gapv」Cookie の値（「howdy」）と等しく設定します。

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 5

s.eVar21 が過去 28 日間にどのページにも設定されていないとします。次のコードでは、s.eVar21 が nothing に設定されます。これは、「ev21gapv」Cookie が最後に設定されてから 28 日後に有効期限が切れたためです。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 6

次のコードは、eVar30 を「shopping」に設定します。次に、「s_gapv」Cookie を設定します。ブラウザーセッションの終了時に有効期限が切れ、s.eVar30 の値（「shopping」）と等しくなります。次に、s.eVar30 を「s_gapv」Cookie の値と等しく設定します（つまり、getAndPersistValue の呼び出しは s_gapv cookie の値を返します（この場合は「shopping」））。

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

s.eVar30 が、セッション中に閲覧された追加ページで明示的な値に設定されていないが、次のコードを介して（doPlugins 内で）設定される場合

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

s.eVar30 は「shopping」（つまり、「s_gapv」Cookie の持続値）に等しく設定されます。

## バージョン履歴

### 3.0（2021年3月19日）

* コンテキストデータとしてバージョン番号を追加しました。

### 2.0（2018 年 4 月 17 日）

* ポイントリリース（コードサイズの縮小）
* `ex` 引数に 0 を渡すと、ブラウザーセッションの終わりではなく、無操作状態が 30 分続いた後に強制的に有効期限が切れるようになりました。

### 1.0（2016 年 1 月 19 日）

* 初回リリース。
