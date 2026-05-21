---
title: すべての検索ページのランク
description: 訪問者がサイトにクリックスルーした検索エンジンのページを特定します。
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 146
ht-degree: 85%

---

# すべての検索ページのランク

「すべての検索ページランク」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者がクリックしてサイトにアクセスした検索結果のページをinsightに提供します。 例えば、サイトが検索エンジンの検索結果の 2 ページ目に表示される場合、この変数のディメンション項目は「検索ページ 2」になります。

## このディメンションへのデータ入力

このディメンションが機能するには、レポートスイートに[内部 URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)が正しく設定されている必要があります。 AppMeasurement は、実装コードを変更せずに、このディメンションを自動的に設定します。

## ディメンション項目

訪問者が検索エンジンからサイトにクリックスルーした場合、このディメンションの値は「検索ページ」にクリックスルーしたページ番号が続くものです。 ヒットが検索エンジンから発生しない場合、このディメンションの値は「未指定」になります。
