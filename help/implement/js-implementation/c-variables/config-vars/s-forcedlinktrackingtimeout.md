---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.forcedLinkTrackingTimeout

 に渡された `s.tl`doneAction の実行前に、トラッキングの完了を待機する時間（ミリ秒）の最大値。この値によって、最大の待機時間が指定されます。このタイムアウトの前にリンクトラッキングが完了した場合は、doneAction が直ちに実行されます。リンクトラッキングが未完了になっている場合は、このタイムアウト時間を長くする必要があると考えられます。

デフォルト値= 250

例：`s.forcedLinkTrackingTimeout = 500`
