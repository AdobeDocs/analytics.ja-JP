---
title: オリジナルの参照ドメイン
description: 訪問者がクリックスルーしてサイトにアクセスする前に閲覧していた最初の参照ドメイン。
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 72%
---
# オリジナルの参照ドメイン

「元の参照ドメイン」 [ ディメンション ](overview.md)は、訪問者がサイトに到達するためにクリックした最初の参照ドメインを報告します。 一度設定されると、その訪問者 ID の全期間を通じて同じ値が保持されます。 このディメンションは、どのサードパーティサイトが元々サイトへのトラフィックを促進しているかを把握するのに役立ちます。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの[内部 URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)を設定する必要があります。 内部 URL フィルターを設定しないと、内部ドメインが含まれるか、外部ドメインが表示されない可能性があります。

## このディメンションへのデータ入力

Adobeは、訪問者の最初の[ リファラー](referrer.md)からこのディメンションを取得し、そのリファラーURLのドメイン部分を使用します。 設定する変数がありません。 レポートスイートの[内部URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)を設定する必要があります。設定に失敗すると、内部ドメインが含まれるか、外部ドメインが表示されない可能性があります。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（訪問者の最初のリファラーから派生） |
| **Web SDK / XDM フィールド** | なし（訪問者の最初のリファラーから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 訪問者 |

訪問者がサイトを離れ、その後いつでも別のドメイン上のリンクをクリックスルーしても、新しい値は記録されません。 新しい値を表示するには、[参照ドメイン ](referring-domain.md)を参照してください。

## ディメンション項目

ディメンション項目には、訪問者がサイトにクリックスルーしたドメインが含まれます。 ヒットにリファラーデータがない（設定または持続的な）場合は、ディメンション項目 `"None"` でグループ化されます。 このディメンション項目は、訪問者がブラウザーのアドレスを手動でアドレスバーに入力したか、ブックマークをクリックしたなど、リファラー値がなかったことを意味します。

## 参照ドメインとオリジナルの参照ドメインの比較

参照ドメインは訪問間で変化する可能性があります。 例えば、訪問者が `google.com` 経由でサイトに到達し、その 1 週間後に `twitter.com` 経由でサイトに到達したとします。 訪問者は、最終的にはサイトで購入します。 ラストタッチ属性を持つディメンションとして参照ドメインを使用している場合、`twitter.com` は購入のクレジットを受け取ります。 オリジナルの参照ドメインをディメンションとして使用している場合、アトリビューションモデルに関係なく、`google.com` が購入のクレジットを受け取ります。

オリジナルの参照ドメインは、特定の訪問者 ID の全期間を通して変更されません。
