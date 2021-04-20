---
description: 'Analysis Workspaceのコンポーネントは、ディメンション、指標、セグメントおよび日付範囲で構成され、これらはプロジェクトにドラッグ&ドロップできます。 '
title: コンポーネントの概要
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 17%

---


# コンポーネントの概要

Analysis Workspaceのコンポーネントは、ディメンション、指標、セグメントおよび日付範囲で構成され、これらはプロジェクトにドラッグ&amp;ドロップできます。

コンポーネントメニューにアクセスするには、左側のナビゲーションバーの&#x200B;**[!UICONTROL コンポーネント]**&#x200B;アイコンをクリックします。 左側のレールアイコンから、または[ホットキー](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)を使用して、[パネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja-JP)、[ビジュアライゼーション](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)、コンポーネントを切り替えることができます。

![](assets/component-overview.png)

また、**[!UICONTROL プロジェクト/プロジェクト情報と設定/表示密度]**&#x200B;に移動して、プロジェクトの[表示密度設定](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)を調整し、左側のレールに一度に表示される値を増やすこともできます。

## ディメンション {#dimensions}

[****](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) ディメンションとは、訪問者の動作を記述し、分析内での表示、分類、比較が可能なテキスト属性です。これらは左側のコンポーネントレール（オレンジ色のセクション）にあり、通常はテーブルの行として適用されます。

ディメンションの例としては、[!UICONTROL ページ名]、[!UICONTROL マーケティングチャネル]、[!UICONTROL デバイスタイプ]、[!UICONTROL 製品]があります。 Dimensionは、Adobeによって提供され、カスタム導入(eVar、Prop、分類など)で取得されます。

各ディメンションには、**ディメンション項目**&#x200B;も含まれます。 Dimension項目は、任意のディメンション名の横の右矢印をクリックすると、左側のコンポーネントレールに表示されます（項目が黄色になります）。

ディメンション項目の例としては、[!UICONTROL ホームページ]（[!UICONTROL ページ]ディメンション内）、[!UICONTROL 有料検索]([!UICONTROL マーケティングチャネル]ディメンション内)、[!UICONTROL タブレット]（[!UICONTROL モバイルデバイスタイプ内）があります。a11/>次元など)を参照してください。]

![](assets/dimensions.png)

## 指標 {#metrics}

[**指標**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) は、訪問者の行動に関する定量的な指標です。これらは左側のコンポーネントレール（緑のセクション）にあり、通常は表の列として適用されます。

指標の例としては、[!UICONTROL ページ表示]、[!UICONTROL 訪問回数]、[!UICONTROL 注文件数]、[!UICONTROL 平均滞在時間]、[!UICONTROL 売上高/注文件数]があります。 指標は、Adobeが提供するか、カスタム導入([!UICONTROL 成功イベント])で取得するか、[計算指標ビルダー](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)を使用して作成します。

![](assets/metrics.png)

## セグメント {#segments}

[**セグメ**](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) ントは、分析に適用されるオーディエンスフィルターです。これらは左側のコンポーネントレール（青いセクション）にあり、通常はパネルの上部または表の指標列の上に適用されます。

セグメントの例としては、[!UICONTROL モバイルデバイス訪問者]、[!UICONTROL 電子メール]からの訪問、[!UICONTROL 認証済みヒット]があります。 セグメントはAdobeが提供するか、[パネルドロップゾーン](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)で作成するか、[セグメントビルダー](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-build.html)を使用して作成します。

![](assets/segments.png)

## 日付範囲 {#date-ranges}

[**日付**](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) 範囲は、分析を実行する日付の範囲です。これらは左側のコンポーネントレール（紫のセクション）にあり、通常は各パネルのカレンダーに適用されます。

日付範囲の例としては、2019年7月、[!UICONTROL 過去4週間]、[!UICONTROL 今月]などがあります。 日付範囲はAdobeで提供され、[パネルのカレンダー](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)に適用されるか、[日付範囲ビルダー](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)を使用して作成されます。

![](assets/date-ranges.png)

## コンポーネントのアクション {#actions}

左側のレールで、コンポーネントを直接（個別に、または複数を選択して）管理できます。 コンポーネントを右クリックするか、コンポーネントリストの上部にあるアクションドットアイコンをクリックします。

![](assets/component-actions.png)

| コンポーネントのアクション | 説明 |
|--- |--- |
| タグ | コンポーネントにタグを適用して整理したり管理したりします。その後、左側のナビゲーションバーのタグでフィルターをクリックするか、#を入力して検索できます。 タグは、コンポーネントマネージャーのフィルターとしても機能します。 |
| お気に入り | コンポーネントをお気に入りのリストに追加します。タグと同様に、左側のレールのお気に入りで検索し、コンポーネントマネージャーでフィルターできます。 |
| 承認 | コンポーネントを「承認済み」とマークして、コンポーネントが組織で承認されたことをユーザーに伝えます。 タグと同様に、左側のレールで「承認済み」で検索し、コンポーネントマネージャーでフィルターできます。 |
| 共有 | 組織内のユーザーとコンポーネントを共有します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |
| 削除 | 不要になったコンポーネントを削除します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |

カスタムコンポーネントは、それぞれのコンポーネントマネージャーを通じて管理することもできます。 例えば、[セグメントマネージャ](/help/components/segmentation/segmentation-workflow/seg-manage.md)です。
