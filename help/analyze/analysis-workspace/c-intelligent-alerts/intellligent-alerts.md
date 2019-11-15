---
description: 新しいインテリジェントアラートシステムでは、アラートをより詳細に制御でき、異常値検出とアラートシステムが統合されます。
title: インテリジェントアラートの概要
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# インテリジェントアラートの概要

インテリジェントアラートを使用すると、アラートをより詳細に制御し、異常値検出をアラートシステムに統合できます。

[YouTubeに関するインテリジェントアラート](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## 概要

Analysis Workspace の新しいアラートビルダーおよびアラートマネージャーは、Reports &amp; Analytics の既存のアラート機能を置き換えます。インテリジェントアラートを使用すると、次のことができます。:

* 異常値（90%、95%、99%、99.75%、99.9%のしきい値）に基づいてアラートを作成する。% change;上/下)
* アラートがトリガーされる頻度のプレビュー
* 自動生成されたAnalysis Workspaceプロジェクトへのリンクを含む電子メールまたはSMSによるアラートの送信
* 単一のアラートで複数の指標をキャプチャする「積み重ね」アラートを作成する

アラートビルダーにアクセスするには、次の 4 つの方法があります。

* アラートビルダーに直接移動する場合： コンポ **[!UICONTROL ーネント]** /ア **[!UICONTROL ラート]**
* Workspaceでのキーボードショートカットの使用： `Ctrl + Shift + A` (Windows)また `Cmd + Shift + A` は(Mac OS)
* Selecting one or more freeform table line item/s, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**. これにより、アラートビルダーが開き、表から適用した適切な指標およびフィルターが事前設定されます。 必要に応じてアラートを編集できます。

   ![選択からアラートを作成](assets/create-alert-from-selection.png)

* From within a Reports &amp; Analytics report, by going to  **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]** . これにより、アラートビルダーが開き、レポートから適用した適切な指標およびフィルターを事前設定します。 必要に応じてアラートを編集できます。

   ![アラートの追加](assets/add-alert.png)

パーセントしきい値は標準偏差です。 例えば、95% = 2 標準偏差と 99% = 3 標準偏差です。選択した時間の精度に応じて、[異なるモデル](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)が使用され、各データポイントが標準からどれくらい離れているか（標準偏差からの乖離）が計算されます。しきい値を小さく設定すると（90%など）、しきい値を大きく設定する場合(99.75%)よりも多くの異常値が得られます。

> [!IMPORTANT] タイムスタンプ付きのデータを使用してアラートを作成すると、アラートが正しく起動しない場合があります。 インテリジェントアラートには、タイムスタンプのないデータの使用をお勧めします。

## アラートの異常値ルックバック

異常値検出を使用するアラートの場合、トレーニング期間は、アラートに対して選択した精度に応じて異なります。

* 月単位の精度：15か月+昨年同じ範囲
* 週単位の精度：15週間+昨年同じ期間
* 毎日の精度：35日+昨年同じ範囲
* 時間単位の精度：336時間

詳しくは [、異常値検出で使用される統計的手法](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) （英語）を参照してください。
