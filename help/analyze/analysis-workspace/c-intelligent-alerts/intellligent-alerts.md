---
description: 新しいインテリジェントアラートシステムでは、アラートをより詳細に制御でき、異常値検出とアラートシステムが統合されます。
title: インテリジェントアラートの概要
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 373a1ecffafdcefe3c7b60954f14c2f3a5ca386d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 60%

---

# インテリジェントアラートの概要

Adobe Analyticsのインテリジェントアラート（または単に「アラート」）を使用すると、データで異常なイベントが発生した場合に、すぐに通知を受け取ることができます。

異常しきい値、変更された割合、または特定のデータポイントに基づいてアラートをトリガーするように設定できます。アラートは、[ 異常値検出 ](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) と統合され、最も必要なときにトリガーされる詳細なコントロールを提供します。

インテリジェントアラートを使用すると、次のことができます。

* 異常値（90％、95％、99％、99.75％、99.9％のしきい値、変化率、超過／未満）に基づいてアラートを構築
* アラートがトリガーされる頻度のプレビュー
* 自動生成される Analysis Workspace プロジェクトへのリンクが記載された電子メールまたは SMS によるアラートの送信
* 1 つのアラートで複数の指標を示す「積み重ね」アラートの作成

次のビデオチュートリアルでは、アラートの基本的な概要を説明します。[ インテリジェントアラート ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=ja) （5:34）

## アラートの異常値ルックバック

異常値検出を使用するアラートの場合、トレーニング期間は、アラートに選択した精度に応じて異なります。

* 月単位の精度：15 ヶ月 + 前年の同じ時間範囲
* 週単位の精度：15 週 + 前年の同じ時間範囲
* 日単位の精度：35 日 + 前年の同じ時間範囲
* 時間単位の精度：336 時間

詳しくは、[ 異常値検出で使用される統計的手法 ](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) を参照してください。

## アラートの作成

Adobe Analyticsでアラートを作成する方法について詳しくは、[ アラートの作成 ](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md) を参照してください。

>[!IMPORTANT]
>
>タイムスタンプ付きデータを使用してアラートを作成すると、アラートが誤って起動される可能性があります。インテリジェントアラートには、タイムスタンプのないデータの使用をお勧めします。

## アラートの管理

アラートマネージャーでは、既存のアラートを管理できます。 タグ付け、名前の変更、削除など、アラートに対して様々な管理タスクを実行できます。

Adobe Analyticsで既存のアラートを管理する方法について詳しくは、「[ アラートの管理 ](/help/components/c-alerts/alert-manager.md)」を参照してください。
