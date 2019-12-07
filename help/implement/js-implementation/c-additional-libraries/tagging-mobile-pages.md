---
description: モバイルトラッキングコードは、サーバー生成イメージタグの形式で、ページ上に配置されます。
keywords: Analytics Implementation;mobile tracking;mobile protocols;prevent caching;alt tag;default image type
title: モバイルプロトコルに対応するページタギング
topic: Developer and implementation
uuid: 5788beaf-f309-4918-a99c-a3e591668205
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# モバイルプロトコルに対応するページタギング

モバイルトラッキングコードは、サーバー生成イメージタグの形式で、ページ上に配置されます。

モバイルトラッキングコードは、サーバー生成イメージタグの形式で、ページ上に配置されます。一般的に、JavaScript や WMLScript などのスクリプト言語はモバイルデバイスではサポートされないので、スクリプト言語を使用してトラッキングビーコンを動的に生成することはできません。

モバイルビーコンイメージは実際には 2 x 2 pixel ですが、すべてのモバイルデバイスを確実にサポートするために、height プロパティと width プロパティを 5 に設定してください。以下に例を示します。

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## 乱数を使用したキャッシュの回避 {#section_BF5C344A16034C439C8704632CF673A7}

Adobe サーバーはトラッキングビーコンをキャッシュしないようにブラウザーに指示しますが、すべてのブラウザーでこの指示が有効なわけではありません。ビーコンがキャッシュされないようにするには、Web サーバーで動的に乱数を生成し、イメージ URL のパスに配置することを推奨します。これにより、レポートの精度が向上します。次に示すように、乱数はパスの最後のセクションに配置してください。

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## ALT タグの追加 {#section_FBD8B2FD1EA0429580C2B933DA300B07}

一部のモバイルブラウザーでは、すべてのイメージのイメージタグに alt テキストを追加する必要があります。イメージタグに ALT 属性を追加する方法を次に示します。

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

パスに必ず「/5/」を正しく含めることが重要です。これは、Adobe サーバーがモバイルデバイスを識別するために使用します。標準の「/1/」を使用する場合、Adobe サーバーはモバイルデバイスに対して cookie を設定しようとします。

## デフォルトのイメージタイプの変更 {#section_2F969909010D4A64BF6E092A32ABADB7}

特定のデバイスでデフォルトのイメージタイプがサポートされない場合、データは一切返されません。これを避けるために、アドビのデータ収集サーバーがそのモバイルデバイスでサポートされる特定のグラフィックタイプを返すように指定することができます。レポートスイート名の後のコードによってイメージタイプを指定します。

* `/5/` の場合、デフォルトのイメージタイプを返します。
* `/5.1/` または `/1/` の場合、常に GIF イメージを返します。

* `/5.5/` の場合、常に WBMP イメージを返します。

「[モバイルプロトコルを使用した訪問者の識別](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md)」を参照してください。
