---
description: Adobe Analysis Workspace とその関連コンポーネントに関する既知の制限のリスト
title: Analysis Workspace の既知の制限
translation-type: tm+mt
source-git-commit: 025ac334f9191b6455eea0530a2a21c01199000a

---


# Analysis Workspace の既知の制限

以下に、Analysis Workspace とその関連コンポーネントに関する既知の制限を示します。

## テーブル

* 日付範囲または指標がテーブルの行として使用されている場合は、日付比較列を追加できません。
* セグメントをテーブルの行として使用すると、「選択から指標を作成」が無効になります。また、「選択から指標を作成」は、日付順の列には適用しないでください。
* 分類行の条件付き書式では、カスタム範囲を使用することはできません。
* 行の値を合計して合計を計算する設定が適用されている場合は、テーブルの合計行をトレンド表示できません（通常は静的な行項目で使用されます）。
* [!UICONTROL Contribution Analysis] は、精度でのみ実行で [!UICONTROL daily] き _ます_。 It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## ビジュアライゼーション

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]:入口/出口ディメンション(例：フロ [!UICONTROL Entry page]ーでは使用できません。
* [!UICONTROL Cohort]:整数以外の値は、コホート条件として使用できません。

## パネル

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## コンポーネント／セグメント

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). 例：IP アドレス。

## コンポーネント／計算指標

* 計算指標は、一部のビジュアライゼーションでは使用できません。上記の「ビジュアライゼーション」を参照してください。
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). 例：[!UICONTROL IP Address]。

## コンポーネント／日付範囲

* カスタムの日付範囲は、サポ [!UICONTROL This day last year]ートさ [!UICONTROL This day last month]れません。

## コンポーネント／仮想レポートスイート

* レポート時間処理が有効な場合、一部のコンポーネントはサポートされません。完全なリストについては、[レポート時間処理](/help/components/vrs/vrs-report-time-processing.md)を参照してください。

## コンポーネント／レポート設定

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. 分析ワークスペースでは、 [!UICONTROL Language/Currency/Encoding] 下部の設定のみが使用されます。 [!UICONTROL Thousands separator]、、 [!UICONTROL Scheduled Report Encoding]および [!UICONTROL CSV Separator Character]。

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. 完全なリストについては、[Attribution IQ に関する FAQ](/help/analyze/analysis-workspace/c-panels/attribution/attribution-faq.md) を参照してください。
