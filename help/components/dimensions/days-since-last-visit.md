---
title: 最終訪問からの日数
description: 現在のヒットから最終訪問までの日数。
feature: Dimensions
exl-id: 8063bdc6-516a-4dd0-a4ca-ded739e8d406
TQID: https://experienceleague.adobe.com/VOkdvehFSgp1xBEq49W5FIphzHi8ZCbrsoMnI7rgQMs
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
source-wordcount: '206'
ht-degree: 57%
---
# 最終訪問からの日数

「前回の訪問からの日数」 [ ディメンション ](overview.md)は、訪問者の現在のヒットから前回の訪問までの経過時間（訪問がある場合）を測定します。 このディメンションは、サイトの訪問後に訪問者が行う行動を把握するのに役立ちます。 以下に例を示します。

* ユーザーはどのぐらいの頻度でサイトを再訪問しているか。
* 返品頻度とコンバージョンとの相関関係？ リピート購入者は頻繁に訪問しますか？
* キャンペーンでクリックスルーしたユーザーは頻繁に訪問するか。

初回訪問者は、このディメンションには含まれません。

## このディメンションへのデータ入力

Adobeは、訪問者の訪問履歴から、このディメンションをサーバーサイドで計算します。 設定する変数はありません。すべての実装に対してすぐに使用できます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、訪問者の最終訪問から現在のヒットまでの日数が含まれます。 各日数は個別のディメンション項目です。`"Same day"` は、訪問者の最後の訪問と現在のヒットが同じ日に発生した場合に発生します。
