---
description: 管理者がレポートスイートまたはデータディクショナリを使用してコンポーネントに説明を追加する方法について説明します。
title: コンポーネントの説明の追加
feature: Components
role: Admin
exl-id: db36ee4a-66e2-45d1-8b7a-49570b5fce93
TQID: https://experienceleague.adobe.com/8z9vnSfrxEb1nkOlTTlHrp3BdElFJmTjbsSLBGbE7Gs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
    internal-label: Data Dictionary
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
    internal-label: VRS
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b3d9fb81837398b349496ec261dc1d0ba3df3645
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 20%
---
# コンポーネントの説明の追加

説明は、ユーザーが Analysis Workspace でプロジェクトを作成する際またはレポートを表示する際に、様々なコンポーネントを最適に使用する方法を理解するのに役立ちます。

Analytics管理者は、レポートスイート内で、またはAnalysis Workspace内で直接データディクショナリを使用して、コンポーネント（ディメンション、指標、セグメント、日付範囲）の説明を追加できます。

## レポートスイート

レポートスイートのコンポーネントに説明を追加できます。

1. **[!UICONTROL 管理者]** > **[!UICONTROL すべての管理者]** > **[!UICONTROL レポートスイート]**&#x200B;を選択します。
1. コンポーネントの説明を指定するレポートスイートマネージャーで、レポートスイートを選択します。
1. **[!UICONTROL 設定を編集]** > **[!UICONTROL コンバージョン]** > **[!UICONTROL コンバージョン変数]**&#x200B;を選択します。
1. コンバージョン変数の詳細を表示するには、![追加](/help/assets/icons/Add.svg)を選択します。
1. 「**[!UICONTROL 説明]**」のチェックボックスを選択し、説明を追加します。
1. 説明を追加する他の変数について、手順4と5を繰り返します。
1. 「**[!UICONTROL 保存]**」を選択します。

>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [&#x200B; コンポーネントの説明を追加](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/intro-to-analytics/customizing-the-ui/adding-dimension-and-metric-descriptions){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## データ辞書 {#add-descriptions}

Analysis Workspace のデータ辞書は、ユーザーと管理者の両方が Analytics 環境のコンポーネントを追跡し、よりよく理解するのに役立ちます。 Analytics管理者は、データディクショナリを使用して、Analysis Workspace内で直接コンポーネントの説明を追加できます。

データディクショナリでのコンポーネント説明の編集について詳しくは、[&#x200B; データディクショナリでのコンポーネントエントリの編集](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)を参照してください。

データ辞書の一般情報については、[データ辞書の概要](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)を参照してください。

>[!MORELIKETHIS]
>
>[&#x200B; レポートコンポーネントの設定](/help/components/vrs/vrs-components.md)
>[データ ディクショナリ コンポーネント エントリ &#x200B;](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md)
>

## 説明の自動生成

{{release-limited-testing-section}}

Adobe Analyticsでは、各説明を手作業で記述する代わりに、生成AIを使用して説明を記述できます。 1つのコンポーネントの説明を生成したり、同時に多くのコンポーネントの説明を生成したりできます。

生成された説明：

* 3つ以下の文章です。
* AI **を使用してAdobeによって生成されたテキスト**&#x200B;で終わると、説明が生成されたことがユーザーに分かります。
* 生成後に編集することもできます。

### 前提条件

説明を生成する前に、生成AIに関する特定の法的条件に同意する必要があります。 組織がこれらの条件に同意していない場合、説明を生成するオプションはグレー表示されます。 オプションの横にある情報アイコン ![情報](/help/assets/icons/InfoOutline.svg)を選択して、この機能を有効にする方法を確認するか、組織の管理者またはAdobe アカウントチームにお問い合わせください。

### 説明の生成方法

生成される説明は、コンポーネントの定義と、コンポーネントがレポートスイートでどのように使用されるかに関する追加のコンテキストに基づいています。次に例を示します。

* ディメンションの上位アイテム
* コンポーネントとともに頻繁に使用されるコンポーネント

計算指標またはセグメントが別のセグメントを参照する場合、生成された説明は、参照されるセグメントの定義を説明します。

### 様々な場所から説明を生成する

Adobe Analyticsの次の領域で説明を生成できます。 一部の場所では、複数のコンポーネントの説明を生成できますが、他の場所では生成できません。

場所を選択して、そこに説明を生成する方法を学習します。

| 場所 | サポートされているコンポーネント | 単一コンポーネント | 複数のコンポーネント |
| --- | --- | --- | --- |
| [&#x200B; データディクショナリ &#x200B;](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>ディメンション</li><li>指標</li><li>計算指標</li><li>セグメント</li><li>日付範囲</li></ul> | はい | はい |
| [セグメントビルダー](/help/components/segmentation/segmentation-workflow/seg-build.md) | セグメント | はい | いいえ |
| [&#x200B; セグメントマネージャー](/help/components/segmentation/segmentation-workflow/seg-manage.md#action-bar) | セグメント | いいえ | はい |
| [計算指標ビルダー](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md) | 計算指標 | はい | いいえ |
| [計算指標マネージャー](/help/components/calculated-metrics/workflow/cm-manager.md#action-bar) | 計算指標 | いいえ | はい |
| [日付範囲ビルダー](/help/analyze/analysis-workspace/components/calendar-date-ranges/create.md#date-range-builder) | 日付範囲 | はい | いいえ |
| [日付範囲マネージャー](/help/analyze/analysis-workspace/components/calendar-date-ranges/manage.md#action-bar) | 日付範囲 | いいえ | はい |

{style="table-layout:auto"}