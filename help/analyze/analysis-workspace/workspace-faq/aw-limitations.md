---
description: Adobe Analysis Workspace とその関連コンポーネントに関する既知の制限事項について説明します。
title: Analysis Workspaceの既知の制限事項
feature: Workspace Basics
role: User, Admin
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 98%

---

# Analysis Workspace の既知の制限

次に、Analysis Workspace とその関連コンポーネントに関する既知の制限を示します。

## テーブル

* 日付範囲または指標がテーブルの行として使用されている場合は、日付比較列を追加できません。
* セグメントをテーブルの行として使用すると、「選択から指標を作成」が無効になります。また、「選択から指標を作成」は、日付順の列には適用しないでください。
* 分類行の条件付き書式では、カスタム範囲を使用することはできません。
* 行の値を合計して合計を計算する設定が適用されている場合は、テーブルの合計行をトレンド表示できません（通常は静的な行項目で使用されます）。

## ビジュアライゼーション

* セグメント（[!UICONTROL フォールアウト]、[!UICONTROL フロー]、[!UICONTROL コホート]、[!UICONTROL ヒストグラム]など）を利用するビジュアライゼーションでは、計算指標を入力として使用することはできません。
* [!UICONTROL フロー]：入口／出口ディメンション（例：[!UICONTROL 入口ページ]）は、フローでは使用できません。
* [!UICONTROL コホート]：整数以外の値をコホート条件として使用することはできません。

## セグメント

* 指標やディメンションには、セグメント化できないものがあります（[!UICONTROL イベント]、[!UICONTROL ユーザー]など）。
* [パネルのドロップゾーン](/help/analyze/analysis-workspace/c-panels/panels.md)で作成されたアドホックセグメントは、クイックセグメントのタイプです。公開されない限り、Workspace の左パネルまたはセグメントマネージャーには表示されません。詳しくは、[クイックセグメント](/help/components/segmentation/segmentation-workflow/seg-quick.md)を参照してください。

## 計算指標

* 計算指標は、一部のビジュアライゼーションでは使用できません。詳しくは、[ビジュアライゼーション](#visualizations)を参照してください。
* 計算指標自体に別々のアトリビューションモデルを含めることができるので、[!UICONTROL アトリビューションパネル]で計算指標を使用できません。
* 計算指標が Workspace から作成される場合（[!UICONTROL コンポーネント／セグメント]から作成される場合とは異なり）、使用できないコンポーネントや演算子があります。例：[!UICONTROL IP アドレス]。

## 日付範囲

* カスタム日付範囲では、[!UICONTROL 昨年の今日]、[!UICONTROL 先月の今日]などはサポートされません。


## レポート設定

* 「[!UICONTROL レポート設定]」ページの一部の設定は適用されません。Analysis Workspace では、一番下の「[!UICONTROL 言語 / 通貨 / エンコード]」設定（[!UICONTROL 桁区切り記号]、[!UICONTROL 予定レポートのエンコード]、[!UICONTROL CSV 区切り記号]）のみが使用されます。



<!--
# Known limitations in Analysis Workspace 

Here is a list of known limitations in Analysis Workspace and its related components:

## Tables

* Date comparison columns cannot be added when either date ranges or metrics are used as rows of a table.
* Create metric from selection is disabled when segments are used as rows of a table. Additionally, Create metric from selection should not be applied to date-aligned columns.
* Conditional formatting for breakdown rows cannot use custom ranges.
* Table total rows cannot be trended when Calculate totals by summing the row values setting is applied (typically used with Static row items).
* [!UICONTROL Contribution Analysis] can be run at the [!UICONTROL daily] granularity _only_. It cannot be run against [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualizations

* Visualizations that leverage segmentation, such as [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort], and [!UICONTROL Histogram], cannot accept calculated metrics as inputs.
* [!UICONTROL Flow]: Entry/Exit dimensions, e.g. [!UICONTROL Entry page], cannot be used in Flow.
* [!UICONTROL Cohort]: Non-integers cannot be used as Cohort criteria.

## Panels

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.

## Components > Segments

* Certain metrics and dimensions are not segmentable, such as [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], etc.
* Adhoc segments created in the [panel dropzone](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja) are a type of quick filter. They do not appear in the left rail of Workspace or the Segment component manager unless they are made public. For more information, see [Quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

## Components > Calculated Metrics

* Calculated metrics cannot be used in certain visualizations. See 'Visualizations' above.
* Calculated metrics cannot be used in the [!UICONTROL Attribution] panel, since calculated metrics themselves can include separate attribution models.
* Certain components and operators are unavailable if a calculated metric is created from Workspace (as opposed to being created from [!UICONTROL Components > Segments]). For example, [!UICONTROL IP Address].

## Components > Date Ranges

* Custom date ranges do not support [!UICONTROL This day last year], [!UICONTROL This day last month], etc.

## Components > Virtual Reports Suites

* When report time processing is enabled, certain components are not supported. For a full list, see [Report Time Processing](/help/components/vrs/vrs-report-time-processing.md).

## Components > All components > Report settings

* Some of the settings on the [!UICONTROL Report Settings] page do not apply. Analysis Workspace uses only the [!UICONTROL Language/Currency/Encoding] settings at the bottom: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], and [!UICONTROL CSV Separator Character].

## Attribution

* A subset of metrics is not supported in [!UICONTROL Attribution]. For a full list, see the [Attribution FAQ](/help/analyze/analysis-workspace/attribution/faq.md).
-->
