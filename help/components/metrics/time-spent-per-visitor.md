---
title: 訪問者別滞在時間（秒）
description: 「訪問者別滞在時間（秒）」指標は、訪問者の全期間に訪問者が特定のディメンション項目を操作した平均時間を示します。
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
TQID: https://experienceleague.adobe.com/NFmA2Q80h2WOTRwoJ882aFMG60y2HKngR0Ew0qnxb8o
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 182
ht-degree: 85%

---

# 訪問者別滞在時間（秒）

[!UICONTROL 訪問者あたりの滞在時間（秒） ] [指標](overview.md)は、訪問者のライフタイム全体で、訪問者が特定のディメンション項目とインタラクションする平均時間を示します。

この指標は、処理アーキテクチャが異なるので、Data Warehouse では使用できません。

## この指標の計算方法

この指標では数式 [`Total seconds spent`](total-seconds-spent.md)`divided by`[`Unique visitors`](unique-visitors.md) が使用されます。

## 100% を超える割合

この指標には、100% を超える割合が頻繁に含まれます。 分母は、ディメンションの訪問者別滞在時間全体を表し、分子は、ディメンション項目の訪問者別滞在時間を表します。 訪問者別のディメンションの滞在時間全体が、指定したディメンション項目の訪問者別滞在時間よりも小さい場合、100％を超える割合が表示されます。 この指標でランクレポートを並べ替えると、異常値ごとの滞在時間が訪問者値ごとに表示されますが、これは通常有用ではありません。 ランクレポートでは、[訪問回数](visits.md)など別の指標で並べ替えることをお勧めします。

滞在時間の一般情報について詳しくは、[滞在時間の概要](time-spent.md)を参照してください。
