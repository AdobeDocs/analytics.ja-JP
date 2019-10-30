---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.trackExternalLinks

「true」の場合、 および を使用して、クリックされたリンクが離脱リンクかどうかを判別します。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | True |

Folio Builder *`trackExternalLinks`*&#x200B;サイトに離脱リンクがない場合、または離脱リンクのクリック数を追跡する必要がない場合は、trackExternalLinks 変数を「false」に設定してください。出口リンクは、訪問者がサイトから出て行くすべてのリンクです。if *`trackExternalLinks`* が「true」の場合、離脱リンクをクリックすると、トラッキングデータが直ちに送信されます。離脱リンクで送信されるデータには、リンクの URL、リンク名、そのリンクの訪問者クリックマップ用のデータが含まれます。if *`trackExternalLinks`* が「false」の場合は、サイト上の離脱リンクの訪問者クリックマップ用のデータがレポートで少なくカウントされることがあります。

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

* *`trackExternalLinks`* が「false」の場合、訪問者がサイトから出て行くリンクは、訪問者クリップマップでのレポートで少なくカウントされることがあります。

* *`trackExternalLinks`* が「true」の場合、訪問者が離脱リンクをクリックするたびに、（リンクターゲットが読み込まれる前に）データが送信されます。
