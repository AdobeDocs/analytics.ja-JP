---
title: 再来訪頻度
description: 現在の訪問から前回の訪問までの時間をグループで示します。
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
TQID: https://experienceleague.adobe.com/k0H7kOCgrBRY3cZckPXaJ9UgLBPTYWHxKT8gzeMQjcI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
source-wordcount: '282'
ht-degree: 76%
---
# 再来訪頻度

「再訪問頻度」 [ ディメンション ](overview.md)は、再訪問者からの訪問の間を通過する時間を示します。 訪問者がサイトに戻ると、アドビは前回の訪問がどれくらい前かを確認し、そのヒットを適切なディメンション項目のバケットに割り当てます。 このディメンションは、訪問者に対する Web サイトのアピール度と関連性を経時的に測定するのに役立ちます。 また、サイトのコンテンツやプロモーションが訪問者に与える影響を識別するのにも役立ちます。

>[!TIP]
>
>このディメンションには、初回訪問者は含まれません。

## このディメンションへのデータ入力

Adobeでは、現在の訪問と訪問者の以前の訪問を比較することで、このディメンションをサーバーサイドで計算します。 設定する変数はありません。すべての実装に対してすぐに使用できます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 訪問 |

## ディメンション項目

ディメンション項目には、前回の訪問からの経過時間に応じて、時間ベースのグループが含まれます。

* 1 日未満
* 1 ～ 3 日
* 3 ～ 7 日
* 7 ～ 14 日
* 14 日～ 1 ヶ月
* 1 ヶ月以上

## ディメンション項目が、プロジェクトの日付範囲外のバケットに表示される場合があります

プロジェクトの日付範囲を設定すると、日付範囲外の訪問にディメンション項目が帰属して表示されることがよくあります。 例えば、訪問者が 7 月にサイトを訪問し、その後、9 月の同じ日に 2 回再訪問したとします。 9 月の再来訪頻度ディメンションでは、「1 か月以上」に 1 件の訪問、「1 日未満」に 1 件の訪問が表示されます。
