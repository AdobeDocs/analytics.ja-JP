---
title: Activity Map 地域
description: クリックされたサイト上の地域。
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
TQID: https://experienceleague.adobe.com/mmLp5-dgKGeovIOMPZxliyhfbpUSMLXca-3Qs6QA0SA
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
source-wordcount: '286'
ht-degree: 7%
---
# Activity Map 地域

「Activity Map リージョン」 [ ディメンション ](overview.md)には、サイト上で最もクリックされたリージョンが表示されます。 このディメンションは、個々のリンクではなく、サイト全体のクリック数を比較したい場合に便利です。 また、動的なコンテンツを提供する領域にも役立ちます。 例えば、回転するニュース記事を含むフロントページがある場合、リンクテキストが常に変更されるため、[Activity Map Link](activity-map-link.md) ディメンションの使用は困難になります。 ただし、これらのリンクは同じ領域を使用するため、個々のリンクが毎日変更される場合でも、その領域のパフォーマンスを分析できます。

## このディメンションにデータを入力

このディメンションは、[ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`からデータを取得します。 実装で[Activity Map](/help/analyze/activity-map/overview.md)を使用している場合、このコンテキストデータ変数は、リンクがクリックされたときにデータを自動的に収集します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（[Activity Map](/help/analyze/activity-map/overview.md) モジュールによって収集） |
| **Web SDK / XDM フィールド** | なし（[Activity Map](/help/analyze/activity-map/overview.md) モジュールによって収集） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 255 バイト |
| **永続性** | 該当なし |

クリックされた特定のリンクの場合、親のDOM要素で次の（順番に）を確認します。

* [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md)によって設定された属性内の値。デフォルトでは`id`属性に設定されます
* 属性`role="region"`の場合の`aria-label`属性の値
* セマンティック要素`<header>`、`<main>`、`<footer>`または`<nav>` （Web SDKのみ）

親DOM要素が上記の条件のいずれも満たさない場合、検索は繰り返しDOM階層を上に進みます。 一致する要素が見つからない場合は、値`BODY`が返されます。

## ディメンション項目

Dimensionのアイテムには、サイトにラベル付けしたリージョンが含まれます。 特定のリージョン値は、使用される属性と、セマンティック HTML要素が存在するかどうかに応じて異なります。
