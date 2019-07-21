---
description: 'null'
seo-description: 'null'
seo-title: Workspaceの制限事項， Analysis Workspaceの既知の制限
title: Analysis Workspaceの既知の制限事項
translation-type: tm+mt
source-git-commit: 9d6b35c7c6de6fcb49fea3b662ff8bc9044b5e29

---


# Analysis Workspaceの既知の制限事項

Analysis Workspaceとその関連コンポーネントの既知の制限事項を次に示します。

## テーブル

* 日付範囲または指標がテーブルの行として使用されている場合、日付比較列を追加できません。
* セグメントをテーブルの行として使用すると、選択から指標を作成することはできません。さらに、選択から指標を作成しても、日付揃え列には適用できません。
* 分類行の条件付き書式では、カスタム範囲を使用できません。
* 行の値設定を合計して合計を計算する場合は、テーブル合計行をトレンド表示できません（通常、静的行項目で使用されます）。
* [!UICONTROL 貢献度分析] は [!UICONTROL 、毎日] の精度 _でのみ実行_&#x200B;できます。[!UICONTROL 時間別]、 [!UICONTROL 週単位]など、時間別には実行できません。

## ビジュアライゼーション

* [!UICONTROL フォールアウト]、 [!UICONTROL フロー]、 [!UICONTROL コホート]、 [!UICONTROL ヒストグラム]などのセグメント化を活用するビジュアライゼーションでは、計算指標を入力として受け入れることはできません。
* [!UICONTROL フロー]:入口ページ/出口ディメンション（ [!UICONTROL 入口ページ]など）は、フローでは使用できません。
* [!UICONTROL コホート]:整数以外の場合は、コホート条件として使用できません。

## パネル

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## コンポーネント/セグメント

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Certain components and operators are unavailable if a segment is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). 例えば、IPアドレスです。

## コンポーネント/計算指標

* 特定のビジュアライゼーションで計算指標を使用することはできません。上記の「ビジュアライゼーション」を参照してください。
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components &gt; Segments]). For example, [!UICONTROL IP Address].

## コンポーネント/日付範囲

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## コンポーネント/仮想レポートスイート

* レポートの時間処理が有効になっている場合、一部のコンポーネントはサポートされていません。For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## コンポーネント/レポート設定

* [!UICONTROL レポート設定] ページの設定の一部は適用されません。Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution IQ

* A subset of metrics is not supported in [!UICONTROL Attribution IQ]. For a full list, see the [Attribution IQ FAQ](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).