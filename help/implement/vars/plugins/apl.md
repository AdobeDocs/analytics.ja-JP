---
title: apl（appendToList）
description: 複数の値をサポートする変数に値を追加します。
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 95%

---

# アドビプラグイン：apl（appendToList）

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`apl` プラグインを使用すると、リスト区切りの変数（例：[`events`](../page-vars/events/events-overview.md)、[`linkTrackVars`](../config-vars/linktrackvars.md)、[`list`](../page-vars/list.md)）に新しい値を安全に追加できます。

* 追加する値が変数に存在しない場合は、コードによって文字列の末尾に値が追加されます。
* 追加する値が変数に既に存在する場合、このプラグインは値を変更しません。この機能により、実装で値の重複を回避できます。
* 追加する変数が空の場合、プラグインは変数を新しい値に設定します。

区切り文字付きの値の文字列を含む既存の変数に新しい値を追加する場合は、このプラグインを使用することをお勧めします。区切り文字付きの値を含む変数に文字列を連結する場合は、このプラグインは不要です。

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
   * Action Type：Initialize APL（Append To List）
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
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`apl`関数は次の引数を使用します。

* **`lv`**（必須、文字列）：新しい値を追加する項目の区切りリストを含む変数です。
* **`vta`**（必須、文字列）：`lv` 引数の値に追加する新しい値のコンマ区切りリストです。
* **`d1`**（オプション、文字列）：`lv` 引数に既に含まれる個々の値を区切るために使用される区切り文字です。設定されていない場合は、デフォルトでコンマ（`,`）が使用されます。
* **`d2`**（オプション、文字列）：出力の区切り文字です。設定されていない場合のデフォルト値は、`d1` と同じ値です。
* **`cc`**（オプション、ブール値）：チェックで大文字と小文字が区別されるかどうかを示すフラグです。`true` の場合、重複チェックでは大文字と小文字が区別されます。`false` の場合や未設定の場合、重複チェックでは大文字と小文字が区別されません。デフォルト値は `false` です。

`apl`関数は、`lv`引数の値に、`vta`引数内の重複しない値を加えた値を返します。

## 例

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## バージョン履歴

### 4.0（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 3.2（2019 年 9 月 25 日（PT））

* 古いバージョンのプラグインを使用した `apl` 呼び出しの互換性の問題を修正しました。
* サイズを小さくするためにコンソールの警告を削除しました。
*  `inList 2.1` を追加しました。

### 3.1（2018 年 4 月 22 日（PT））

* `d2` 引数が設定されていない場合、デフォルトで `d1` 引数の値になるようになりました。

### 3.0（2018 年 4 月 16 日（PT））

* プラグインの完全な再分析と書き換え
* 詳細なエラーチェックを追加しました。
* `vta` 引数は、一度に複数の値を指定できるようになりました。
* 戻り値の書式を設定する `d2` 引数を追加しました。
* `cc` 引数をブール値に変更しました。

### 2.5（2016 年 2 月 18 日（PT））

* 比較処理に`inList`関数を使用するようになりました。

### 2.0（2016 年 1 月 26 日（PT））

* `d`（区切り文字）引数がオプションになりました（デフォルトでコンマ）。
* `u`（大文字と小文字の区別フラグ）引数がオプションになりました（デフォルトでは大文字と小文字が区別されません）。
* `u`（大文字と小文字の区別のフラグ）引数に関係なく、プラグインは、値がリストに既に存在する場合に、値をリストに追加しなくなりました。
