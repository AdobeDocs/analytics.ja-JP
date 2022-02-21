---
title: getNewRepeat
description: 新規訪問者とリピーターのアクティビティを追跡します。
feature: Variables
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 100%

---

# アドビプラグイン：getNewRepeat

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getNewRepeat` プラグインを使用すると、サイトへの訪問者が新しい訪問者か、再訪問者かを希望の日数以内に判断できます。カスタム日数を使用して訪問者を「新規」として識別する場合は、このプラグインを使用することをお勧めします。Analysis Workspace の新規訪問者ディメンションと再訪問者ディメンションが組織のニーズを満たしている場合、このプラグインは不要です。

## Adobe Experience Platform のタグを使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getNewRepeat
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「[!UICONTROL 設定]」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getNewRepeat` 関数は次の引数を使用します。

* **`d`**（整数、オプション）：訪問者を再び `"New"` にリセットする間隔の最小日数です。この引数を設定しない場合、デフォルトで 30 日に設定されます。

この関数は、プラグインによって設定された Cookie が存在しないか、有効期限が切れている場合の `"New"` 値を返します。プラグインによって設定された Cookie が存在する場合、および現在のヒットからの経過時間と Cookie に設定された時間が 30 分を超える場合、`"Repeat"` の値を返します。この関数は、訪問全体に対して同じ値を返します。

このプラグインは、`[LENGTH]` が `d` 引数と等しい、「`"s_nr[LENGTH]"`」という名前の Cookie を使用します。Cookie には、現在時刻と訪問者の現在のステータス（`"New"` または `"Repeat"`）を表す Unix タイムスタンプが含まれます。

## 例

```js
// Sets eVar1 to "New" if it is the visitor's first visit to the site, or they have not visited in at least 30 days. Otherwise, sets eVar1 to "Repeat".
s.eVar1 = getNewRepeat();

// Sets eVar2 to "New" if it is the visitor's first visit to the site, or they have not visited in at least a year (365 days). Otherwise, sets eVar2 to "Repeat".
s.eVar2 = getNewRepeat(365);
```

## バージョン履歴

### 3.0 （2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 2.1（2019 年 9 月 30 日（PT））

* JavaScript ロジックを再配置し、プラグインサイズを削減しました。

### 2.0（2018 年 4 月 16 日（PT））

* より小さいコードサイズで再コンパイルしました。
* 訪問情報を保存する Cookie に名前を付ける機能を削除しました。プラグインは、`d` 引数に渡された値に基づいて、Cookie に動的に名前を付けるようになりました。
