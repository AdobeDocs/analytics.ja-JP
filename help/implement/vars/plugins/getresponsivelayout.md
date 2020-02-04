---
title: getResponsiveLayout
description: 現在閲覧中のWebサイトのレイアウトを特定します。
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Adobeプラグイン：getResponsiveLayout

> [!IMPORTANT] このプラグインは、Adobe Analyticsを使用してより多くの価値を得るために、アドビコンサルティングから提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `getResponsiveLayout` ラグインを使用すると、訪問者が現在閲覧しているレスポンシブデザインベースのWebサイトのバージョンを追跡できます。 サイトでレスポンシブデザインを使用し、訪問者が閲覧したサイトのバージョンを追跡する場合は、このプラグインを使用することをお勧めします。 サイトでレスポンシブデザインを使用しない場合は、このプラグインは不要です。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. プラグインを使用する起動ルールに対して、次の設定を含むアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：addProductEvarの初期化
1. ルールへの変更を保存して発行します

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張」タブ [!UICONTROL に移動し] 、Adobe Analytics拡張機能の [!UICONTROL 下にある「設定] 」ボタンをクリックします。
1. 「カスタムコー [!UICONTROL ドを使用してトラッキングを設定] 」アコーディオンを展開すると、「エディターを開く  」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

Analyticsトラッキングオブジェクトをインスタンス化した後（を使用して）、AppMeasurementファイルの任意の場所に次のコードをコピーして貼り付 `s_gi`けます。 コードのコメントとバージョン番号を実装に保持しておくと、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getResponsiveLayout` ッドでは、次の引数を使用します。

* **`ppw`**（必須、整数）:ページがスマートフォンの縦置きレイアウトからスマートフォンの横置きレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅（ピクセル単位）
* **`plw`**（必須、整数）:ページがスマートフォンの横置きレイアウトからタブレットベースのレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅のピクセル数です
* **`tw`**（必須、ブール値）:ページがタブレットレイアウトからデスクトップベースのレイアウトに切り替わる前に、ブラウザーウィンドウに表示できるピクセルの最大幅です。

このメソッドを呼び出すと、2つの部分を含む文字列が返されます。 最初の部分では、ブラウザーの幅と上記の引数に応じて、次の値が使用されます。

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` （縦置きと横置きの両方のレイアウトを持たないサイトの場合）
* `"tablet layout"`
* `"desktop layout"`

返される文字列の2番目の部分は、ブラウザーの幅と高さの寸法です。 例：`"desktop layout:1243x700"`。

## 呼び出しの例

### 例1

...

* ブラウザーの幅が500ピクセルを超える場合、サイトはスマートフォンの縦置きモードからスマートフォンの横置きモードに切り替わります
* ブラウザーの幅が700ピクセルを超える場合、サイトはスマートフォンの横置きモードからタブレットモードに切り替わります。
* ブラウザーの幅が1000ピクセルを超える場合、サイトのモードがタブレットモードからデスクトップモードに切り替わる

...次のコードは、eVar10を、訪問者のエクスペリエンスとしての現在のレスポンシブデザインレイアウト、およびブラウザーの幅とサイズに等しく設定します

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### 例2

...

* サイトにはスマートフォンモード、タブレットモード、デスクトップモードのみがある
* ブラウザーの幅が500ピクセルを超える場合、サイトのモードがスマートフォンモードからタブレットモードに切り替わります
* ブラウザーの幅が1,100ピクセルを超える場合、サイトのモードがタブレットモードからデスクトップモードに切り替わります。

...次のコードは、eVar10を、訪問者のエクスペリエンスとしての現在のレスポンシブデザインレイアウト、およびブラウザーの幅とサイズに等しく設定します

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## バージョン履歴

### 1.0（2018年5月2日）

* 初回リリース。
