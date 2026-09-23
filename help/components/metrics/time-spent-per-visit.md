---
title: 1訪問あたりの滞在時間（指標）
description: ディメンション項目の訪問別滞在時間。
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
TQID: https://experienceleague.adobe.com/X1RtHTTmu0VIblFC3jANE7d6bIbtm4W5OvqFZDp8bLE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 88%
---
# 訪問別滞在時間（秒）

>[!BEGINSHADEBOX]

*このヘルプページでは、「訪問別滞在時間」が指標としてどのように機能するかを説明します。 詳しくは、[訪問別滞在時間](../dimensions/time-spent-per-visit.md)ディメンションを参照してください。*

>[!ENDSHADEBOX]

「訪問あたりの滞在時間（秒）」 [指標](overview.md)は、各訪問で訪問者が特定のディメンション項目とやり取りする平均時間を示します。

この指標は、処理アーキテクチャが異なるので、Data Warehouse では使用できません。

## この指標の計算方法

この指標では [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)` の式が使用されます。

## 「平均サイト滞在時間」との比較

この指標と[サイトでの平均滞在時間](average-time-on-site.md)は似ていますが、いくつかの主な違いがあります。 どちらの指標も、分子として「合計滞在時間（秒）」を使用します。 ただし、「平均サイト滞在時間」では、ディメンション項目を含むシーケンスを分母として使用します。 訪問別滞在時間は、訪問回数を分母として使用します。

結果として、これらの指標は、訪問レベルでは似たような結果を生みますが、ヒットレベルでは異なります。

## 100% を超える割合

この指標には、100% を超える割合が頻繁に含まれます。 分母は、ディメンション全体の訪問別滞在時間で、分子はディメンション項目の訪問別滞在時間です。 ディメンション全体の訪問別滞在時間が、指定されたディメンション項目の訪問別滞在時間よりも小さい場合、100％を超える割合が表示されます。 この指標でランキングレポートを並べ替えると、訪問別滞在時間の値が表示されますが、これは通常有用ではありません。 ランキングレポートでは、[訪問回数](visits.md)など別の指標で並べ替えることをお勧めします。

滞在時間の一般情報について詳しくは、[滞在時間の概要](time-spent.md)を参照してください。
