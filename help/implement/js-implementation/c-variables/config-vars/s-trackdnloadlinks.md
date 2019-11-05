---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.trackDownLoadLinks

サイト上のダウンロード可能ファイルへのリンクを追跡する場合は、 を「true」に設定します。

*`trackDownloadLinks`* が「true」の場合は、どのリンクがダウンロード可能ファイルかを判断するために *`linkDownloadFileTypes`* を使用します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

Folio Builder *`trackDownloadLinks`*&#x200B;サイトにダウンロード可能ファイルへのリンクがない場合、またはダウンロード可能ファイルのクリック数を追跡する必要がない場合は、trackDownloadLinks 変数を「false」に設定してください。*`trackDownloadLinks`* が「true」の場合は、ファイルのダウンロードリンクがクリックされると、データが直ちに [!DNL Analytics] に送信されます。ダウンロードリンクで送信されるデータには、ダウンロードリンクの URL と、そのリンクの訪問者クリックマップ用のデータが含まれます。if *`trackDownloadLinks`* が「false」の場合は、サイト上のダウンロード可能ファイルへのリンクの訪問者クリックマップ用のデータがレポートで少なくカウントされることがあります。

## 構文と可能な値

*`trackDownloadLinks`変数には、「true」または「false」を設定する必要があります。*

## 例

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## 設定

なし

## 注意事項、質問、ヒント

* *`trackDownloadLinks`* が「false」の場合は、ユーザーがサイト上でファイルのダウンロードに使用するリンクの数が、訪問者クリックマップでのレポートで少なくカウントされることがあります。

* *`trackDownloadLinks`* が「true」の場合は、訪問者がファイルのダウンロードリンクをクリックするたびにデータが送信されます。
