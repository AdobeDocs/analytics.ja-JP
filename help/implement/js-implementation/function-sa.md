---
description: s.sa() 関数を使用すると、ページ上のレポートスイートを、イメージリクエストが実行される前後いつでも動的に変更できます。
keywords: Analytics の導入
seo-description: s.sa() 関数を使用すると、ページ上のレポートスイートを、イメージリクエストが実行される前後いつでも動的に変更できます。
seo-title: s.sa() 関数
solution: Analytics
subtopic: 関数
title: s.sa() 関数
topic: 開発者と導入
uuid: a6aacd10-2a5b-448b- b3b7- bad5590b71d4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# s.sa() 関数

s.sa() 関数を使用すると、ページ上のレポートスイートを、イメージリクエストが実行される前後いつでも動的に変更できます。

ページをリロードせずに、様々なレポートスイートにデータを送信したい場合は、この関数の使用を強く推奨します。

この情報は、レポートと導入の両方に精通している上級ユーザー向けです。結果に関する十分な知識のない場合は、導入に編集を加えないでください。導入を変更する必要がある場合は、貴社のアカウントマネージャーにご連絡ください。

## 関数のプロパティ {#section_E10CB41A0CF749F4A24C8377958E3671}

この関数の設定では、事前に定義されていた変数がすべて使用され、それらの変数を異なるレポートスイートで使用することができます。

## 実装例 {#section_14B0B8C853244D5F82B08B995773640C}

1 つのレポートスイートにビデオデータを送り、別のレポートスイートにそれ以外のデータを送ります。

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

s.sa() とマルチスイートタギングを使用します。

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```

