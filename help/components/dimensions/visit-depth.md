---
title: 訪問の深さ
description: 訪問の深さをレポートする訪問ベースのディメンション。
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
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
source-wordcount: '209'
ht-degree: 68%
---
# 訪問の深さ

「訪問の深さ」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者が訪問全体で閲覧したページビュー数をレポートします。 訪問の深さは、ヒットがページビューで、[ページ](page.md)ディメンションが最後のページ表示のディメンション項目と同じでない場合にのみ増加します。 これは訪問ベースのディメンションで、訪問全体を通して同じ値が保持されます。 この変数は、訪問が終了した後に、その訪問内のすべてのヒットに対して設定されます。

## このディメンションへのデータ入力

Adobeは、各訪問のページビューから、このディメンションをサーバーサイドで計算します。 設定する変数はありません。すべての実装に対してすぐに使用できます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 訪問 |

## ディメンション項目

ディメンション項目には、`"Pages per visit"` 文字列の後に、訪問のページ数を表す数字が続きます。 `"Pages per visit: 1"` ディメンション項目は単一ページの訪問を表し、`"Pages per visit: 8"` ディメンション項目は 8 つのページビュー（および任意の数のリンクトラッキングコール）を持つ訪問を表します。

## ヒットの深さとの比較

ディメンション間の比較については、「[ヒットの深さ](hit-depth.md)」を参照してください。
