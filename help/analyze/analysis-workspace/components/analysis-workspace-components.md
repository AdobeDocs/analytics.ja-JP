---
description: Analysis Workspace のコンポーネントは、プロジェクトにドラッグ＆ドロップできるディメンション、指標、セグメント、および日付範囲で構成されています。
title: コンポーネントの概要
feature: Components
role: User, Admin
exl-id: e2c98c77-64ee-4349-956a-3ab092e36017
source-git-commit: 6247f44aca1e6aba6cf02ed34a0e26ef5e182021
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 71%

---

# コンポーネントの概要

Analysis Workspace のコンポーネントは、プロジェクトにドラッグ＆ドロップできるディメンション、指標、セグメント、および日付範囲で構成されています。

「コンポーネント」メニューにアクセスするには、左側のレールにある「**[!UICONTROL コンポーネント]**」アイコンをクリックします。 左側のレールアイコンから、または[ホットキー](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)を使用して、[パネル](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja)、[ビジュアライゼーション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=ja)、コンポーネントを切り替えることができます。

![](assets/component-overview.png)

また、**[!UICONTROL プロジェクト／プロジェクト情報と設定／ビュー密度]**&#x200B;に移動して、プロジェクトの[ビュー密度設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=ja)を調整し、左側のレールで一度に多くの値を表示することもできます。

## ディメンション {#dimensions}

[**ディメンション**](https://experienceleague.adobe.com/docs/analytics/components/dimensions/overview.html?lang=ja)は、訪問者行動を説明するテキスト属性であり、分析内で表示、分類、および比較できます。 これらは左側のコンポーネントレール（オレンジ色のセクション）にあり、通常はテーブルの行として適用されます。

ディメンションの例としては、[!UICONTROL ページ名]、[!UICONTROL マーケティングチャネル]、[!UICONTROL デバイスタイプ]、[!UICONTROL 製品]があります。 ディメンションはアドビが提供し、カスタム実装（eVar、Prop、分類など）を通じて取得します。

各ディメンションには、**ディメンション項目**&#x200B;も含まれます。 任意のディメンション名の横にある右矢印をクリックすると、ディメンション項目が左側のコンポーネントレールに表示されます（項目は黄色で表示）。

ディメンション項目の例としては、[!UICONTROL ホームページ]（[!UICONTROL ページ]ディメンション内）、[!UICONTROL 有料検索]（[!UICONTROL マーケティングチャネル]ディメンション内）、[!UICONTROL タブレット]（[!UICONTROL モバイルデバイスタイプ]ディメンション内）などがあります。

![](assets/dimensions.png)

## 指標 {#metrics}

[**指標**](https://experienceleague.adobe.com/docs/analytics/components/metrics/overview.html?lang=ja)は、訪問者行動に関する定量的な指標です。 これらは左側のコンポーネントレール（緑色のセクション）にあり、通常は表の列として適用されます。

指標の例としては、[!UICONTROL ページビュー]、[!UICONTROL 訪問回数]、[!UICONTROL 注文件数]、[!UICONTROL 平均滞在時間]、および[!UICONTROL 売上高／注文件数]があります。 指標は、アドビから提供されるか、カスタム実装（[!UICONTROL 成功イベント]）を通じて取得、または[計算指標ビルダー](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=ja)を使用して作成します。

![](assets/metrics.png)

## セグメント {#segments}

[**セグメント**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=ja)は、分析に適用するオーディエンスフィルターです。 これらは左側のコンポーネントレール（青いセクション）にあり、通常はパネルの上部または表の指標列の上に適用されます。

セグメントの例としては、[!UICONTROL モバイルデバイス訪問者]、[!UICONTROL 電子メールからの訪問]、および[!UICONTROL 認証済みヒット]があります。 セグメントはアドビから提供されるか、[パネルドロップゾーン](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja)で作成、または[セグメントビルダー](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=ja)を使用して作成します。

![](assets/segments.png)

## 日付範囲 {#date-ranges}

[**日付範囲**](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html?lang=ja)は、分析を実行する日付の範囲です。 これらは左側のコンポーネントレール（紫のセクション）にあり、通常は各パネルのカレンダーに適用されます。

日付範囲コンポーネントは、パネルカレンダーに対して相対的に設定できます。 詳しくは、 [相対パネルの日付範囲について](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates).

日付範囲の例としては、2019 年 7 月、[!UICONTROL 過去 4 週間]、[!UICONTROL 今月]などがあります。 日付範囲はアドビが提供するか、[パネルのカレンダー](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=ja)に適用されるか、[日付範囲ビルダー](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=ja)を使用して作成します。

![](assets/date-ranges.png)


## コンポーネントの管理 {#actions}

左側のパネルでコンポーネントを直接管理できます。

1. コンポーネントを右クリックします。

   または

   コンポーネントを選択してから、 **アクション** （3 ドット）アイコンを使用して、コンポーネントリストの上部に表示されます。

   >[!TIP]
   >
   >   Shift キーを押しながら複数のコンポーネントを選択するか、Command キー (Mac) または Ctrl キー (Windows) を押しながら複数のコンポーネントを選択できます。


   ![](assets/component-actions.png)

   | コンポーネントのアクション | 説明 |
   |--- |--- |
   | [!UICONTROL **タグ**] | コンポーネントにタグを適用して整理したり管理したりします。次に、フィルターをクリックするか「#」を入力して、左側のレールのタグで検索できます。 タグは、コンポーネントマネージャーのフィルターとしても機能します。 |
   | [!UICONTROL **お気に入り**] | コンポーネントをお気に入りのリストに追加します。タグと同様に、左側のレールのお気に入りで検索し、コンポーネントマネージャーでフィルタリングできます。 |
   | [!UICONTROL **承認**] | コンポーネントを「承認済み」とマークして、コンポーネントが組織で承認されていることをユーザーに知らせます。 タグと同様に、左側のレールで「承認済み」を検索し、コンポーネントマネージャーでフィルタリングできます。 |
   | [!UICONTROL **共有**] | 組織内のユーザーとコンポーネントを共有します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |
   | [!UICONTROL **削除**] | 不要になったコンポーネントを削除します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |

カスタムコンポーネントは、それぞれのコンポーネントマネージャーを通じて管理することもできます。 例えば、[セグメントマネージャ](/help/components/segmentation/segmentation-workflow/seg-manage.md)です。

## コンポーネントリストの検索、フィルタリング、並べ替え

Analysis Workspaceの左側のパネルでコンポーネントリストを検索、フィルタリングおよび並べ替えて、特定のコンポーネントをすばやく見つけることができます。

### コンポーネントリストを検索

1. を選択します。 **コンポーネント** アイコン ![コンポーネントアイコン](assets/components-icon.png) をクリックします。

1. 検索フィールドに、プロジェクトで使用するコンポーネントの名前を入力します。

   コンポーネントの種類は、色とアイコンの両方で識別できます。 **Dimension** ![Dimensionアイコン](assets/dimension-icon.png) オレンジ色です **セグメント** ![セグメントアイコン](assets/segment-icon.png) 青い **日付範囲** ![日付範囲アイコン](assets/date-range-icon.png) 紫色で **指標** ![指標アイコン](assets/default-metric-icon.png) は緑です。 Adobeアイコン ![Adobeアイコン](assets/default-calc-metric-icon.png) は、計算指標テンプレートまたはセグメントテンプレート、および計算ツールアイコンを示します ![計算ツールアイコン](assets/calculated-metric-icon-created.png) は、組織の Analytics 管理者が作成した計算指標を示していました。

1. ドロップダウンリストに表示される場合に、コンポーネントを選択します。

### コンポーネントリストのフィルタリング

1. を選択します。 **コンポーネント** アイコン ![コンポーネントアイコン](assets/components-icon.png) をクリックします。

1. を選択します。 **フィルター** アイコン ![データ辞書フィルターアイコン](assets/components-filter-icon.png).

   または

   検索フィールドにシャープ記号 (#) を入力します。

1. 次のいずれかのフィルターオプションを選択して、コンポーネントのリストをフィルターします。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **承認済み**] | 管理者が承認済みとしてマークしたコンポーネントのみを表示します。 |
   | [!UICONTROL **お気に入り**] | お気に入りのリストにあるコンポーネントのみを表示します。お気に入りのリストにコンポーネントを追加する方法については、[コンポーネントの概要](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)を参照してください。 |
   | [!UICONTROL **ディメンション**] | ディメンションであるコンポーネントのみを表示します |
   | [!UICONTROL **指標**] | 指標であるコンポーネントのみを表示します |
   | [!UICONTROL **セグメント**] | セグメントであるコンポーネントのみを表示します<!--this is Filters in CJA--> |
   | [!UICONTROL **日付範囲**] | 日付範囲であるコンポーネントのみを表示します |
   | [!UICONTROL **すべてを表示**] | すべてのコンポーネントの表示。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **未承認**] | 管理者が承認済みとしてまだマークしていないコンポーネントのみを表示します。レビューと承認が必要なコンポーネントを管理者が識別する際に役立ちます。このオプションは、管理者のみが使用できます。 |

1. （オプション）リストをさらに絞り込むには、 [コンポーネントリストの並べ替え](#sort-the-component-list).

### コンポーネントリストの並べ替え

1. （オプション）コンポーネントリストに任意のフィルターを適用します。詳しくは、 [コンポーネントリストのフィルタリング](#filter-the-component-list).

1. を選択します。 **コンポーネント** アイコン ![コンポーネントアイコン](assets/components-icon.png) をクリックします。

1. を選択します。 **並べ替え** アイコン ![コンポーネントを並べ替えアイコン](assets/component-sort-icon.png)次に、次のいずれかのフィルターオプションを選択して、コンポーネントのリストを並べ替えます。

   {{components-sort-options}}
