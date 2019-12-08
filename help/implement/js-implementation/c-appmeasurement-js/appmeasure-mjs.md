---
description: JavaScript 版 AppMeasurement は s_code.js と同じ機能を提供する新しいライブラリですが、モバイルサイトとデスクトップサイトのどちらで使用してもより軽量で高速です。
keywords: appmeasurement;Analytics Implementation;javascript;appmeasurement for javascript;initialization;retrieve appmeasurement instance;clear vars;clearvars;appmeasurement utilities;appmeasurement instance;appmeasurement benefits
subtopic: JavaScript AppMeasurement
title: JavaScript 版 AppMeasurement について
topic: Developer and implementation
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript 版 AppMeasurement について

[!DNL AppMeasurement]JavaScript 版 は s_code.js と同じ機能を提供する新しいライブラリですが、モバイルサイトとデスクトップサイトのどちらで使用してもより軽量で高速です。

## 移行の前に知っておくべきこと {#section_B8E7B39E8469468883BA0B41234F21C4}

この新しい [!DNL AppMeasurement] のバージョンに切り替える前に理解しておくべき変更点について、以下の一覧に示します。

* 一部のプラグインはサポートされなくなりました。[AppMeasurement プラグインのサポート](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md)を参照してください。
* このライブラリは、動的なアカウント選択（[dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md)、[dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md)、および [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)）をサポートしていません。

* ライブラリとページコードを、`<head>` タグ内に配置できるようになりました。
* メディアモジュールおよび統合モジュールは、JavaScript [!DNL AppMeasurement] ダウンロードパッケージに含まれるバージョンを使用してください。Surveyモジュールはサポートされません。
* 既存のページコードは新しいバージョンと互換性があります。
* このライブラリは、クエリパラメーターの取得、cookie の読み取り／書き込み、高度なリンクトラッキングの実行のためのネイティブユーティリティを含みます。

## よくある質問 {#section_9BD41B08F7B54197B230937714B9357A}

パフォーマンス、ビデオトラッキング、モバイルなどについて詳しくは、[FAQ](/help/implement/faq.md) を参照してください。

## 初期化プロセス {#section_F6D5680F6D134B6AB1F01C6235860635}

[!DNL AppMeasurement]インスタンスを初期化するには、レポートスイート ID を渡して `s_gi()` を呼び出します。

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

`s_gi` を呼び出したときに、指定された `s_account` に対して [!DNL AppMeasurement] インスタンスが存在しない場合は、新しいインスタンスが作成されます。それ以外の場合は、既存のインスタンスが返されます。この機能により、同じアカウントに対して重複オブジェクトを作成しないようにすることができます。

## AppMeasurement インスタンスの取得 {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

コード全体で、グローバル [s_gi() 関数](/help/implement/js-implementation/function-s-gi.md)を呼び出して既存の [!DNL AppMeasurement] インスタンスを取得します。

## ユーティリティ {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] は、以下の組み込みのユーティリティを提供します。

* [Util.cookieRead](/help/implement/js-implementation/util-cookieread.md)
* [Util.cookieWrite](/help/implement/js-implementation/util-cookiewrite.md)
* [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md)

## 変数のクリア {#section_597C411E7EDB42BC9A6A0508C9D57147}

新しい `clearVars` メソッドを使用して、インスタンスオブジェクトから以下の値をクリアできます。

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

次に例を示します。

```js
s.clearVars()
```

## メリット {#section_091E5A28E89E438E8A54A95F55165743}

* H.25 コードと比較して 3 倍 ～ 7 倍も高速。
* わずか 21K の非圧縮コード、8K の gzip 圧縮コード（H.25 コードでは、33K もの非圧縮コード、13K の gzip 圧縮コード）。
* 一般的なプラグインの多くをネイティブサポート。
* モバイルサイトで使用できるほど軽量かつ高速で、フルデスクトップ Web で使用できるほど堅牢。1 つのライブラリを Web 環境全体で活用できます。

