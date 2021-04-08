---
title: getVisitDuration
description: 訪問者がサイトに来訪した時間を追跡します。
translation-type: ht
source-git-commit: ca8e563118dcc74dfa718bd203db295faf4e9aa6
workflow-type: ht
source-wordcount: '585'
ht-degree: 100%

---


# アドビプラグイン：getVisitDuration

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getVisitDuration` プラグインは、訪問者がその時点までサイトに滞在した時間を分単位で追跡します。この時点までのサイトの累積時間を追跡する場合や、アクティビティの実行に要する時間を追跡する場合は、このプラグインを使用することをお勧めします。このプラグインは、イベント間の時間を追跡しません。この機能が必要な場合は、[`getTimeBetweenEvents`](gettimebetweenevents.md) プラグインを使用します。

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
   * Action Type：Initialize getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.1 */
function getVisitDuration(){if(arguments&&"-v"===arguments[0])return{plugin:"getVisitDuration",version:"2.1"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getVisitDuration="2.1");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};d=(new Date).getTime();var k=cookieRead("s_dur"),a=0;if(isNaN(k)||18E5<d-k)k=d;a=d-k;cookieWrite("s_dur",k+"",30);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute":a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getVisitDuration` メソッドでは引数を使用しません。以下のどちらかの値を返します。

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` （`[x]` は訪問者がサイトにランディングしてから経過した分数）

このプラグインは、訪問者がサイトにランディングしてから経過したミリ秒数である、「`"s_dur"`」というファーストパーティ Cookie を作成します。Cookie は、無操作状態が 30 分間続くと有効期限が切れます。

## 呼び出しの例

### 例 1

次のコードは...

```js
s.eVar10 = s.getVisitDuration();
```

eVar10 を常に訪問者がサイトにランディングしてから経過した分数に設定します。

### 例 2

次のコードは...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

inList プラグインを使用して、イベント変数に購入イベントが含まれているかどうかを確認します。その場合、eVar10 は訪問者の訪問開始から購入時刻までの分数に設定されます。

### 例 3

次のコードは...

```js
s.prop10 = s.getVisitDuration();
```

prop10 を常に訪問者がサイトにランディングしてから経過した分数に設定します。これは、prop10 でパスが有効になっている場合に役立ちます。「出口」指標を prop10 レポートに追加すると、訪問者がサイトを離脱するまでに訪問にかかった時間の詳細な「散布図」レポートが表示されます。

## バージョン履歴

### 2.1（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 2.0（2018 年 5 月 2 日（PT））

* ポイントリリース（プラグインの完全な再分析と書き換え）。
