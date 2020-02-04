---
title: getVisitDuration
description: 訪問者がサイトに来訪した時間を追跡します。
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobeプラグイン：getVisitDuration

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `getVisitDuration` ラグインは、訪問者がその時点までサイトに滞在した時間を分単位で追跡します。 この時点までのサイトの累積時間を追跡する場合や、アクティビティの実行に要する時間を追跡する場合は、このプラグインを使用することをお勧めします。 このプラグインは、イベント間の時間を追跡しません。この機能が必要な場合は、プラグインを `getTimeBetweenEvents` 使用します。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * 条件：なし
   * イベント：コア — ライブラリ読み込み済み（ページの上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：getVisitDurationの初期化
1. ルールに対する変更を保存して発行します。

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
/* Adobe Consulting Plugin: getVisitDuration v2.0 */
s.getVisitDuration=function(){var d=new Date,c=d.getTime(),b=this.c_r("s_dur");if(isNaN(b)||18E5<c-b)b=c;var a=c-b;d.setTime(c+18E5); this.c_w("s_dur",b+"",d);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute": a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメ `getVisitDuration` ソッドでは引数を使用しません。 次のいずれかの値を返します。

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (ここ `[x]` で、訪問者がサイトにランディングしてから経過した分数)

このプラグインは、訪問者がサイトにランディングし `"s_dur"`てから経過したミリ秒数である、というファーストパーティcookieを作成します。 cookieは、無操作状態が30分間続くと有効期限が切れます。

## 呼び出しの例

### 例1

次のコード…

```js
s.eVar10 = s.getVisitDuration();
```

...は、常にeVar10を、訪問者がサイトにランディングしてから経過した分数に設定します。

### 例2

次のコード…

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...inlistプラグインを使用して、イベント変数に購入イベントが含まれているかどうかを確認します。  その場合、eVar10は訪問者の訪問開始から購入時刻までの分数に設定されます。

### 例3

次のコード…

```js
s.prop10 = s.getVisitDuration();
```

...は、常にprop10を、訪問者がサイトにランディングしてから経過した分数に設定します。  これは、prop10でパスが有効になっている場合に役立ちます。  「出口」指標をprop10レポートに追加すると、訪問者がサイトを離脱するまでに訪問にかかった時間の詳細な「散布図」レポートが表示されます。

## バージョン履歴

### 2.0（2018年5月2日）

* ポイントリリース（プラグインの完全な再分析/書き換え）。
