---
description: 'Analysis Workspaceのコンポーネントは、ディメンション、指標、セグメントおよび日付範囲で構成され、これらはプロジェクトにドラッグ&ドロップできます。 '
title: コンポーネントの概要
uuid: 1a4e1c35-eac9-4eb4-be2e-ecb2c6728150
translation-type: tm+mt
source-git-commit: 08d61f4e41bae8a9a0a4be6a950db4ef093c4b02
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 13%

---


# コンポーネントの概要

Analysis Workspaceのコンポーネントは、ディメンション、指標、セグメントおよび日付範囲で構成され、これらはプロジェクトにドラッグ&amp;ドロップできます。

To access the Components menu, click the **Components** icon in the left rail. 左側のレールアイコンまたは [ホットキーを使用して、](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)パネル [、](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)ビジュアライゼーション [、コンポーネントを切り替えることができます](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)。

また、プロジェクト/ [表示情報と設定/表示密度に移動して、プロジェクトの](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) 密度の設定を調整し ****、左側のレールに一度に表示される値を増やすこともできます。

## ディメンション {#dimensions}

[**Dimension**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) は、訪問者の動作を説明するテキスト属性で、分析内での表示、分類および比較が可能です。 これらは左側のコンポーネントレール（オレンジ色のセクション）にあり、通常はテーブルの行として適用されます。

ディメンションの例としては、ページ名、マーケティングチャネル、デバイスタイプ、製品があります。 Dimensionは、Adobeによって提供され、カスタム導入(eVar、Prop、分類など)で取得されます。

各ディメンションには、 **ディメンション項目も含まれ** ます。 Dimension項目は、任意のディメンション名の横にある山形の矢印をクリックすると、左側のコンポーネントレールに表示されます（項目が黄色に表示されます）。

ディメンション項目の例としては、ホームページ（ページディメンション内）、有料検索(マーケティングチャネルディメンション内)、タブレット（モバイルデバイスタイプディメンション内）などがあります。

## 指標 {#metrics}

[**指標**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) (Metrics)は、訪問者の行動に関する定量的な指標です。 これらは左側のコンポーネントレール（緑のセクション）にあり、通常は表の列として適用されます。

指標の例としては、ページ表示数、訪問回数、注文回数、平均滞在時間、売上高/注文があります。 指標は、Adobeによって提供され、カスタム導入(成功イベント)で取得されるか、 [計算指標ビルダーを使用して作成されます](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)。

## セグメント {#segments}

[**セグメント**](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) は、分析に適用されるオーディエンスフィルターです。 これらは左側のコンポーネントレール（青いセクション）にあり、通常はパネルの上部または表の指標列の上に適用されます。

セグメントの例としては、モバイルデバイス訪問者、電子メールからの訪問、認証済みヒットなどがあります。 セグメントはAdobeが提供するか、 [パネルのドロップゾーンで作成するか](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)、 [セグメントビルダーを使用して作成します](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-build.html)。

## 日付範囲 {#date-ranges}

[**日付範囲**](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) :分析を実行する日付の範囲です。 これらは左側のコンポーネントレール（紫のセクション）にあり、通常は各パネルのカレンダーに適用されます。

日付範囲の例としては、2019年7月、過去4週間、今月があります。 日付範囲は、Adobeが提供するか、 [パネルカレンダーで適用するか](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)、 [日付範囲ビルダーを使用して作成します](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)。

## コンポーネントのアクション {#actions}

左側のレールで、コンポーネントを直接（個別に、または複数を選択して）管理できます。 コンポーネントを右クリックするか、コンポーネントリストの上部にあるアクションドットアイコンをクリックします。

| コンポーネントのアクション | 説明 |
|--- |--- |
| タグ | コンポーネントにタグを適用して整理したり管理したりします。その後、左側のナビゲーションバーのタグでフィルターをクリックするか、#を入力して検索できます。 タグは、コンポーネントマネージャーのフィルターとしても機能します。 |
| お気に入り | コンポーネントをお気に入りのリストに追加します。タグと同様に、左側のレールのお気に入りで検索し、コンポーネントマネージャーでフィルターできます。 |
| 承認 | コンポーネントを「承認済み」とマークして、コンポーネントが組織で承認されたことをユーザーに伝えます。 タグと同様に、左側のレールで「承認済み」で検索し、コンポーネントマネージャーでフィルターできます。 |
| 共有 | 組織内のユーザーとコンポーネントを共有します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |
| 削除 | 不要になったコンポーネントを削除します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |

カスタムコンポーネントは、それぞれのコンポーネントマネージャーを通じて管理することもできます。
