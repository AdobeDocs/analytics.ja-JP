---
title: getNewRepeat
description: 新規訪問者とリピート訪問者のアクティビティを追跡します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getNewRepeat

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getNewRepeat` ラグインを使用すると、サイトの訪問者が新しい訪問者か、希望の日数内の再訪問者かを判断できます。 カスタム日数を使用して訪問者を「新規」として識別する場合は、このプラグインの使用をお勧めします。 Analysis Workspaceの新規/再訪問者ディメンションが組織のニーズを満たす場合、このプラグインは不要です。

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
   * アクションタイプ：getNewRepeatの初期化
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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getNewRepeat` ッドでは、次の引数を使用します。

* **`d`** （整数、オプション）:訪問者を再びリセットする訪問間隔の最小日数 `"New"`。 この引数を設定しない場合、デフォルトで30日に設定されます。

このメソッドは、プラグイ `"New"` ンによって設定されたcookieが存在しないか、有効期限が切れている場合の値を返します。 プラグインによって設定さ `"Repeat"` れたcookieが存在するかどうか、および現在のヒットからの経過時間とcookieに設定された時間が30分を超える場合の値を返します。 このメソッドは、訪問全体で同じ値を返します。

このプラグインは、引数と等しいとい `"s_nr[LENGTH]"` う名 `[LENGTH]` 前のcookieを使用し `d` ます。 Cookieには、現在時刻と訪問者の現在のステータス（または）を表すUnixタイムスタンプが含ま`"New"` れて `"Repeat"`います。

## 呼び出しの例

### 例1

次のコードでは、s.eVar1を新規訪問者の「新規」の値に設定し、s.eVar1を（新規呼び出しのたびに）そのサイトへの訪問の残りの部分の「新規」の値に設定し続けます。

```js
s.eVar1=s.getNewRepeat();
```

### 例2

訪問者が最後にs.getNewRepeat()が呼び出されてから31分から30日の間にサイトに戻ってきた場合、次のコードはs.eVar1を「Repeat」の値に設定し、s.eVar1を訪問者の残りの訪問全体で「Repeat」の値（新しい呼び出しごと）に設定します。

```js
s.eVar1=s.getNewRepeat();
```

### 例3

訪問者が最後にs.getNewRepeat()が呼び出されてから30日以上サイトを訪問していない場合、次のコードはs.eVar1を「New」の値に設定し、s.eVar1を（新しい呼び出しのたびに）その訪問者の残りの訪問全体で「New」の値に設定し続けます。

```js
s.eVar1=s.getNewRepeat();
```

### 例4

訪問者が最後にs.getNewRepeat()が呼び出されてから31分から365日（1年）たつたびにサイトに戻ってきた場合、次のコードはs.eVar1を「Repeat」の値に設定し、残りの期間中、s.eVar1を「Repeat」の値（新しい呼び出しごとに）に設定します訪問者のサイトへの訪問。

```js
s.eVar1=s.getNewRepeat(365);
```

### 例5

訪問者が最後にs.getNewRepeat()が呼び出されてから365日（1年）以上サイトを訪問していない場合、次のコードはs.eVar1を「New」の値に設定し、s.eVar1を残りの訪問者全体で「New」の値に設定し続けますサイトへの訪問。

```js
s.eVar1=s.getNewRepeat(365);
```

## バージョン履歴

### 2.1（2019年9月31日）

* JavaScriptロジックを再配置してプラグインサイズを削減

### 2.0（2018年4月17日）

* より小さいコードサイズで再コンパイル
* 訪問情報を保存するcookieの名前付け機能を削除しました。 プラグインは、引数に渡された値に基づいて、Cookieに動的に名前を付けるようになり `d` ました。
