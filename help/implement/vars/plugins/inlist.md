---
title: inList
description: 値が別の文字区切り値に含まれているかどうかを確認します。
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '743'
ht-degree: 100%

---

# アドビプラグイン：inList

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`inList` プラグインを使用すると、区切り文字列または JavaScript 配列オブジェクト内に値が既に存在するかどうかを確認できます。その他のプラグインの中には、`inList`プラグインの動作が依存するものもあります。このプラグインは、部分文字列と一致しない JavaScript `indexOf()` メソッドよりも明確な利点を提供します。例えば、このプラグインを使用して `"event2"` のチェックをおこなった場合、`"event25"` を含む文字列とは一致しません。区切り文字付きの文字列や配列の値を確認する必要がない場合や、独自の `indexOf()` ロジックを使用する場合は、このプラグインは不要です。

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
   * Action Type：Initialize inList
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
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`inList` メソッドでは、次の引数を使用します。

* **`lv`**（必須、文字列または配列）：検索する値の区切りリストまたは JavaScript 配列オブジェクトです。
* **`vtc`**（必須、文字列）：検索する値です。
* **`d`**（オプション、文字列）：`lv` 引数内の個々の値を区切るために使用する区切り文字です。設定されていない場合は、デフォルトでコンマ（`,`）が使用されます。
* **`cc`**（オプション、ブール値）：`true` に設定した場合、大文字と小文字が区別されます。`false` に設定するか省略すると、チェックでは大文字と小文字が区別されません。デフォルト値は `false` です。

このメソッドを呼び出すと、一致が見つかった場合は `true`、見つからなかった場合は `false` が返されます。

## 呼び出しの例

### 例 1

以下の条件が当てはまる場合：

```js
s.events="event22,event24";
```

次のコードが実行された場合、

```js
if(s.inList(s.events,"event22"))
```

「if」条件文は「true」になります。

### 例 2

以下の条件が当てはまる場合：

```js
s.events="event22,event24";
```

次のコードが実行された場合、

```js
if(s.inList(s.events,"event2"))
```

inList の呼び出しで event2 と s.events の区切り文字付き値のいずれかが完全に一致しなかったので、「if」条件文は「false」になります。

### 例 3

以下の条件が当てはまる場合：

```js
s.events="event22,event24";
```

次のコードが実行された場合、

```js
if(!s.inList(s.events,"event23"))
```

inList の呼び出しで、event23 と s.events の区切り文字付き値のいずれかとが完全に一致しなかったので、「if」条件文は「true」になります。（inList 変数呼び出しの最初にある「NOT」演算子に注意してください）。

### 例 4

以下の条件が当てはまる場合：

```js
s.events = "event22,event23";
```

次のコードが実行された場合、

```js
if(s.inList(s.events,"EVenT23","",1))
```

「if」条件文は「false」になります。この例は実用的ではありませんが、大文字と小文字を区別するフラグを使用する際に注意が必要であることを示しています。

### 例 5

以下の条件が当てはまる場合：

```js
s.linkTrackVars = "events,eVar1";
```

次のコードが実行された場合、

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

「if」条件文は「false」になります。呼び出しに渡される d 引数の値（「|」）は、s.linkTrackVars 内の個々の値がパイプ文字で区切られていると想定しますが、実際には値がコンマで区切られています。この場合、プラグインは s.linkTrackVars の値全体（「events,eVar1」）と、検索する値（「eVar1」）の一致を確認しようとします。

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
