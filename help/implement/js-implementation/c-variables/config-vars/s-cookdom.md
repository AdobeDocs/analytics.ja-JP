---
description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
keywords: Analytics の実装
seo-description: 動的変数を使用すると、サイトのイメージリクエストで完全な値を複数回入力することなく、ある変数の値を別の変数にコピーできます。
solution: null
title: 動的変数
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieDomain

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

一般に、は `s.cookieDomainPeriods` から生成するために使 `s.cookieDomain` 用されま `window.location.hostname`す。 を使用する代 `s.cookieDomainPeriods`わりに、実装で使用する `s.cookieDomain` ものを明示的に設定できます。 例えば以下を使用して、ページの完全修飾名で Cookie を設定できます。

`s.cookieDomain = window.location.hostname;`
