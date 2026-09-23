---
title: 出口ディメンション
description: 離脱ディメンションとその使用方法を一覧します。
keywords: 出口ページ、離脱サイトセクション、離脱サーバー、離脱カスタムインサイト
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 74%
---
# 出口ディメンション

>[!BEGINSHADEBOX]

*このヘルプページでは、終了が[&#x200B; ディメンション &#x200B;](overview.md)として機能する仕組みについて説明します。 出口が指標として機能する方法について詳しくは、[出口](../metrics/exits.md)指標を参照してください。*

>[!ENDSHADEBOX]

出口ディメンションは、最後のディメンション項目を記録し、訪問のすべてのヒットに遡って適用します。 出口ディメンションは、レポートスイート設定の「[トラフィック変数](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)」でパスが有効になっているすべての変数で使用できます。

## 離脱ディメンションへのデータでの入力

離脱ディメンションは、関連付けられたトラフィック変数に基づいています。 Adobeは、訪問中にその変数に対して最後に見られた値から各離脱ディメンションを導き出します。設定する専用の変数はありません。 非離脱変数にデータが含まれる場合は、関連する離脱ディメンションにもデータが含まれます。 トラフィック変数にデータが含まれる場合、離脱ディメンションに対して実装変更は必要ありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（訪問者の最後のヒットから派生） |
| **Web SDK / XDM フィールド** | なし（訪問者の最後のヒットから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 訪問 |

## ディメンション項目

離脱変数は通常、実装でのカスタム文字列に基づくので、どのディメンション項目にするかは組織側で決定します。 特定の離脱ディメンションの値は、関連付けられた非離脱ディメンションのディメンション項目と一致します。 例えば、「出口ページ」ディメンションのディメンション項目は、「ページ」ディメンションのディメンション項目と同様の値を含みます。
