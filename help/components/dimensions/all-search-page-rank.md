---
title: すべての検索ページのランク
description: 訪問者がサイトにクリックスルーした検索エンジンのページを特定します。
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '145'
ht-degree: 100%

---

# すべての検索ページのランク

「すべての検索ページランク」ディメンションは、訪問者がサイトにクリックスルーした検索結果のページを明らかにします。例えば、サイトが検索エンジンの検索結果の 2 ページ目に表示される場合、この変数のディメンション項目は「検索ページ 2」になります。

## このディメンションへのデータ入力

このディメンションが機能するには、レポートスイートに[内部 URL フィルター](/help/admin/admin/internal-url-filter-admin.md)が正しく設定されている必要があります。AppMeasurement は、実装コードを変更せずに、このディメンションを自動的に設定します。

## ディメンション項目

訪問者が検索エンジンからサイトにクリックスルーした場合、このディメンションの値は「検索ページ」にクリックスルーしたページ番号が続くものです。ヒットが検索エンジンから発生しない場合、このディメンションの値は「未指定」になります。
