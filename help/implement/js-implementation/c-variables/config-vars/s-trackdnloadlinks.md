---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackDownLoadLinks

サイト上のダウンロード可能ファイルへのリンクを追跡する場合は、 を「true」に設定します。

If  is 'true,'  is used to determine which links are downloadable files.*`trackDownloadLinks`**`linkDownloadFileTypes`*

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

Folio Builder *`trackDownloadLinks`*&#x200B;サイトにダウンロード可能ファイルへのリンクがない場合、またはダウンロード可能ファイルのクリック数を追跡する必要がない場合は、trackDownloadLinks 変数を「false」に設定してください。If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. ダウンロードリンクで送信されるデータには、ダウンロードリンクの URL と、そのリンクの訪問者クリックマップ用のデータが含まれます。if *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

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

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.

* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.