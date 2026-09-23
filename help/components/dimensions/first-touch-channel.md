---
title: ファーストタッチチャネル
description: 訪問者のエンゲージメント有効期限内で最初のマーケティングチャネル。
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
TQID: https://experienceleague.adobe.com/1XBUjwxlZXmhXJtQZgpv9yU5Fwhns-bb9Q7BcP5S30Q
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 67%
---
# ファーストタッチチャネル

「ファーストタッチチャネル」 [ ディメンション ](overview.md)は、訪問者のエンゲージメント期間中に訪問者が最初に一致したマーケティングチャネルをレポートします（デフォルトでは30日間）。 このディメンションは、最初のトラフィックを貴社のサイトにもたらすマーケティングチャネルを把握するのに役立ち、最も効果的な分野でマーケティング活動に焦点を当てることができます。

## このディメンションへのデータ入力

このディメンションは、マーケティングチャネルの処理ルールによって導き出されます。 [ マーケティングチャネルマネージャー](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md)で定義したチャネル名を直接参照します。 すべてのヒットは、レポートスイートのマーケティングチャネル処理ルールを数値順に実行し、一致する結果が見つかるまで処理されます。これにより、そのマーケティングチャネルとヒットが関連付けられます。 設定する変数がありません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（マーケティングチャネル処理ルールによって派生） |
| **Web SDK / XDM フィールド** | なし（マーケティングチャネル処理ルールによって派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 設定可能 |

ファーストタッチチャネルは、訪問者がサイトに 30 日（デフォルトの訪問者エンゲージメント期間）を超えて訪問しない状態にならない限り、維持されます。

このディメンションを特定の値に設定する場合は、次の手順を実行する必要があります。

* 「レポートスイートの設定」の下のマーケティングチャネルマネージャーで、目的のディメンション項目をチャネルとして設定します。
* ヒットに必要な条件を含むマーケティングチャネルの処理ルールを設定します。
* サイトに対する訪問者のヒットは、マーケティングチャネルの処理ルールで説明されている条件に一致する必要があります。 _そして_、訪問者のエンゲージメント期間内に最初に一致するマーケティングチャネルの値である必要があります。

後続のヒットが、別のマーケティングチャネルの条件と一致する場合、このディメンションは新しいマーケティングチャネルで上書きされません。

## ディメンション項目

ディメンション項目には、マーケティングチャネルマネージャー内の任意のチャネル名が含まれます。 デフォルトでは、`"Paid search"`、`"Natural search"`、`"Display"`、 `"Email"`、`"Affiliate"`、`"Direct"`、`"Internal"`、`"Social networks"`、`"Referring domains"`の値が含まれます。 マーケティングチャネルマネージャーでチャネルを追加または削除できます。これにより、このディメンションの値が変化します。
