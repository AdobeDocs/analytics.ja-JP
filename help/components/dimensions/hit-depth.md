---
title: ヒットの深さ
description: 訪問内のヒット数。
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
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
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
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
source-wordcount: '355'
ht-degree: 63%
---
# ヒットの深さ

「ヒットの深さ」の[&#x200B; ディメンション &#x200B;](overview.md)は、特定のヒットが訪問するまでの距離をレポートします。 このディメンションは、訪問者がサイト上でアクションを実行するのが訪問のどの時点かを把握するのに役立ちます。 ヒットの深さは、ページビュー（[`t()`](/help/implement/vars/functions/t-method.md)）およびリンクトラッキングヒット（[`tl()`](/help/implement/vars/functions/tl-method.md)）を含むすべてのタイプのヒットをカウントします。

## このディメンションへのデータ入力

Adobeは、各訪問のヒットの順序から、このディメンションをサーバーサイドで計算します。 設定する変数はありません。すべての実装に対してすぐに使用できます。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（Adobeで計算） |
| **Web SDK / XDM フィールド** | なし（Adobeで計算） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、`"Hit Depth"` 文字列の後に、訪問へのヒット数を表す数値が続きます。 `"Hit Depth 1"` ディメンション項目は訪問の最初のヒットを表し、`"Hit Depth 8"` ディメンション項目は訪問の 8 番目のヒットを表します。

>[!NOTE]
>
>Adobe Analyticsは、第2 レベルの精度でのみタイムスタンプを記録します。 同じタイムスタンプ秒を共有するヒットの場合、Adobeは、レポートに反映される順序がヒットが発生した順序と同じであることを保証できません。 ミリ秒レベルの精度が企業にとって優先事項である場合は、Customer Journey Analyticsの利用を検討してください。

## 訪問の深さとの比較

ヒットの深さでは、ページビューやリンクトラッキングのヒットなど、すべてのタイプのヒットがカウントされます。 訪問の深さは、ページビューのヒットに対してのみ増加します。_そして_、[ページ](page.md)ディメンションの項目が前のページの値と同じではありません。 また、訪問の深さは訪問ベースのディメンションです。つまり、訪問のすべてのヒットに対して同じ値になります。 次の表に、訪問の例と、ヒットの深さと訪問の深さをどのように考慮するかを示します。

| ページシーケンス | ヒットの深さ | 訪問の深さに対するカウント？ | 訪問の深さ |
| --- | --- | --- | --- |
| ホームページ | 1 | はい | 4 |
| 製品ページ | 2 | はい | 4 |
| ホームページ | 3 | はい | 4 |
| カスタムリンククリック | 4 | いいえ（カスタムリンク） | 4 |
| カスタムリンククリック | 5 | いいえ（カスタムリンク） | 4 |
| 製品ページ | 6 | ○ | 4 |
| カスタムリンククリック | 7 | いいえ（カスタムリンク） | 4 |
| 製品ページ | 8 | いいえ（前のページと同じ） | 4 |
