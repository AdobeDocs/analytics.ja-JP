---
title: getAndPersistValue
description: 後でいつでも取得できる値を格納します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getAndPersistValue

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getAndPersistValue` ラグインを使用すると、後で訪問中に取得できるcookieに値を格納できます。 これは、Adobe Experience Platform Launchの機能と [!UICONTROL Storage duration] 同様の役割を果たします。 変数の設定後、後続のヒットでAnalytics変数を自動的に同じ値に保持する場合は、このプラグインの使用をお勧めします。 Launchの機能が十分な場合や、後続のヒットで変数を同じ値に設定して保持する必要がない場合は、このプラグインは必要あり [!UICONTROL Storage duration] ません。 組み込み型の永続性のeVarは、アドビがサーバー側で保持するので、このプラグインを使用する必要はありません。

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
   * アクションタイプ：getAndPersistValueの初期化
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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getAndPersist` ッドでは、次の引数を使用します。

* **`vtp`** （必須）:ページ間で保持する値
* **`cn`** （オプション）:値を格納するCookieの名前。 この引数が設定されていない場合、cookieに `"s_gapv"`
* **`ex`** （オプション）:Cookieの有効期限が切れるまでの日数。 この引数が設定され `0` ているか、設定されていない場合、cookieは訪問の最後（30分間無操作状態が続く）に有効期限が切れます。

引数内の変数が設定さ `vtp` れている場合、プラグインはcookieを設定し、そのcookieの値を返します。 引数内の変数が設 `vtp` 定されていない場合、プラグインはcookieの値のみを返します。

## 例

### 例1

次のコードでは、eVar21を「hello」の値に設定します。  次に、eVar21の値(&quot;hello&quot;)。  次に、コードはeVar21をev21gapv cookieの値に等しく設定します。

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例2

eVar21が現在のページにまだ設定されていないが、過去28日間に前のページで「hello」に設定されていたとします。   次のコードでは、eVar21がev21gapv cookieの値(&quot;hello&quot;)。  関数が呼び出される前に現在のページでeVar21が設定されていなかったので、ev21gapv cookieはリセットされません。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例3

eVar21が現在のページにまだ設定されていないが、過去28日間に前のページで「hello」に設定されていたとします。  次のコードは、ev21gapv cookieの値(&quot;hello&quot;)。  eVar21は設定されません。

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例4

次のコードでは、eVar21を「howdy」の値に設定します。  次に、コードはeVar21の値(&quot;howdy&quot;)。  次に、コードはprop35をev21gapv cookieの値(&quot;howdy&quot;)。

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例5

s.eVar21が過去28日間にどのページにも設定されていないとします。  次のコードでは、s.eVar21がnothingに設定されます。これは、最後に設定されてから28日後にev21gapv cookieの有効期限が切れたためです。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例6

次のコードは、eVar30を「shopping」に設定します。  次に、s_gapv cookieを設定します。これは、s.eVar30の値(&quot;shopping&quot;)。  次に、s.eVar30をs_gapv cookieの値と等しく設定します(例：getAndPersistValue呼び出しはs_gapv cookieの値を返します（この場合は「shopping」）。

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

s.eVar30が、セッション中に閲覧された追加ページで明示的な値に設定されていないが、次のコードを介して（doPlugins内で）設定されている場合…

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30は「shopping」（s_gapv cookieの永続値）に等しく設定されます。

## バージョン履歴

### 2.0（2018年4月17日）

* ポイントリリース（コードサイズが小さい）
* 引数に0を渡すと、ブ `ex` ラウザーセッションの終了時ではなく、無操作状態が30分間続いた後に強制的に有効期限が切れるようになりました。

### 1.0（2016年1月19日）

* 初回リリース。
