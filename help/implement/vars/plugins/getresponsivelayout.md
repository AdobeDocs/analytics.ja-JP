---
title: getResponsiveLayout
description: 現在閲覧中の Web サイトのレイアウトを特定します。
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '674'
ht-degree: 100%

---

# アドビプラグイン：getResponsiveLayout

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getResponsiveLayout` プラグインを使用すると、訪問者が現在閲覧しているレスポンシブデザインベースの Web サイトのバージョンを追跡できます。サイトでレスポンシブデザインを使用し、訪問者が閲覧したサイトのバージョンを追跡する場合は、このプラグインを使用することをお勧めします。サイトでレスポンシブデザインを使用しない場合は、このプラグインは不要です。

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
   * Action Type：Initialize getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getResponsiveLayout` メソッドでは、次の引数を使用します。

* **`ppw`**（必須、整数）：ページがスマートフォンの縦置きレイアウトからスマートフォンの横置きレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅（ピクセル単位）です。
* **`plw`**（必須、整数）：ページがスマートフォンの横置きレイアウトからタブレットベースのレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅（ピクセル単位）です。
* **`tw`**（必須、ブール値）：ページがタブレットレイアウトからデスクトップベースのレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅（ピクセル単位）です。

このメソッドを呼び出すと、2 つの部分を含む文字列が返されます。最初の部分では、ブラウザーの幅と上記の引数に応じて、次の値が使用されます。

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` （縦置きと横置きの両方のレイアウトを持たないサイトの場合）
* `"tablet layout"`
* `"desktop layout"`

返される文字列の 2 番目の部分は、ブラウザーの幅と高さの寸法です。例：`"desktop layout:1243x700"`。

## 呼び出しの例

### 例 1

以下の条件が当てはまる場合：

* ブラウザーの幅が 500 ピクセルを超える場合、サイトはスマートフォンの縦置きモードからスマートフォンの横置きモードに切り替わります
* ブラウザーの幅が 700 ピクセルを超える場合、サイトはスマートフォンの横置きモードからタブレットモードに切り替わります
* ブラウザーの幅が 1,000 ピクセルを超える場合、サイトはタブレットモードからデスクトップモードに切り替わります

次のコードは、eVar10 を、訪問者のエクスペリエンスとしての現在のレスポンシブデザインレイアウト、およびブラウザーの幅とサイズに等しく設定します。

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### 例 2

以下の条件が当てはまる場合：

* サイトにはスマートフォンモード、タブレットモード、デスクトップモードのみがあります
* ブラウザーの幅が 500 ピクセルを超える場合、サイトのモードがスマートフォンモードからタブレットモードに切り替わります
* ブラウザーの幅が 1,100 ピクセルを超える場合、サイトはタブレットモードからデスクトップモードに切り替わります

次のコードは、eVar10 を、訪問者のエクスペリエンスとしての現在のレスポンシブデザインレイアウト、およびブラウザーの幅とサイズに等しく設定します。

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## バージョン履歴

### 1.1（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2018 年 5 月 2 日（PT））

* 初回リリース。
