---
description: s.t() 関数は、対象のページに定義されているすべての変数をイメージリクエストにまとめて、Adobe サーバーに送信します。
keywords: track;Analyticsの導入;ページトラッキング;トラックページ
seo-description: s.t() 関数は、対象のページに定義されているすべての変数をイメージリクエストにまとめて、Adobe サーバーに送信します。
seo-title: s.t() 関数 - ページトラッキング
solution: Analytics
subtopic: 関数
title: s.t() 関数 - ページトラッキング
topic: 開発者と導入
uuid: 67696e46-1e0d-4200- bfad-4217d1023948
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# s.t() 関数 - ページトラッキング

s.t() 関数は、対象のページに定義されているすべての変数をイメージリクエストにまとめて、Adobe サーバーに送信します。

## 関数のプロパティ {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* [!UICONTROL s.t()] の呼び出しを削除すると、データが [!DNL Analytics] に送信されなくなります。複数の [!UICONTROL s.t()] の呼び出しを使用すると、複数のイメージリクエストが実行されます（サイトでレポートされるトラフィックが 2 倍になります）。

* 1 回のページ読み込みで複数のイメージリクエストを実行する場合は、[!UICONTROL s.tl()] 関数を使用することを推奨します。
* この関数をトリガーすると、常に[!UICONTROL ページビュー数]が増加し、[!UICONTROL s.pageName] 変数が含まれます。

## 導入 {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

[!UICONTROL コードマネージャー]内でコードを生成すると、ページコードの末尾は次のようになります。

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 
```

コードの各行にはそれぞれ特定の目的があります。

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

このコード行によって、JavaScript 関数が実行されます。[!UICONTROL s_code] 変数とそれに続く document.write メソッドは、イメージオブジェクトをサポートしないブラウザー（バージョン 3 より前の Netscape ブラウザーおよびバージョン 4 より前の Internet Explorer。これらのブラウザーを使用しているのは、全インターネットユーザーの 0.5 ％未満と推測されます）に対して実行されます。

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

[!UICONTROL s.t()] 関数に関するその他の質問については、貴社のアカウントマネージャーにお問い合わせください。アカウントマネージャーがアドビ導入コンサルタントとのミーティングを設定し、導入コンサルタントがサポートを行うことができます。
