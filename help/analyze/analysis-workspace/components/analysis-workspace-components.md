---
description: 'Analysis Workspace のコンポーネントは、プロジェクトにドラッグ＆ドロップできるディメンション、指標、セグメント、および日付範囲で構成されています。 '
title: コンポーネントの概要
feature: Workspace の基本
role: Business Practitioner, Administrator
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 92%

---

# コンポーネントの概要

Analysis Workspace のコンポーネントは、プロジェクトにドラッグ＆ドロップできるディメンション、指標、セグメント、および日付範囲で構成されています。

「コンポーネント」メニューにアクセスするには、左側のレールにある「**[!UICONTROL コンポーネント]**」アイコンをクリックします。 左側のレールアイコンから、または[ホットキー](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)を使用して、[パネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja)、[ビジュアライゼーション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=ja)、コンポーネントを切り替えることができます。

![](assets/component-overview.png)

また、**[!UICONTROL プロジェクト／プロジェクト情報と設定／ビュー密度]**&#x200B;に移動して、プロジェクトの[ビュー密度設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=ja)を調整し、左側のレールで一度に多くの値を表示することもできます。

## ディメンション {#dimensions}

[**ディメンション**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html)は、訪問者行動を説明するテキスト属性であり、分析内で表示、分類、および比較できます。 これらは左側のコンポーネントレール（オレンジ色のセクション）にあり、通常はテーブルの行として適用されます。

ディメンションの例としては、[!UICONTROL ページ名]、[!UICONTROL マーケティングチャネル]、[!UICONTROL デバイスタイプ]、[!UICONTROL 製品]があります。 ディメンションはアドビが提供し、カスタム実装（eVar、Prop、分類など）を通じて取得します。

各ディメンションには、**ディメンション項目**&#x200B;も含まれます。 任意のディメンション名の横にある右矢印をクリックすると、ディメンション項目が左側のコンポーネントレールに表示されます（項目は黄色で表示）。

ディメンション項目の例としては、[!UICONTROL ホームページ]（[!UICONTROL ページ]ディメンション内）、[!UICONTROL 有料検索]（[!UICONTROL マーケティングチャネル]ディメンション内）、[!UICONTROL タブレット]（[!UICONTROL モバイルデバイスタイプ]ディメンション内）などがあります。

![](assets/dimensions.png)

## 指標 {#metrics}

[**指標**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html)は、訪問者行動に関する定量的な指標です。 これらは左側のコンポーネントレール（緑色のセクション）にあり、通常は表の列として適用されます。

指標の例としては、[!UICONTROL ページビュー]、[!UICONTROL 訪問回数]、[!UICONTROL 注文件数]、[!UICONTROL 平均滞在時間]、および[!UICONTROL 売上高／注文件数]があります。 指標は、アドビから提供されるか、カスタム実装（[!UICONTROL 成功イベント]）を通じて取得、または[計算指標ビルダー](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)を使用して作成します。

![](assets/metrics.png)

## セグメント {#segments}

[**セグメント**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)は、分析に適用するオーディエンスフィルターです。 これらは左側のコンポーネントレール（青いセクション）にあり、通常はパネルの上部または表の指標列の上に適用されます。

セグメントの例としては、[!UICONTROL モバイルデバイス訪問者]、[!UICONTROL 電子メールからの訪問]、および[!UICONTROL 認証済みヒット]があります。 セグメントはアドビから提供されるか、[パネルドロップゾーン](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)で作成、または[セグメントビルダー](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html)を使用して作成します。

![](assets/segments.png)

## 日付範囲 {#date-ranges}

[**日付範囲**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html)は、分析を実行する日付の範囲です。 これらは左側のコンポーネントレール（紫のセクション）にあり、通常は各パネルのカレンダーに適用されます。

日付範囲の例としては、2019 年 7 月、[!UICONTROL 過去 4 週間]、[!UICONTROL 今月]などがあります。 日付範囲はアドビが提供するか、[パネルのカレンダー](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html)に適用されるか、[日付範囲ビルダー](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)を使用して作成します。

![](assets/date-ranges.png)

## コンポーネントのアクション {#actions}

左側のレールで、コンポーネントを直接（個別に、または複数を選択して）管理できます。 コンポーネントを右クリックするか、コンポーネントリストの上部にあるアクションドットアイコンをクリックします。

![](assets/component-actions.png)

| コンポーネントのアクション | 説明 |
|--- |--- |
| タグ | コンポーネントにタグを適用して整理したり管理したりします。次に、フィルターをクリックするか「#」を入力して、左側のレールのタグで検索できます。 タグは、コンポーネントマネージャーのフィルターとしても機能します。 |
| お気に入り | コンポーネントをお気に入りのリストに追加します。タグと同様に、左側のレールのお気に入りで検索し、コンポーネントマネージャーでフィルタリングできます。 |
| 承認 | コンポーネントを「承認済み」とマークして、コンポーネントが組織で承認されていることをユーザーに知らせます。 タグと同様に、左側のレールで「承認済み」を検索し、コンポーネントマネージャーでフィルタリングできます。 |
| 共有 | 組織内のユーザーとコンポーネントを共有します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |
| 削除 | 不要になったコンポーネントを削除します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |

カスタムコンポーネントは、それぞれのコンポーネントマネージャーを通じて管理することもできます。 例えば、[セグメントマネージャ](/help/components/segmentation/segmentation-workflow/seg-manage.md)です。
