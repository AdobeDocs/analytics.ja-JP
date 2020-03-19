---
title: getResponsiveLayout
description: 現在表示中のWebサイトのレイアウトを特定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getResponsiveLayout

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getResponsiveLayout` ラグインを使用すると、訪問者が現在見ているレスポンシブデザインベースのWebサイトのバージョンを追跡できます。 サイトでレスポンシブデザインを使用し、訪問者が閲覧したサイトのバージョンを追跡する場合は、このプラグインの使用をお勧めします。 サイトでレスポンシブデザインを使用しない場合は、このプラグインは不要です。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最もよく使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、ボタンをクリックしま [!UICONTROL Catalog] す。
1. 拡張機能のインストールと公 [!UICONTROL Common Analytics Plugins] 開
1. まだ設定していない場合は、「Initialize Plug-ins」というラベルの付いたルールを次の設定で作成します。
   * 条件：なし
   * イベント：コア — ライブラリ読み込み済み（ページの上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：getResponsiveLayoutを初期化
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、Adobe Analytics拡張機能の下 [!UICONTROL Configure] にあるボタンをクリックします。
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

次のコードを、Analyticsトラッキングオブジェクトのインスタンス化（を使用）後に、AppMeasurementファイルの任意の場所にコピーして貼り付 [`s_gi`](../functions/s-gi.md)けます。 導入時にコードのコメントとバージョン番号を保持すると、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getResponsiveLayout` ッドでは、次の引数を使用します。

* **`ppw`** （必須、整数）:ページがスマートフォンの縦置きレイアウトからスマートフォンの横置きレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大幅（ピクセル単位）
* **`plw`** （必須、整数）:ページがスマートフォン用の横置きレイアウトからタブレット用のレイアウトに切り替わる前に、ブラウザーウィンドウに表示できる最大ピクセル幅です。
* **`tw`** （必須、ブール値）:ページがタブレットレイアウトからデスクトップベースのレイアウトに切り替わる前に、ブラウザーウィンドウに表示されるピクセルの最大幅です。

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

* ブラウザーの幅が500ピクセルを超える場合、サイトは電話の縦置きモードから電話の横置きモードに切り替わります。
* ブラウザーの幅が700ピクセルを超える場合に、サイトがスマートフォンの横置きモードからタブレットモードに切り替わる
* ブラウザーの幅が1000ピクセルを超える場合、サイトのモードがタブレットモードからデスクトップモードに切り替わる

...次のコードは、eVar10を、訪問者による現在のレスポンシブデザインレイアウトと同じエクスペリエンス、およびブラウザーの幅とサイズに設定します

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### 例2

...

* サイトには、スマートフォンモード、タブレットモード、デスクトップモードのみがあります
* ブラウザーの幅が500ピクセルを超える場合、サイトのモードがスマートフォンモードからタブレットモードに切り替わる
* ブラウザーの幅が1,100ピクセルを超える場合、サイトのモードがタブレットモードからデスクトップモードに切り替わる

...次のコードは、eVar10を、訪問者による現在のレスポンシブデザインレイアウトと同じエクスペリエンス、およびブラウザーの幅とサイズに設定します

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## バージョン履歴

### 1.0（2018年5月2日）

* 初回リリース。
