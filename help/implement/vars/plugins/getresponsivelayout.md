---
title: getResponsiveLayout
description: 現在閲覧中の Web サイトのレイアウトを特定します。
feature: Variables
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 86%

---

# アドビプラグイン：getResponsiveLayout

{{plug-in}}

`getResponsiveLayout` プラグインを使用すると、訪問者が現在閲覧しているレスポンシブデザインベースの Web サイトのバージョンを追跡できます。サイトでレスポンシブデザインを使用し、訪問者が閲覧したサイトのバージョンを追跡する場合は、このプラグインを使用することをお勧めします。サイトでレスポンシブデザインを使用しない場合は、このプラグインは不要です。

## Web SDK または Web SDK 拡張機能を使用したプラグインのインストール

このプラグインは、Web SDK 内での使用はまだサポートされていません。

## Adobe Analytics拡張機能を使用してプラグインをインストールします

Adobeでは、Adobe Analyticsで最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getResponsiveLayout` 関数は次の引数を使用します。

* **`ppw`**（必須、整数）：ページがスマートフォンの縦置きレイアウトからスマートフォンの横置きレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅（ピクセル単位）です。
* **`plw`**（必須、整数）：ページがスマートフォンの横置きレイアウトからタブレットベースのレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅（ピクセル単位）です。
* **`tw`**（必須、整数）：ページがタブレットレイアウトからデスクトップベースのレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅（ピクセル単位）です。

この関数を呼び出すと、コロン（`:`）で区切られた 2 つの部分を含む文字列が返されます。文字列の最初の部分には、ブラウザーの幅と上記の引数に応じて、次のいずれかの値が含まれます。

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` （縦置きと横置きの両方のレイアウトを持たないサイトの場合）
* `"tablet layout"`
* `"desktop layout"`

返される文字列の 2 番目の部分は、ブラウザーの幅と高さの寸法です。例：`"desktop layout:1243x700"`。

## 例

```js
// A visitor accesses your site on their laptop. The browser window is maximized.
// * Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
// * Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels
// Sets eVar10 to "desktop layout:1920x937".
s.eVar10 = getResponsiveLayout(500, 700, 1000);

// A visitor accesses your site on their phone.
// * Your site has only a phone mode, a tablet mode, and a desktop mode
// * Your site switches from phone mode to tablet mode when the browser width is greater than 800 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels
// Sets eVar10 to "phone portrait layout:720x1280"
s.eVar10 = getResponsiveLayout(800, 800, 1100);
```

## バージョン履歴

### 1.1（2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 1.0（2018 年 5 月 2 日（PT））

* 初回リリース。
