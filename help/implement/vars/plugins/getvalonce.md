---
title: getValOnce
description: Analytics 変数が 2 回続けて同じ値に設定されないようにします。
feature: Variables
exl-id: 23bc5750-43a2-4693-8fe4-d6b31bc34154
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 74%

---

# アドビプラグイン：getValOnce

{{plug-in}}

`getValOnce` プラグインは、変数が同じ値に複数回設定されるのを防ぎます。訪問者がページを更新した場合や、特定のページを複数回訪問した場合の重複を排除する場合は、このプラグインを使用することをお勧めします。Analysis Workspace の「回数」指標を使用しない場合は、このプラグインは不要です。

## Web SDK 拡張機能を使用したプラグインのインストール

Adobeには、Web SDK で最もよく使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. クリック **[!UICONTROL タグ]** 左側で、目的のタグプロパティをクリックします。
1. クリック **[!UICONTROL 拡張機能]** 左側で、 **[!UICONTROL カタログ]** タブ
1. を見つけてインストールする **[!UICONTROL 共通の Web SDK プラグイン]** 拡張子。
1. クリック **[!UICONTROL データ要素]** 左側で、目的のデータ要素をクリックします。
1. 次の設定で、目的のデータ要素名を設定します。
   * 拡張：共通の Web SDK プラグイン
   * データ要素: `getValOnce`
1. 右側に目的のパラメーターを設定します。
1. 変更を保存し、データ要素に公開します。

## Web SDK の手動実装プラグインのインストール

このプラグインは、Web SDK の手動実装内での使用は、まだサポートされていません。

## Adobe Analytics拡張機能を使用したプラグインのインストール

Adobeには、Adobe Analyticsで最もよく使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getValOnce
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターを使用したプラグインのインストール

Common Analytics Plugins プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングを行う際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v3.1 */
function getValOnce(vtc,cn,et,ep){var e=vtc,i=cn,t=et,n=ep;  if(arguments&&"-v"===arguments[0])return{plugin:"getValOnce",version:"3.1"};var o=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();if(void 0!==o&&(o.contextData.getValOnce="3.1"),window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){var n=window.location.hostname,o=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){o=2<o?o:2;var r=n.lastIndexOf(".");if(0<=r){for(;0<=r&&1<o;)r=n.lastIndexOf(".",r-1),o--;r=0<r?n.substring(r):n}}if(g=r,i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var f=new Date;f.setTime(f.getTime()+6e4*t)}else f=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!=typeof cookieRead)&&cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),n=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>n?i.length:n)))?e:""},e){var i=i||"s_gvo",t=t||0,n="m"===n?6e4:864e5;if(e!==cookieRead(i)){var r=new Date;return r.setTime(r.getTime()+t*n),cookieWrite(i,e,0===t?0:r),e}}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getValOnce` 関数は次の引数を使用します。

* **`vtc`**（必須、文字列）：以前に同じ値に設定されていたかどうかを確認する変数です。
* **`cn`**（オプション、文字列）：確認する値を保持する Cookie の名前です。デフォルトは `"s_gvo"` です。
* **`et`**（オプション、整数）：Cookie の有効期限（引数に応じて日単位または分単位）`ep`です。デフォルト値は `0` で、ブラウザーセッションの終わりに有効期限が切れます。
* **`ep`**（オプション、文字列）：この引数は、`et` 引数も設定されている場合にのみ設定します。`et` 引数で有効期限を日数ではなく分単位で指定する場合は `"m"` に設定します。デフォルト値は `"d"` で、日単位で `et` 引数を設定します。

`vtc` 引数と Cookie の値が一致する場合、この関数は空の文字列を返します。`vtc` 引数と Cookie の値が一致しない場合、この関数は `vtc` 引数を文字列として返します。

## 例

```js
// Prevent the same value from being passed in to the campaign variable more than once in a row for next 30 days
s.campaign = getValOnce(s.campaign,"s_campaign",30);

// Prevent the same value from being passed in to eVar2 more than once in a row for the browser session
s.eVar2 = getValOnce(s.eVar2,"s_ev2");

// Prevent the same value from being passed in to eVar8 more than once in a row for 10 minutes
s.eVar8 = getValOnce(s.eVar8,"s_ev8",10,"m");
```

## バージョン履歴

### 3.1（2022 年 9 月 23 日）

* 有効期限のバグを修正しました

### 3.0 （2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 2.01

* Cookie の書き込みに関する問題を修正しました。

### 2.0

* ポイントリリース（再コンパイル、コードサイズの縮小）。

### 1.1

* `t` パラメーターを使用して有効期限の指定に分または日を選択するオプションを追加しました。
* `k` 変数のスコープをプラグインに制限する修正を加えました。この変更により、ページ上の他のコードとの干渉が発生する可能性を回避できます。
