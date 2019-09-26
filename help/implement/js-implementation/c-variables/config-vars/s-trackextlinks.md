---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.trackExternalLinks

が「true」の場合、およびを使用して、クリックされたリンクが離脱リンクであるかどうかを判断します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

Folio Builder *`trackExternalLinks`*&#x200B;サイトに離脱リンクがない場合、または離脱リンクのクリック数を追跡する必要がない場合は、trackExternalLinks 変数を「false」に設定してください。出口リンクは、訪問者がサイトから出て行くすべてのリンクです。If *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. 離脱リンクで送信されるデータには、リンクの URL、リンク名、そのリンクの訪問者クリックマップ用のデータが含まれます。If *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

## 構文と可能な値

*`trackExternalLinks`変数には、「true」または「false」を設定する必要があります。*

```
js
s.trackExternalLinks=true|false
```

## 例

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## 設定

なし

## 注意事項、質問、ヒント

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.

* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).
