---
description: Analytics 変数の長さは、HTML コードスニペット、JavaScript ライブラリファイル、イメージリクエストの各サイズに影響する場合があります。
keywords: Analytics の導入
seo-description: Analytics 変数の長さは、HTML コードスニペット、JavaScript ライブラリファイル、イメージリクエストの各サイズに影響する場合があります。
seo-title: 変数の長さ
solution: Analytics
subtopic: トラブルシューティング
title: 変数の長さ
topic: 開発者と導入
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 変数の長さ

Analytics 変数の長さは、HTML コードスニペット、JavaScript ライブラリファイル、イメージリクエストの各サイズに影響する場合があります。

長い変数（60 文字以上）を多数使用している場合、変数の値が短い識別子に置き換えられる場合があります。データ分類または VISTA ルールを使用して、その識別子をわかりやすい名前に変換することができます。

>[!NOTE]
>
>ほとんどのAnalytics変数は最大100文字です（eVarは最大255文字）。Internet Explorer では、GET イメージリクエストの URL 全体で最大 2,048 文字まで許可されます。イメージリクエストのサイズ制限は、変数だけでなく、ブラウザー、オペレーティングシステム、ブラウザープラグイン（Netscape／Mozilla のみ）に関する情報にも適用されます。

