---
title: inList
description: 値が別の文字区切り値に含まれているかどうかを確認します。
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '557'
ht-degree: 100%

---

# アドビプラグイン：inList

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`inList` プラグインを使用すると、区切り文字列または JavaScript 配列オブジェクト内に値が既に存在するかどうかを確認できます。その他のプラグインの中には、`inList`プラグインの動作が依存するものもあります。このプラグインは、部分文字列と一致しない JavaScript `indexOf()` メソッドよりも明確な利点を提供します。例えば、このプラグインを使用して `"event2"` のチェックをおこなった場合、`"event25"` を含む文字列とは一致しません。区切り文字付きの文字列や配列の値を確認する必要がない場合や、独自の `indexOf()` ロジックを使用する場合は、このプラグインは不要です。

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
   * Action Type：Initialize inList
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
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`inList` 関数は、入力に応じてブール値を返します。 次の引数を使用します。

* **`lv`**（必須、文字列または配列）：検索する値の区切りリストまたは JavaScript 配列オブジェクトです。
* **`vtc`**（必須、文字列）：検索する値です。
* **`d`**（オプション、文字列）：`lv` 引数内の個々の値を区切るために使用する区切り文字です。設定されていない場合は、デフォルトでコンマ（`,`）が使用されます。
* **`cc`**（オプション、ブール値）：`true` または `1` に設定した場合、チェックでは大文字と小文字が区別されます。`false` に設定するか省略すると、チェックでは大文字と小文字が区別されません。デフォルト値は `false` です。

この関数を呼び出すと、一致が見つかった場合は `true`、見つからなかった場合は `false` が返されます。

## 例

```js
// Returns true
s.events = "event22,event24";
if(inList(s.events,"event22")) {
    // Code will execute
}

// Returns false because event2 is not an exact match in the string
s.events = "event22,event24";
if(inList(s.events,"event2")) {
    // Code will not execute
}

// Returns true because of the NOT operator
s.events = "event22,event24";
if(!inList(s.events,"event23")) {
    // Code will execute
}

// Returns false because of the case-sensitive check
s.events = "event22,event23";
if(inList(s.events,"EVenT23","",true)) {
    // Code will not execute
}

// Returns false because of a mismatched delimiter, treating "events,eVar1" as a single value
s.linkTrackVars = "events,eVar1";
if(inList(s.linkTrackVars,"eVar1","|")) {
    // Code will not execute
}
```

## バージョン履歴

### 3.0 （2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### V2.1（2019 年 9 月 26 日（PT））

* `cc` 引数をブール値にしないオプションを追加しました。例えば、`1` は有効なケースチェック値です。

### V2.0（2018 年 4 月 17 日（PT））

* ポイントリリース（再コンパイル、コードサイズの縮小）。

### V1.01（2017 年 9 月 27 日（PT））

* コードを最適化してサイズを縮小しました。

### v1.0（2009）

* 初回リリース。
