---
title: ラストタッチチャネル
description: 訪問者のエンゲージメント有効期限内で最も新しいマーケティングチャネル。
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
TQID: https://experienceleague.adobe.com/wUNsv-0snBfk6EE6yeCEuT8-hGvBu9U8tjKDfxhVRA0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 49%
---
# ラストタッチチャネル

「ラストタッチチャネル」 [&#x200B; ディメンション &#x200B;](overview.md)は、訪問者のエンゲージメント期間中に訪問者が一致した最新のマーケティングチャネルをレポートします（デフォルトでは30日間）。 このディメンションは、コンバージョンにつながるトラフィックを貴社のサイトに導くマーケティングチャネルを把握するのに役立ち、最も効果的な分野でマーケティング活動に焦点を当てることができます。

## このディメンションへのデータ入力

このディメンションは、マーケティングチャネルの処理ルールによって導き出されます。 [&#x200B; マーケティングチャネルマネージャー](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)で定義したチャネル名を直接参照します。 すべてのヒットは、レポートスイートのマーケティングチャネル処理ルールを数値順に実行し、一致する結果が見つかるまで処理されます。これにより、そのマーケティングチャネルとヒットが関連付けられます。 設定する変数がありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（マーケティングチャネル処理ルールによって派生） |
| **Web SDK / XDM フィールド** | なし（マーケティングチャネル処理ルールによって派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 設定可能 |

ラストタッチチャネルは、訪問者が訪問者エンゲージメント期間（デフォルトでは 30 日）を超えてサイトを訪問しない限り維持されます。

このディメンションを特定の値に設定する場合は、次の手順を実行する必要があります。

* 「レポートスイートの設定」の下のマーケティングチャネルマネージャーで、目的のディメンション項目をチャネルとして設定します。
* ヒットに対する条件を含むマーケティングチャネル処理ルールを設定します。
* サイトへの訪問者のヒットは、マーケティングチャネル処理ルールで定義されている条件に一致している必要があります。

>[!TIP]
>
>[参加属性](/help/analyze/analysis-workspace/attribution/models.md)を使用する指標でこのディメンションを使用すると、他の属性モデルが使用しない場合、クレジットを`None`に属性できます。 参加指標でクレジットを受け取るには、レポートウィンドウ内のマーケティングチャネル [&#x200B; インスタンス &#x200B;](../metrics/instances.md)が必要です。 マーケティングチャネルが最初にレポートウィンドウの外に設定され、永続化された値のみがレポートウィンドウ内に存在する場合、参加指標はクレジットを`None`に属性します。 その他のアトリビューションモデルでは、クレジットを永続値に関連付けています。 このシナリオで`None`へのアトリビューションを避ける場合は、非参加アトリビューションモデルの使用を検討してください。

## ディメンション項目

ディメンション項目には、マーケティングチャネルマネージャー内の任意のチャネル名が含まれます。 デフォルトでは、`"Paid search"`、`"Natural search"`、`"Display"`、 `"Email"`、`"Affiliate"`、`"Direct"`、`"Internal"`、`"Social networks"`、`"Referring domains"`の値が含まれます。 マーケティングチャネルマネージャーでチャネルを追加または削除できます。これにより、このディメンションの値が変化します。
