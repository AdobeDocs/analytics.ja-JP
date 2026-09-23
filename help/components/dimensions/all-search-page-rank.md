---
title: すべての検索ページのランキング
description: 訪問者がサイトにクリックスルーした検索エンジンのページを特定します。
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 62%
---
# すべての検索ページのランキング

「すべての検索ページランク」 [ ディメンション ](overview.md)は、訪問者がクリックしてサイトにアクセスした検索結果のページをinsightに提供します。 例えば、サイトが検索エンジンの検索結果の 2 ページ目に表示される場合、この変数のディメンション項目は「検索ページ 2」になります。

## このディメンションへのデータ入力

Adobeは、このディメンションを各ヒットの検索エンジン [ リファラー](referrer.md)から取得し、訪問者がクリックした検索結果のページを判断します。 設定する変数がありません。 このディメンションが機能するには、レポートスイートに[内部 URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)が正しく設定されている必要があります。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（検索エンジンリファラーから派生） |
| **Web SDK / XDM フィールド** | なし（検索エンジンリファラーから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

訪問者が検索エンジンからサイトにクリックスルーした場合、このディメンションの値は「検索ページ」に続けて、クリックスルーしたページ番号になります。 ヒットが検索エンジンから発生しない場合、このディメンションの値は「未指定」になります。
