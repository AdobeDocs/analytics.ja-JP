---
title: Data Warehouse セグメントの互換性
description: Data Warehouseで使用できるセグメント定義について説明します。
feature: Data Warehouse
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 456
ht-degree: 9%

---

# Data Warehouse セグメントの互換性

セグメントビルダーで構築されたすべてのセグメントをData Warehouseで使用できるわけではありません。 このページでは、Data Warehouseと互換性のあるセグメント定義について説明します。これにより、[Data Warehouse リクエストを作成する](/help/export/data-warehouse/create-request/t-dw-create-request.md)際に選択できるようになります。

セグメントは、次の&#x200B;**両方**&#x200B;がtrueの場合にのみData Warehouseと互換性があります。

* **サポートされているコンポーネント**: セグメントは、Data Warehouseがサポートするディメンションと指標のみを使用します。
* **サポートされている構造**: セグメントの構造は、Data Warehouseが適用するルールに従っています。

いずれかの条件が満たされない場合、Data Warehouse リクエストを作成する際にセグメントがオプションとして表示されず、互換性のないセグメントを含むバーチャルレポートスイートを選択するとエラーが表示されます。

## サポートされているコンポーネント

セグメントは、適用されたリクエストと同じデータに対して評価されるので、**Data Warehouse リクエストでサポートされていないコンポーネントもセグメントでサポートされていません。** Data Warehouseがサポートしていないディメンションと指標の完全なリストについては、[Data Warehouseでのコンポーネントのサポート ](component-support.md)を参照してください。

[ コンポーネントサポート ](component-support.md)に記載されているディメンションと指標に加えて、次のディメンションはData Warehouse *リクエスト*&#x200B;で使用できますが、**はセグメント定義**&#x200B;内で使用できません。

* [[!UICONTROL 月間通算日]](/help/components/dimensions/day-of-month.md)
* [[!UICONTROL 曜日]](/help/components/dimensions/day-of-week.md)
* [[!UICONTROL 年間通算日]](/help/components/dimensions/day-of-year.md)
* [[!UICONTROL 時間帯]](/help/components/dimensions/hour-of-day.md)
* [[!UICONTROL  マーケティングチャネル ]](/help/components/dimensions/marketing-channel.md) （代わりに[[!UICONTROL  ラストタッチチャネル ]](/help/components/dimensions/last-touch-channel.md)を使用）
* [[!UICONTROL 年間通算月]](/help/components/dimensions/month-of-year.md)
* [[!UICONTROL  ページが見つかりません]](/help/components/dimensions/pages-not-found.md) （代わりに[[!UICONTROL  ページタイプエラー]](/help/components/dimensions/pages-not-found.md)を使用）
* [[!UICONTROL 四半期]](/help/components/dimensions/quarter-of-year.md)
* [[!UICONTROL 平日／週末]](/help/components/dimensions/weekday-weekend.md)

## サポートされる構造

サポートされているコンポーネントのみを使用するセグメントであっても、その構造はData Warehouseが適用するルールに従う必要があります。 セグメント構造は、完全にサポートされているか、部分的にサポートされているか、サポートされていません。

**サポートされている**:

* **セグメントスタック**:1つのData Warehouse リクエストに複数のセグメントを適用できます。
* **ネストされたコンテナ**：サポートされている、提供されたスコープは各レベルで減少します（訪問者→訪問→ヒット）。 スコープを増やすコンテナはサポートされていません。

**部分的にサポートされています**:

* **コンテナを除外**：最上位レベルでのみサポートされます。 Data Warehouseでは、`A AND NOT B`として表現可能なセグメントのみがサポートされています。つまり、**この特性を含める**&#x200B;および&#x200B;**この特性を除外する**。 他のコンテナ内にネストされた除外コンテナはサポートされていません。
* **AND/OR ロジック**：制限付きでサポートされています。 `exclusion`または`without` コンテナをAND/OR ロジックと組み合わせて使用する場合、`A AND NOT B`として書き換えることができるセグメントのみがサポートされます。

**サポートされていません**:

* **シーケンシャルセグメント**: THEN演算子を使用して順序付き訪問者ナビゲーションシーケンスを定義するセグメントはサポートされていません。
* **「次のいずれかに等しい」演算子および「次のいずれかに等しくない」演算子**：これらの演算子は、Data Warehouse セグメントではサポートされていません。

## ディメンションとして使用されるセグメント

Data Warehouse レポートでセグメントをディメンションとして使用すると、レポートは`"0"`または`"1"`を含む列を返します。

* **`"0"`**：ディメンション項目がセグメントの条件を満たしていません。
* **`"1"`**：ディメンション項目がセグメントの条件を満たしています。
