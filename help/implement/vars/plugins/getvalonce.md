---
title: getValOnce
description: Analytics 変数が 2 回続けて同じ値に設定されないようにします。
translation-type: tm+mt
source-git-commit: 5a81754ca6137d7bc1e790fe537acbb4bbdb8efb
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 99%

---


# アドビプラグイン：getValOnce

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getValOnce` プラグインは、変数が同じ値に複数回設定されるのを防ぎます。訪問者がページを更新した場合や、特定のページを複数回訪問した場合の重複を排除する場合は、このプラグインを使用することをお勧めします。Analysis Workspace の「回数」指標を使用しない場合は、このプラグインは不要です。

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
   * Action Type：Initialize getValOnce
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
/* Adobe Consulting Plugin: getValOnce v3.0 (Requires AppMeasurement) */
function getValOnce(vtc,cn,et,ep){var e=vtc,k=cn,l=et,m=ep;if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.0"};var c=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,a;b<window.s_c_il.length;b++)if(a=window.s_c_il[b],a._c&&"s_c"===a._c)return a}();"undefined"!==typeof c&&(c.contextData.getValOnce="3.0");window.cookieWrite=window.cookieWrite||function(b,a,d){if("string"===typeof b){var h=window.location.hostname,c=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){c=2<c?
c:2;var f=h.lastIndexOf(".");if(0<=f){for(;0<=f&&1<c;)f=h.lastIndexOf(".",f-1),c--;f=0<f?h.substring(f):h}}g=f;a="undefined"!==typeof a?""+a:"";if(d||""===a)if(""===a&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return b&&(document.cookie=encodeURIComponent(b)+"="+encodeURIComponent(a)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(b)===a:!1}};window.cookieRead=window.cookieRead||function(b){if("string"===
typeof b)b=encodeURIComponent(b);else return"";var a=" "+document.cookie,d=a.indexOf(" "+b+"="),c=0>d?d:a.indexOf(";",d);return(b=0>d?"":decodeURIComponent(a.substring(d+2+b.length,0>c?a.length:c)))?b:""};return e&&(k=k||"s_gvo",l=l||0,m="m"===m?6E4:864E5,e!==this.c_r(k))?(c=new Date,c.setTime(c.getTime()+l*m),cookieWrite(k,e,0===l?0:m),e):""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getValOnce` メソッドでは、次の引数を使用します。

* **`vtc`**（必須、文字列）：以前に同じ値に設定されていたかどうかを確認する変数です。
* **`cn`**（オプション、文字列）：確認する値を保持する Cookie の名前です。デフォルトは `"s_gvo"` です。
* **`et`**（オプション、整数）：Cookie の有効期限（引数に応じて日単位または分単位）`ep`です。デフォルト値は `0` で、ブラウザーセッションの終わりに有効期限が切れます。
* **`ep`**（オプション、文字列）：この引数は、`et` 引数も設定されている場合にのみ設定します。`et` 引数で有効期限を日数ではなく分単位で指定する場合は `"m"` に設定します。デフォルト値は `"d"` で、日単位で `et` 引数を設定します。

`vtc` 引数と Cookie の値が一致する場合、このメソッドは空の文字列を返します。`vtc` 引数と Cookie の値が一致しない場合、このメソッドは `vtc` 引数を文字列として返します。

## 呼び出しの例

### 例 1

この呼び出しを使用して、次の 30 日間、同じ値が連続で s.campaign に複数回渡されるのを防ぎます。

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

上記の呼び出しでは、プラグインはまず、「s_campaign」Cookie に既に含まれている値と、現在の s.campaign 変数から取得されている値を比較します。一致しない場合、プラグインは「s_campaign」Cookie を s.campaign からの新しい値と同じに設定し、新しい値を返します。この比較は今後 30 日間おこなわれます。

### 例 2

この呼び出しを使用して、セッション全体で同じ値が設定されるのを防ぎます。

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

このコードは、ユーザーのセッション中に同じ値が s.eVar2 に 2 回以上連続して渡されるのを防ぎます。また、有効期限が 0 に設定されているので、（呼び出しの最後に）ep の「m」引数値も無視します。また、このコードは比較値を「s_ev2」Cookie に保存します。

## バージョン履歴

### 3.0（2021年3月19日）

* コンテキストデータとしてバージョン番号を追加しました。

### 2.01

* Cookie の書き込みに関する問題を修正しました。

### 2.0

* ポイントリリース（再コンパイル、コードサイズの縮小）。

### 1.1

* `t` パラメーターを使用して有効期限の指定に分または日を選択するオプションを追加しました。
* `k` 変数のスコープをプラグインに制限する修正を加えました。この変更により、ページ上の他のコードとの干渉が発生する可能性を回避できます。
