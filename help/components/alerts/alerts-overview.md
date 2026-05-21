---
description: アラートを使用して、通知をきめ細かく制御したり、異常値検出と統合したりする方法について説明します。
title: アラートの概要
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
TQID: https://experienceleague.adobe.com/FDzJzBjxMc-EkhW0k0NiENt-g53sRnzXQDs1XQWFseI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 53%

---

# アラートの概要

Adobe Analytics のアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受信できます。

また、Adobe Analytics パッケージに応じて、異常しきい値に基づいてトリガーされるアラートを使用することもできます。 これらのアラート（*インテリジェントアラート*&#x200B;とも呼ばれます）は、[異常値検出](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)と統合する詳細な制御を提供し、最も必要なときにトリガーします。

アラートを使用すると、次のことができます。

* アラートトリガーの頻度をプレビューします。
* 自動生成される Analysis Workspace プロジェクトへのリンクが記載された電子メールまたは SMS によるアラートの送信。
* 1つのアラートで複数の指標をキャプチャする&#x200B;*積み重ね* アラートを作成します。
* 以下にもとづいてアラートを作成します。
   * 存在する指標の異常値は、予想しきい値を超えているか、下回っています。

     [異常値検出](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)は、過去のデータを使用して、期待値に上限と下限を加えた値を構築します。 実際の指標の値が上限を超えているか、しきい値として定義されている下限を下回っている場合、そのイベントは、しきい値の信頼性レベルで異常値とみなされ、アラートがトリガーされます。 しきい値が高い（例：99%または99.9%）場合、より広い範囲の帯域が使用され、より極端な異常値によって発生するアラートが少なくなります。 しきい値が低い（例：90%）場合、バンドが狭くなり、極端な異常値が少ないことが原因のアラートが多くなります。
   * 指標の変化を特定の割合で表示。
   * 特定の値の上、下、または等しい指標。 （Select、Prime、またはUltimate パッケージを含むAdobe Analyticsのお客様のみが利用できます）

この[ ビデオチュートリアル ](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/intelligent-alerts)では、アラートの基本的な概要を説明します。


## アラートの異常値ルックバック

>[!NOTE]
>
>異常値検出を使用したアラート（_インテリジェントアラート_&#x200B;とも呼ばれる）の使用は、Adobe Analytics Prime または Ultimate パッケージを使用している組織でのみ使用できます。

異常値検出を使用するアラートの場合、トレーニング期間は、アラートに選択した精度に応じて異なります。

* 月単位の精度：15 ヶ月 + 前年の同じ時間範囲
* 週単位の精度：15 週 + 前年の同じ時間範囲
* 日単位の精度：35 日 + 前年の同じ時間範囲
* 時間単位の精度：336 時間

詳しくは、[異常値検出で使用される統計的手法](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)を参照してください。

## アラートの作成

Adobe Analytics でアラートを作成する方法について詳しくは、[アラートの作成](/help/components/alerts/alert-builder.md)を参照してください。

>[!IMPORTANT]
>
>タイムスタンプ付きデータを使用してアラートを作成すると、アラートが誤って起動される可能性があります。 アラートには、タイムスタンプのないデータの使用をお勧めします。

## アラートの管理

アラートマネージャーでは、既存のアラートを管理できます。 タグ付け、名前変更、削除など、アラートに対して様々な管理タスクを実行できます。

Adobe Analytics で既存のアラートを管理する方法について詳しくは、[アラートの管理](/help/components/alerts/alert-manager.md)を参照してください。
