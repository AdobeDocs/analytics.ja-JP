---
title: getAndPersistValue
description: 後でいつでも取得できる値を格納します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# アドビプラグイン：getAndPersistValue

>[!IMPORTANT] このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getAndPersistValue` プラグインを使用すると、Cookie に値を保存して後で訪問中に取得できます。It serves a similar role to the [!UICONTROL Storage duration] feature in Adobe Experience Platform Launch. 変数の設定後の後続のヒットで Analytics 変数を自動的に同じ値に保持する場合は、このプラグインを使用することをお勧めします。This plug-in is not necessary if Launch&#39;s [!UICONTROL Storage duration] feature is sufficient, or if you do not need to set and persist variables to the same value in subsequent hits. 組み込み型の eVar の永続性は、アドビがサーバー側で保持するので、このプラグインを使用する必要はありません。

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
   * Action Type：Initialize getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getAndPersist` メソッドでは、次の引数を使用します。

* **`vtp`**（必須）：ページ間で保持する値です。
* **`cn`**（オプション）：値を保存する Cookie の名前です。この引数が設定されていない場合、Cookie の名前は `"s_gapv"` です。
* **`ex`**（オプション）：Cookie の有効期限が切れるまでの日数です。この引数が `0` であるまたは設定されていない場合、Cookie は訪問の終了時（無操作状態が 30 分間続く）に期限切れになります。

`vtp` 引数内の変数が設定されている場合、プラグインは Cookie を設定し、その Cookie の値を返します。`vtp` 引数内の変数が設定されていない場合、プラグインは Cookie の値のみを返します。

## 例

### 例 1

次のコードは、eVar21 を「hello」の値に設定します。次に、コードは「ev21gapv」Cookie を設定します。これは、28 日で有効期限が切れ、eVar21 の値（つまり「hello」）に等しくなります。次に、コードは eVar21 を「ev21gapv」Cookie の値と等しく設定（またはリセット）します。

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 2

eVar21 が現在のページに設定されていないが、過去 28 日間に前のページで「hello」に設定されたとします。次のコードは単に、eVar21 を「ev21gapv」Cookie の値（「hello」）と等しく設定します。関数が呼び出される前に eVar21 が現在のページに設定されていなかったので、「ev21gapv」Cookie はリセットされません。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 3

eVar21 が現在のページに設定されていないが、過去 28 日間に前のページで「hello」に設定されたとします。次のコードは単に、prop35 を「ev21gapv」Cookie の値（「hello」）と等しく設定します。eVar21 は設定されません。

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 4

次のコードは、eVar21 を「howdy」の値に設定します。次に、コードは「ev21gapv」Cookie を設定（またはリセット）します。28 日で有効期限が切れ、eVar21 の値（つまり「howdy」）に等しくなります。次に、コードは prop35 を「ev21gapv」Cookie の値（「howdy」）と等しく設定します。

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 5

s.eVar21 が過去 28 日間にどのページにも設定されていないとします。次のコードでは、s.eVar21 が nothing に設定されます。これは、「ev21gapv」Cookie が最後に設定されてから 28 日後に有効期限が切れたためです。

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### 例 6

次のコードは、eVar30 を「shopping」に設定します。次に、「s_gapv」Cookie を設定します。ブラウザーセッションの終了時に有効期限が切れ、s.eVar30 の値（「shopping」）と等しくなります。次に、s.eVar30 を「s_gapv」Cookie の値と等しく設定します（つまり、getAndPersistValue の呼び出しは s_gapv cookie の値を返します（この場合は「shopping」））。

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

s.eVar30 が、セッション中に閲覧された追加ページで明示的な値に設定されていないが、次のコードを介して（doPlugins 内で）設定される場合

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

s.eVar30 は「shopping」（つまり、「s_gapv」Cookie の持続値）に等しく設定されます。

## バージョン履歴

### 2.0（2018 年 4 月 17 日）

* ポイントリリース（コードサイズの縮小）
* `ex` 引数に 0 を渡すと、ブラウザーセッションの終わりではなく、無操作状態が 30 分続いた後に強制的に有効期限が切れるようになりました。

### 1.0（2016 年 1 月 19 日）

* 初回リリース。
