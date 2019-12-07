---
description: AJAX による導入は、標準的な HTML ページ上にコードを導入することと非常によく似ています。
keywords: Analytics Implementation
title: AJAX による実装
topic: Developer and implementation
uuid: 9e3477ef-7dea-4c76-ab61-36a188222be7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# AJAX による実装

AJAX による導入は、標準的な HTML ページ上にコードを導入することと非常によく似ています。

ビジネスには答えを必要とする問題があり、必要性の評価と変数の割り当てをおこないます。次に設計を適用し、導入します。既に導入の初期段階を経験していれば、このような考え方を理解できるでしょう。

## ソリューションの設計 {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

[!UICONTROL AJAX] を混在させるときの違いは、収集する必要のある詳細のレベルをまず理解することです。ページ（マクロレベル）上でのコンテンツ変更またはアプリケーション（マイクロレベル）のトラッキング属性の変更によって、どの変数を設定すべきか、およびアドビへのデータ送信方法としてどの方式が最善かが決まります。

## コードの導入 {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

JavaScript コードにはデータを送信できる関数が 2 つあります。データ送信に使用する方法を知るために従うべきガイドラインがいくつかあります。同じページ上で既にイメージリクエストが実行されていた場合、まず設定済み変数の値をクリアする必要があります。JavaScript 版 [!DNL AppMeasurement] で `clearVars()` 関数を使用するか、H コードを使用している場合は変数をクリアする簡単な JavaScript 関数を記述します。次に、変更されたコンテンツ（*`pageName`* 変数）に適切な値を設定します。変数を設定した後、*`t()`* 関数を呼び出します。

> [!NOTE]`s.t()` を呼び出す前に、残したくない s オブジェクトの値をすべてクリアする必要があります。JavaScript 版 [!DNL AppMeasurement] を使用している場合は、`s.clearVars()` を呼び出すことができます。H コードを使用している場合は、変数を空の文字列に設定する簡単なルーチンを記述します。

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

以下の例では、JQuery `.ajax` 関数の `done` コールバックでのトラッキングコールを示しています。

```
$.ajax({ 
  url: "test.html", 
  dataType: "html" 
}) 
  .done(function( response ) { 
    $( "#content" ).html( response ); 
  s.clearVars(); 
  s.pageName = $( "h1:first" ).text(); 
  s.t(); 
  }); 
```

同じページ上で既にイメージリクエストが実行されていた場合、まずは設定済み変数の値をクリアします。これは、以下の方法で実行できます。

* 簡単な JavaScript 関数を作成して、アドビの変数をクリアします。
* 設定する&#x200B;*`linkTrackVars`* および *`linkTrackEvents`* 変数を設定します（[!DNL s_code.js] ファイル内でまだ設定していない場合）。

* 次に、変更されたコンテンツ（*`pageName`* 変数）に適切な値を設定します。
* 変数を設定した後、*`tl()`* 関数を呼び出します。

```js
//set linkTrackVars and linkTrackEvents> (if applicable) 
//set new variables 
s.tl(this,'o','Link Name');
```

```js
s.linkTrackVars="prop1,eVar1,events"; s.linkTrackEvents="event1"; 
s.prop1="some value"; s.eVar1="another value"; s.events="event1"; 
s.tl(this,'o','My Link Name');
```

