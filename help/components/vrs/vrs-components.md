---
description: 仮想レポートスイートをキュレートして、Analysis Workspace内のコンポーネントを含めたり除外したりできます。
title: 仮想レポートスイートコンポーネントのキュレーション
feature: VRS
exl-id: 19163829-328a-4064-b1be-8c09d1d94a0d
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 40%

---

# 仮想レポートスイートコンポーネントのキュレーション

仮想レポートスイートをキュレートして、Analysis Workspace内のコンポーネントを含めたり除外したりできます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Component curation](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/virtual-report-suites/component-curation-in-virtual-report-suites){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


>[!NOTE]
>
>キュレーションされた Workspace プロジェクトおよびキュレーションされた仮想レポートスイートで、管理者および非管理者が表示できるコンポーネントに対して変更が加えられました。以前は、「**[!UICONTROL すべてのコンポーネントを表示]**」ボタンをクリックすることで、誰でもキュレーションされていないコンポーネントを表示できました。[&#x200B; 更新されたキュレーションエクスペリエンス &#x200B;](/help/analyze/analysis-workspace/curate-share/curate.md) を使用すると、表示するコンポーネントをより詳細に制御できます。

コンポーネントのキュレーションを有効にするには、次の手順に従います。

1. **[!UICONTROL Analytics]**/**[!UICONTROL コンポーネント]**/**[!UICONTROL 仮想レポートスイート]**/**[!UICONTROL 新しい仮想レポートスイートの作成]** に移動します。
1. **[!UICONTROL 設定]**&#x200B;を定義したら、「**[!UICONTROL コンポーネント]**」タブをクリックします。

1. 「**[!UICONTROL 仮想レポートスイートコンポーネントのカスタマイズを有効にする]**」チェックボックスを選択します。

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >コンポーネントのカスタマイズが有効になっている場合、仮想レポートスイートは **Analysis Workspace からのみ**&#x200B;アクセスでき、次の場所からはアクセスできません。
   >
   >* [!UICONTROL Data Warehouse]
   >* [!UICONTROL Report Builder]
   >* [!UICONTROL Activity Map]
   >* Analytics レポート API

   オンにすると、仮想レポートスイートに含めるコンポーネントを追加できます。それには、該当するコンポーネントを「除外されたコンポーネント」列から「含まれるコンポーネント」列にドラッグします。 含めたり除外したりできるコンポーネントは次のとおりです。

   * ディメンション
   * 指標
   * セグメント
   * 日付範囲

   >[!NOTE]
   >
   >キュレートされたコンポーネント（セグメント、計算指標、日付範囲）を&#x200B;*共有*&#x200B;する必要はありません。共有されていなくても、仮想レポートスイート用にキュレートされている場合は、Analysis Workspace で常に表示されます。

1. コンポーネントにフィルターを適用するかコンポーネントの検索を実行して「**[!UICONTROL すべてを追加]**」をクリックすると、選択されたすべてのコンポーネントが「含む」列に追加されます。

   ![](assets/vrs-add-all.png)

## コンポーネントの名前の変更 {#section_0F7CD9F684FE4765BC00A2AFED56550E}

仮想レポートスイートに固有の、含まれるコンポーネントの表示名を変更できます。 例えば、仮想レポートスイートにページ名を含め、よりモバイルに適したコンテキストに名前を変更する場合は、アプリScreensに変更できます。 この仮想レポートスイートが使用されるたびに、新しい名前がAnalysis Workspaceに表示されます。

![](assets/vrs-rename-component.png)

Analysis Workspaceで、含まれているコンポーネントの情報アイコンをクリックして、名前を変更したコンポーネントの元の名前を表示します。

![](assets/vrs-aw-renamed.png)

## コンポーネントグループ {#section_483BEC76F49E46ADAAA03F0A12E48426}

コンポーネントグループを使用すると、仮想レポートスイートに一括でコンポーネントを追加できます。 例えば、モバイルアプリ分析に固有のデフォルトコンポーネントセットを読み込む場合は、モバイルアプリ グループを選択します。 対応するディメンションと指標のセット（名前は変更済み）が、仮想レポートスイートの「含まれる」リストに自動的に追加されます。

![](assets/vrs-comp-grp.png)

## Workspace の動作 {#section_6C32F8B642804C0097FCB14E21028D4A}

Analysis Workspace のキュレーションについて詳しくは、[プロジェクトのキュレーションおよび共有](/help/analyze/analysis-workspace/curate-share/curate.md)を参照してください。
