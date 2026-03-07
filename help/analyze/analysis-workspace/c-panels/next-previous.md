---
description: 特定のディメンションの次の項目または前の項目を表示する、次または前の項目パネルの使用方法を説明します。
title: 次または前の項目パネル
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 88%

---

# 次または前の項目パネル {#next-or-previous-item-panel}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="次または前の項目"
>abstract="パネルを作成して、ユーザーが来訪前にいたディメンションまたはユーザーが次に移動するディメンションを理解します。"

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="次または前の項目"
>abstract="訪問者が来訪前にいた場所または次に移動する場所として最も一般的なものを分析します。<br/><br/>**ディメンション**：ディメンションを選択します。例：**ページ**。<br/>**ディメンション項目**：特定のディメンション項目を選択します。例：**ホームページ**。<br/>**方向**：「**次へ**」を選択すると、選択したディメンション項目の直後のディメンション項目が表示されます。「**前へ**」を選択すると、選択したディメンション項目に至るまでのディメンション項目が表示されます。<br/>**コンテナ**：「**セッション**」を選択して同じセッション内の次／前のディメンション項目を表示するか、「**ユーザー**」を選択して同じユーザーの次／前のディメンション項目を表示します。"

>[!BEGINSHADEBOX]

_この記事では、_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** の次または前の項目パネルについて説明します。_<br/>_この記事の [CustomerJourneyAnalytics](/help/analyze/analysis-workspace/c-panels/next-previous.md)_ ![Customer Journey Analytics](/help/assets/icons/CustomerJourneyAnalytics.svg) バージョンについては、_&#x200B;**次または前の項目パネル** を参照してください。_

>[!ENDSHADEBOX]

**[!UICONTROL 次または前の項目]**&#x200B;パネルには、特定のディメンションの次または前のディメンション項目を識別する多数のテーブルおよびビジュアライゼーションが含まれています。例えば、顧客がホームページを訪問した後に、どのページを最も頻繁に訪問したかを探索する必要があるとします。

## 使用

**[!UICONTROL 次または前の項目]**&#x200B;パネルを使用するには：

1. **[!UICONTROL 次または前の項目]**&#x200B;パネルを作成します。パネルの作成方法について詳しくは、[パネルの作成](panels.md#create-a-panel)を参照してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。

### パネル入力

次の入力設定を使用して、[!UICONTROL 次または前の項目]パネルを設定できます。

![次または前の項目パネル](assets/next-or-previous-item.png)

| 入力 | 説明 |
| --- | --- |
| **[!UICONTROL ディメンション]** | 次または前の項目を探索するディメンションを選択します。 |
| **[!UICONTROL ディメンション項目]** | 次／前のお問い合わせの中心となる特定のディメンション項目を選択します。 |
| **[!UICONTROL 方向]** | [!UICONTROL 次]または[!UICONTROL 前]のどちらのディメンション項目を検索するかを指定します。 |
| **[!UICONTROL コンテナ]** | コンテナ **[!UICONTROL 訪問]** または **[!UICONTROL 訪問者]** （デフォルト）を選択して、問い合わせの範囲を決定します。 |

{style="table-layout:auto"}

「**[!UICONTROL 作成]**」を選択して、パネルを作成します。

### パネル出力

[!UICONTROL 次または前の項目]パネルでは、豊富なデータとビジュアライゼーションのセットが返されるので、特定のディメンション項目の前後の発生件数をより深く理解できます。

![次／前のパネル出力](assets/next-or-previous-item-output.png)


| ビジュアライゼーション | 説明 |
| --- | --- |
| **[!UICONTROL 横棒グラフ]** | 選択したディメンション項目に基づいて、次の（または前の）項目を一覧表示します。個々のバーの上にポインタを合わせると、フリーフォームテーブル内の対応する項目がハイライト表示されます。 |
| **[!UICONTROL 数値の概要]** | 今月（これまで）のすべての次または前のディメンション項目の発生件数の概要。 |
| **[!UICONTROL フリーフォームテーブル]** | 選択したディメンション項目に基づいて、次の（または前の）項目を表形式で一覧表示します。例えば、ホームページまたはワークスペースページの後（または前）にその人物が訪問した一番人気のページ（発生ごと）。 |

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