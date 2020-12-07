---
title: JavaScript 版 AppMeasurement への移行
description: H コードから実装を移行するために必要な事項を決定します。
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 100%

---


# JavaScript 版 AppMeasurement への移行

実装で引き続き H コードを使用する場合は、AppMeasurement の最新バージョンに移行することを強くお勧めします。[Adobe Experience Platform Launch](../launch/overview.md) を使用した Analytics の実装をお勧めします。ただし、更新された JavaScript の実装を使用することもできます。

H コードと比較した場合、AppMeasurement には次の注目すべき変更が含まれています。

* H. コードと比較して 3 倍～7 倍も高速。
* H コードより軽い - 21kb 非圧縮コード（H コードは 33kb）。
* ライブラリとページコードを、`<head>` タグ内に配置できるようになりました。
* 既存のページレベルの H コードは、AppMeasurement と互換性があります。
* このライブラリは、クエリーパラメーターの取得、Cookie の読み取り／書き込み、高度なリンクトラッキングの実行のためのネイティブユーティリティを含みます。
* このライブラリでは、動的アカウント設定変数（`dynamicAccountSelection`、`dynamicAccountMatch`、`dynamicAccountList` など）はサポートされません。
* Survey モジュールはサポートされません。

次の手順は、一般的な移行ワークフローを示しています。

1. **新しい AppMeasurement ファイルをダウンロードします**：Adobe Analytics にログインし、管理者／Code Manager の順に移動して、新しいファイルにアクセスします。ダウンロードした圧縮ファイルには、`AppMeasurement.js` 縮小ファイルと、メディアモジュールおよび統合モジュールが含まれています。
1. **`s_code.js` のカスタマイズを`AppMeasurement.js`** にコピーします：`s_code.js` で `DO NOT ALTER ANYTHING BELOW THIS LINE` セクションの前にあるすべてのコードを `AppMeasurement.js` の先頭に移動します。
1. **すべてのプラグインを更新します**：`s_code.js` ファイルに一覧表示されているプラグインのそれぞれが最新バージョンを使用していることを確認します。これにはメディアモジュールと統合モジュールが含まれます。
1. **AppMeasurement.js ファイルをデプロイします**：`AppMeasurement.js` ファイルを Web サーバーにアップロードします。
1. **スクリプトの参照先を`AppMeasurement.js`** に更新します：すべてのページで、`s_code.js` ではなく `AppMeasurement.js` が参照されていることを確認します。

## Appmeasurement コードの例

一般的な `AppMeasurement.js` ファイル。設定変数が `doPlugins` 関数より前に設定されていることを確認します。

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
s.trackingServer="example.sc.adobedc.net";

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

各ページに `AppMeasurement.js` と `VisitorAPI.js` への参照が含まれていることも必ず確認してください。詳しくは、[JavaScript の実装](/help/implement/js/overview.md)を参照してください。
