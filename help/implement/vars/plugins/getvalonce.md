---
title: getValOnce
description: Analytics変数が1行に2回同じ値に設定されないようにします。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getValOnce

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getValOnce` ラグインは、変数が同じ値に複数回設定されるのを防ぎます。 訪問者がページを更新した場合や、特定のページを複数回訪問した場合の重複を排除する場合は、このプラグインを使用することをお勧めします。 Analysis Workspaceの「回数」指標について心配しない場合は、このプラグインは不要です。

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
   * アクションタイプ：getValOnceの初期化
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
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getValOnce` ッドでは、次の引数を使用します。

* **`vtc`** （必須、文字列）:以前に同じ値に設定されていたかどうかを確認する変数
* **`cn`** （オプション、文字列）:確認する値を保持するcookieの名前。 デフォルトは `"s_gvo"`
* **`et`** （オプション、整数）:cookieの有効期限（日単位、または引数に応じて分単位） `ep` です。 デフォルト `0`はに設定され、ブラウザーセッションの終了時に有効期限が切れます。
* **`ep`** （オプション、文字列）:引数も設定されている場合にのみ、 `et` この引数を設定します。 引数の有効期限を日 `"m"` 数ではなく分単位で切 `et` れるようにする場合は、この引数をに設定します。 デフォルト `"d"`は日単位で引数を設 `et` 定する値です。

引数とcookie `vtc` の値が一致する場合、このメソッドは空の文字列を返します。 引数と `vtc` cookieの値が一致しない場合、このメソッドは引数を文字列 `vtc` として返します。

## 呼び出しの例

### 例1

この呼び出しを使用して、同じ値が次の30日間連続で複数回s.campaignに渡されないようにします。

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

上記の呼び出しでは、プラグインはまず、s_campaign cookieに既に含まれている値と、現在のs.campaign変数から取得されている値を比較します。   一致が行われない場合、s_campaign cookieはs.campaignの新しい値と同じに設定され、新しい値が返されます。   この比較は今後30日間行われる

### 例2

この呼び出しを使用して、セッション全体で同じ値が設定されないようにします。

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

このコードを使用すると、同じ値がユーザーのセッション中に1行に複数回s.eVar2に渡されるのを防ぐことができます。  また、有効期限が0に設定されているので、引数（呼び出しの最後）の「m」値も無視します。   また、比較値がs_ev2 cookieに保存されます。

## バージョン履歴

### 2.0

* ポイントリリース（再コンパイルされ、コードサイズが小さくなりました）。

### 1.1

* パラメーターを使用して、有効期限の分または日を選択するオプションを追加し `t` ました。
* プラグインのみに制限す `k` るために使用する変数のスコープを修正しました。 この変更により、ページ上の他のコードとの干渉が発生する可能性を回避できます。
