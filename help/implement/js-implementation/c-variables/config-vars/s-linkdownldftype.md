---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.linkDownloadFileTypes

 変数は、コンマで区切られたファイル拡張子のリストです。

サイトにこれらの拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクがクリックされた場合にその URL が[!UICONTROL ファイルのダウンロード数]レポートに表示されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|--- |--- |--- |--- |
| 該当なし | 該当なし | トラフィック／サイトトラフィック／ファイルのダウンロード数 | "exe、zip、wav、mp3、mov、mpg、avi、wmv、doc、pdf、xls" |

Folio Builder *`linkDownloadFileTypes`* 変数は、*`trackDownloadLinks`* が「True」に設定されている場合にのみ関係します。

リンク上でマウスを左クリックした場合にのみ、[!UICONTROL ファイルのダウンロード数]レポートでカウントされます。ページが読み込まれたときに自動的に開始されるファイルダウンロード、またはリダイレクトの後で実行されるファイルダウンロードはすべて、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。ファイルを右クリックし「対象をファイルに保存」オプションを選択した場合も、[!UICONTROL ファイルのダウンロード数]レポートではカウントされません。

Folio Builder *`linkDownloadFileTypes`* 変数は、RSS フィードに対するクリック数を追跡するために使用することができます。.xml または他の拡張子を持つ RSS フィードへのリンクがある場合は、*`linkDownloadFileTypes`* リストに「,xml」を追加すると、各 RSS リンクのクリック回数を確認できます。

## 構文と可能な値

ファイル拡張子のみ含めます（スペースなし）。

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

リストにはどのようなファイル拡張子でも含めることができます。htm や aspx のような一般的なファイル拡張子は、*`linkDownloadFileTypes`* と呼ばれる iFrame を読み込みます。これらの拡張子を含めると、クリックごとに余分なイメージリクエストが送信されることになり、これはプライマリサーバーコールとして請求されます。

## 例

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## 設定*

なし

## 注意事項、質問、ヒント

* ダウンロードファイルを左クリックした場合のみ、URL が[!UICONTROL ファイルのダウンロード数レポート]に表示されます。
* 共通のファイル拡張子を&#x200B;*`linkDownloadFileTypes`* に一般的なファイル拡張子を含めると、Adobe のサーバーに送信されるサーバーコール総数が大幅に増えることがあります。
* サーバーサイドでのリダイレクトへのリンクやファイルのダウンロードを自動的に開始する HTML ページはカウントされません（ファイル拡張子が *`linkDownloadFileTypes`* の場合を除く）。
* JavaScript（javascript:openLink( ) など）を使用するリンクは、ファイルのダウンロード数にはカウントされません。
