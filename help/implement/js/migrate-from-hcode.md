---
title: JavaScript 版 AppMeasurement への移行
description: Hコードから実装を移行するために必要な事項を決定します。
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# JavaScript 版 AppMeasurement への移行

導入で引き続きHコードを使用する場合は、AppMeasurementの最新バージョンに移行することを強くお勧めします。 Adobe Experience Platform Launchを使用したAnalytics [の導入をお勧めします](../launch/overview.md) 。ただし、更新されたJavaScriptの実装を使用することもできます。

Hコードと比較した場合、AppMeasurementには次の点に注目すべき変更が含まれています。

* Hコードと比べて3倍～ 7倍高速
* Hコードより軽い — 21 KB非圧縮コードとHコード（非圧縮時は33 KB）。
* ライブラリとページコードを、`<head>` タグ内に配置できるようになりました。
* 既存のページレベルのHコードは、AppMeasurementと互換性があります。
* このライブラリは、クエリパラメーターの取得、cookie の読み取り／書き込み、高度なリンクトラッキングの実行のためのネイティブユーティリティを含みます。
* このライブラリは、動的アカウント設定変数（、およびを含む） `dynamicAccountSelection`をサポ `dynamicAccountMatch`ートしてい `dynamicAccountList`ません。
* Surveyモジュールはサポートされません。

次の手順は、一般的な移行ワークフローを示しています。

1. **新しいAppMeasurementファイルのダウンロード**:Adobe Analyticsにログインし、管理者/コードマネージャーに移動して、新しいファイルにアクセスします。 ダウンロードした圧縮ファイルには、縮小ファイルと `AppMeasurement.js` 、メディアモジュールおよび統合モジュールが含まれています。
1. **カスタマイズのコ`s_code.js``AppMeasurement.js`**ピー先：セクションの前にあるすべてのコ`DO NOT ALTER ANYTHING BELOW THIS LINE`ードをの先`s_code.js`頭に移動します`AppMeasurement.js`。
1. **すべてのプラグインを更新**:ファイルに一覧表示されている各プラグインの最新バージョンを使用していることを確認し `s_code.js` ます。 これにはメディアモジュールと統合モジュールが含まれます。
1. **AppMeasurement.jsファイルをデプロイします**。ファイルをWebサ `AppMeasurement.js` ーバーにアップロードします。
1. **参照先のスクリプトを更新しま`AppMeasurement.js`**す：すべてのページが、ではなく参照されてい`AppMeasurement.js`ることを確認しま`s_code.js`す。

## Appmeasurementコードの例

一般的なファ `AppMeasurement.js` イル。 設定変数が関数の上に設定されていることを確認し `doPlugins` ます。

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your account manager.*/
s.trackingServer="example.sc.omtrdc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## ページコードの例

各ページに読み込まれる一般的なコード。

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

各ページに `AppMeasurement.js` と `VisitorAPI.js` への参照が含まれていることも必ず確認してください。詳しくは [、「JavaScriptの実装](/help/implement/js/overview.md) 」を参照してください。
