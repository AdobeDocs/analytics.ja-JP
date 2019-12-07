---
description: Analytics 変数の長さは、HTML コードスニペット、JavaScript ライブラリファイル、イメージリクエストの各サイズに影響する場合があります。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 変数の長さ
topic: Developer and implementation
uuid: 87deabb3-2acb-4797-9a65-769d9e2fbd62
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 変数の長さ

Analytics 変数の長さは、HTML コードスニペット、JavaScript ライブラリファイル、イメージリクエストの各サイズに影響する場合があります。

長い変数（60 文字以上）を多数使用している場合、変数の値が短い識別子に置き換えられる場合があります。データ分類または VISTA ルールを使用して、その識別子をわかりやすい名前に変換することができます。

> [!NOTE]ほとんどの Analytics 変数には、最大 100 文字（eVar では最大 255 文字）の制限があります。Internet Explorer では、GET イメージリクエストの URL 全体で最大 2,048 文字まで許可されます。イメージリクエストのサイズ制限は、変数だけでなく、ブラウザー、オペレーティングシステム、ブラウザープラグイン（Netscape／Mozilla のみ）に関する情報にも適用されます。

