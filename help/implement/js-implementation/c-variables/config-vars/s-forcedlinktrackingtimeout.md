---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.forcedLinkTrackingTimeout

この値によって、最大の待機時間が指定されます。Specifically, it sets the maximum number of milliseconds to wait for tracking to finish before performing the `doneAction` that was passed into `s.tl`. このタイムアウトの前にリンクトラッキングが完了した場合は、`doneAction` が直ちに実行されます。リンクトラッキングが未完了になっている場合は、このタイムアウト時間を長くする必要があると考えられます。

デフォルト値= 250

例：`s.forcedLinkTrackingTimeout = 500`
