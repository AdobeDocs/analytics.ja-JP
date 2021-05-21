---
title: apl（appendToList）
description: 複数の値をサポートする変数に値を追加します。
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '1036'
ht-degree: 100%

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
   * Action Type：Initialize APL（Append To List）
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
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`apl` メソッドでは、次の引数を使用します。

* **`lv`**（必須、文字列）：新しい値を追加する項目の区切りリストを含む変数です。
* **`vta`**（必須、文字列）：`lv` 引数の値に追加する新しい値のコンマ区切りリストです。
* **`d1`**（オプション、文字列）：`lv` 引数に既に含まれる個々の値を区切るために使用される区切り文字です。設定されていない場合は、デフォルトでコンマ（`,`）が使用されます。
* **`d2`**（オプション、文字列）：出力の区切り文字です。設定されていない場合のデフォルト値は、`d1` と同じ値です。
* **`cc`**（オプション、ブール値）：チェックで大文字と小文字が区別されるかどうかを示すフラグです。`true` の場合、重複チェックでは大文字と小文字が区別されます。`false` の場合や未設定の場合、重複チェックでは大文字と小文字が区別されません。デフォルト値は `false` です。

`apl` メソッドは、`lv` 引数の値に、`vta` 引数内の重複しない値を加えた値を返します。

## 呼び出しの例

### 例 1

以下の条件が当てはまる場合：

```js
s.events = "event22,event24";
```

次のコードが実行された場合、

```js
s.events = s.apl(s.events, "event23");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event24,event23";
```

### 例 2

以下の条件が当てはまる場合：

```js
s.events = "event22,event23";
```

次のコードが実行された場合、

```js
s.events = s.apl(s.events, "event23");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event23";
```

この例では、s.events に既に「event23」が含まれているので、apl 呼び出しで s.events は変更されませんでした。

### 例 3

以下の条件が当てはまる場合：

```js
s.events = ""; //blank value
```

次のコードが実行された場合、

```js
s.events = s.apl(s.events, "event23");
```

s.events の最終値は次のとおりです。

```js
s.events = "event23";
```

### 例 4

以下の条件が当てはまる場合：

```js
s.prop4 = "hello|people";
```

次のコードが実行された場合、

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

s.prop4 の最終値は、引き続き次のとおりです。

```js
s.prop4 = "hello|people";
```

ただし、s.eVar5 の最終値は次のとおりです。

```js
s.eVar5 = "hello|people|today";
```

プラグインは値を返すだけであることに注意してください。lv 引数を使用して渡された変数は、必ずしも「リセット」されるわけではありません。

### 例 5

以下の条件が当てはまる場合：

```js
s.prop4 = "hello|people";
```

次のコードが実行された場合、

```js
s.prop4 = s.apl(s.prop4, "today");
```

s.prop4 の最終値は次のとおりです。

```js
s.prop4 = "hello|people,today";
```

区切り文字は、lv 引数の値と d1 および d2 引数の値の間で一貫性を保つようにしてください

### 例 6

以下の条件が当てはまる場合：

```js
s.events = "event22,event23";
```

次のコードが実行された場合、

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event23,EVentT23";
```

この例は実用的ではありませんが、大文字と小文字を区別するフラグを使用する際に注意が必要であることを示しています。

### 例 7

以下の条件が当てはまる場合：

```js
s.events = "event22,event23";
```

次のコードが実行された場合、

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event23,event24,event25");
```

このプラグインでは、「event23」は s.events に既に存在するので追加しません。ただし、event24 と event25 はどちらも s.events に含まれていないため追加されます。

### 例 8

以下の条件が当てはまる場合：

```js
s.linkTrackVars = "events,eVar1";
```

次のコードが実行された場合、

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

s.linkTrackVars の最終値は次のとおりです。

```js
s.linkTrackVars = "events,eVar1,campaign";
```

この apl 呼び出しの最後の 3 つの引数（&quot;,&quot;,&quot;,&quot;,false）は、デフォルトの引数値と一致するので、設定する必要はありませんが、「無害」です。

### 例 9

以下の条件が当てはまる場合：

```js
s.events = "event22,event24";
```

次のコードが実行された場合、

```js
s.apl(s.events, "event23");
```

s.events の最終値は次のとおりです。

```js
s.events = "event22,event24";
```

プラグインを単独で（変数に戻り値を割り当てずに）実行しても、lv 引数を通じて渡された変数は実際には「リセット」されません。

### 例 10

以下の条件が当てはまる場合：

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

次のコードが実行された場合、

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

s.list2 の最終値は次のとおりです。

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

2 つの区切り文字引数が異なるので、渡される値は最初の区切り文字引数（ ）で区切られ、2 番目の区切り文字引数（-）で結合されます。

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

* 比較処理に `inList` メソッドを使用するようになりました。

### 2.0（2016 年 1 月 26 日（PT））

* `d`（区切り文字）引数がオプションになりました（デフォルトでコンマ）。
* `u`（大文字と小文字の区別フラグ）引数がオプションになりました（デフォルトでは大文字と小文字が区別されません）。
* `u`（大文字と小文字の区別のフラグ）引数に関係なく、プラグインは、値がリストに既に存在する場合に、値をリストに追加しなくなりました。
