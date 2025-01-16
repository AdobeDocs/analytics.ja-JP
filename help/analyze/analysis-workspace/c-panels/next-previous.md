---
description: 特定のディメンションの次または前のディメンション項目を表示するパネル。
title: 次または前の項目パネル
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: 9a29057e71627d4c77a1d039d7fd5b0ec9c0f447
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 36%

---

# 次または前の項目パネル {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="次または前の項目"
>abstract="パネルを作成して、ユーザーが来訪前にいたディメンションまたはユーザーが次に移動するディメンションを理解します。"

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="次または前の項目"
>abstract="訪問者が来訪前にいた場所または次に移動する場所として最も一般的なものを分析します。<br/><br/>**ディメンション**：ディメンションを選択します。例：**ページ**。<br/>**ディメンション項目**：特定のディメンション項目を選択します。例：**ホームページ**。<br/>**方向**：「**次へ**」を選択すると、選択したディメンション項目の直後のディメンション項目が表示されます。「**前へ**」を選択すると、選択したディメンション項目に至るまでのディメンション項目が表示されます。<br/>**コンテナ**：「**セッション**」を選択して同じセッション内の次／前のディメンション項目を表示するか、「**ユーザー**」を選択して同じユーザーの次／前のディメンション項目を表示します。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*この記事は、![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)**Adobe Analyticsの次または前の項目パネルに関する説明です**。<br/> この記事の [](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)**Customer Journey Analytics**バージョンについては、![ 次または前の項目パネル* を参照してください。

>[!ENDSHADEBOX]

**[!UICONTROL 次または前の項目]** パネルには、特定のディメンションの次または前のディメンション項目を識別する多数のテーブルおよびビジュアライゼーションが含まれています。 例えば、顧客がホームページを訪問した後に最も頻繁に訪問したページを調べる必要があるとします。

## 使用

**[!UICONTROL 次または前の項目]** パネルを使用するには：

1. **[!UICONTROL 次または前の項目]** パネルを作成します。 パネルの作成方法について詳しくは、[パネルの作成](panels.md#create-a-panel)を参照してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。

### パネル入力

[!UICONTROL  次または前の項目 ] パネルは、次の入力設定を使用して設定できます。

![ 次または前の項目パネル ](assets/next-or-previous-item.png)

| 入力 | 説明 |
| --- | --- |
| **[!UICONTROL ディメンション]** | 次または前の項目を調査するディメンションを選択します。 |
| **[!UICONTROL ディメンション項目]** | 次/前の問い合わせの中央にある特定のディメンション項目を選択します。 |
| **[!UICONTROL 方向]** | 検索するディメンション項目が [!UICONTROL  次へ ] か [!UICONTROL  前へ ] かを指定します。 |
| **[!UICONTROL コンテナ]** | コンテナ [!UICONTROL  セッション ] または [!UICONTROL  個人 ] （デフォルト）を選択して、問い合わせの範囲を決定します。 |

{style="table-layout:auto"}

**[!UICONTROL ビルド]** を選択して、パネルをビルドします。

### パネル出力

[!UICONTROL  次または前の項目 ] パネルは、豊富なデータとビジュアライゼーションのセットを返し、特定のディメンション項目の後または前の発生件数をより深く理解するのに役立ちます。


![ 次/前のパネル出力 ](assets/next-or-previous-item-output.png)


| ビジュアライゼーション | 説明 |
| --- | --- |
| **[!UICONTROL 横棒グラフ]** | 選択したディメンション項目に基づいて、次の項目（または前の項目）をリストします。 個々のバーの上にマウスポインターを置くと、フリーフォームテーブルの対応する項目がハイライトされます。 |
| **[!UICONTROL 数値の概要]** | 当月（これまで）の次または前のすべてのディメンション項目の発生件数の概要。 |
| **[!UICONTROL フリーフォームテーブル]** | 選択したディメンション項目に基づいて、次の（または前の）項目をテーブル形式でリストします。 例えば、ユーザーがホームページまたは Workspace ページの後（または前）に移動した、最も人気の高いページ（発生件別）です。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[パネルの作成](/help//analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>

<!--
# Next or previous item panel

This panel contains a number of tables and visualizations to easily identify the next or previous dimension item for a specific dimension. For example, you might want to explore which pages customers went to most often after they visited the Home page.

## Access the panel

You can access the panel from within [!UICONTROL Reports] or within [!UICONTROL Workspace].

| Access point | Description |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>The panel is already dropped into a project.</li><li>The left rail is collapsed.</li><li>If you selected [!UICONTROL Next page], default settings have already been applied, such as [!UICONTROL Page] for [!UICONTROL Dimension], and the top page as the [!UICONTROL Dimension Item], [!UICONTROL Next] for [!UICONTROL Direction] and [!UICONTROL Visit] for [!UICONTROL Container]. You can modify all these settings.</li></ul>![Next/Previous panel](assets/next-previous.png)|
| Workspace | Create a new project and select the Panel icon in the left rail. Then drag the [!UICONTROL Next or previous item] panel above the Freeform table. Notice that the [!UICONTROL Dimension] and [!UICONTROL Dimension Item] fields are left blank. Select a dimension from the drop-down list. [!UICONTROL Dimension items] are populated based on the [!UICONTROL dimension] you chose. The top dimension item gets added, but you can select a different item. The defaults are Next and Visitor. Again, you can modify these as well.<p>![Next/Previous panel](assets/next-previous2.png) |

{style="table-layout:auto"}

## Panel Inputs {#Input}

You can configure the [!UICONTROL Next or previous item] panel panel using these input settings:

| Setting | Description |
| --- | --- |
| Segment (or other component) drop zone | You can drag and drop segments or other components to further filter your panel results. |
| Dimension | The dimension for which you want to explore next or previous items. |
| Dimension Item | The specific item at the center of your next/previous inquiry. |
| Direction | Specify whether you are looking for the [!UICONTROL Next] or the [!UICONTROL Previous] dimension item. |
| Container | [!UICONTROL Visit] or [!UICONTROL Visitor] (default) determine the scope of your inquiry. |

{style="table-layout:auto"}

Click **[!UICONTROL Build]** to build the panel.

## Panel output {#output}

The [!UICONTROL Next or previous item] panel returns a rich set of data and visualizations to help you better understand what occurrences follow or precede specific dimension items.

![Next/Previous panel output](assets/next-previous-output.png)

![Next/Previous panel output](assets/next-previous-output2.png)

| Visualization | Description |
| --- | --- |
| Horizontal bar | Lists the next (or previous) items based on the dimension item you chose. Hovering over an individual bar highlights the corresponding item in the Freeform table. |
| Summary number | High-level summary number of all next or previous dimension item occurrences for the current month (so far.) |
| Freeform table | Lists the next (or previous) items based on the dimension item you chose, in a table format. For example, which were the most popular pages (by occurrences) that people went to after (or before) the home page or the workspace page. |

{style="table-layout:auto"}

-->