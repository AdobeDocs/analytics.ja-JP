---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.forcedLinkTrackingTimeout

この値によって、最大の待機時間が指定されます。具体的には、`s.tl` に渡された `doneAction` の実行前に、トラッキングの完了を待機する時間（ミリ秒）の最大値を設定します。このタイムアウトの前にリンクトラッキングが完了した場合は、`doneAction` が直ちに実行されます。リンクトラッキングが未完了になっている場合は、このタイムアウト時間を長くする必要があると考えられます。

デフォルト値 = 250

例：`s.forcedLinkTrackingTimeout = 500`
