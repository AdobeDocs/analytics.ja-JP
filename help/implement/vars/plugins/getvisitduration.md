---
title: getVisitDuration
description: 訪問者がサイトに来訪した時間を追跡します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：getVisitDuration

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getVisitDuration` プラグインは、訪問者がその時点までサイトに滞在した時間を分単位で追跡します。この時点までのサイトの累積時間を追跡する場合や、アクティビティの実行に要する時間を追跡する場合は、このプラグインを使用することをお勧めします。このプラグインは、イベント間の時間を追跡しません。この機能が必要な場合は、[`getTimeBetweenEvents`](gettimebetweenevents.md) プラグインを使用します。

## Adobe Experience Platform Launch 拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getVisitDuration
1. ルールに対する変更を保存して発行します。

## Launch カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
1. 目的のプロパティをクリックします。
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getVisitDuration` メソッドでは引数を使用しません。以下のどちらかの値を返します。

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` （`[x]` は訪問者がサイトにランディングしてから経過した分数）

このプラグインは、訪問者がサイトにランディングしてから経過したミリ秒数である、「`"s_dur"`」というファーストパーティ Cookie を作成します。Cookie は、無操作状態が 30 分間続くと有効期限が切れます。

## 呼び出しの例

### 例 1

次のコードは...

```js
s.eVar10 = s.getVisitDuration();
```

eVar10 を常に訪問者がサイトにランディングしてから経過した分数に設定します。

### 例 2

次のコードは...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

inList プラグインを使用して、イベント変数に購入イベントが含まれているかどうかを確認します。その場合、eVar10 は訪問者の訪問開始から購入時刻までの分数に設定されます。

### 例 3

次のコードは...

```js
s.prop10 = s.getVisitDuration();
```

prop10 を常に訪問者がサイトにランディングしてから経過した分数に設定します。これは、prop10 でパスが有効になっている場合に役立ちます。「出口」指標を prop10 レポートに追加すると、訪問者がサイトを離脱するまでに訪問にかかった時間の詳細な「散布図」レポートが表示されます。

## バージョン履歴

### 2.0（2018 年 5 月 3 日）

* ポイントリリース（プラグインの完全な再分析と書き換え）。
