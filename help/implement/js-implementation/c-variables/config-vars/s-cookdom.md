---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics Implementation
solution: null
title: 動的変数
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomain

変数は、[!DNL Analytics] の Cookie である `s_cc` および `s_sq` を設定するドメインを決定します。

一般的に、`s.cookieDomainPeriods` は `window.location.hostname` から `s.cookieDomain` を生成するために使用されます。`s.cookieDomainPeriods` を使用する代わりに、`s.cookieDomain` を実装で使用するよう明示的に設定することもできます。例えば以下を使用して、ページの完全修飾名で Cookie を設定できます。

`s.cookieDomain = window.location.hostname;`
