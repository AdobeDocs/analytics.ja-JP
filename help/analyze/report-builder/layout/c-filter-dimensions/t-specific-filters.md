---
description: 値を直接指定するフィルターです。
title: 特定のフィルター
topic: Report builder
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 91%

---


# 特定のフィルター

値を直接指定するフィルターです。

条件に厳密に一致するフィルターを作成することにより、特定のディメンション項目を検索できます。例えば、[!DNL homepage.htm]、[!DNL contact_us.html]、[!DNL corporate_info.html] 内のページを抽出するフィルターを作成できます。

**特定のフィルターを作成するには**

1.  リクエストを作成または編集して、[!UICONTROL リクエストウィザード：ステップ 2] に進みます。

   ![手順の結果](assets/dimension_filter.png)

1.  [!UICONTROL リクエストウィザード：ステップ 2] で、グリッド内のディメンションの隣にあるリンクをクリックし、「**[!UICONTROL フィルター]**」を選択します。

   ![手順の結果](assets/choose_page_specific01.png)

1. 「**[!UICONTROL リストから選択]**」を有効にして、次のいずれかのオプションを有効にします。

   * **セル範囲から選択：**&#x200B;セルからデータを選択します。以下を選択できます。
   * **範囲内のすべてのセル：**&#x200B;範囲内のすべてのセルからフィルター条件を読み取ります。説明テキストでは、選択する必要のあるセルのグループ数が指定されます。隣接しない複数の領域を指定するには、Ctrl キーを押しながらセル範囲を指定します。マッピングする必要のある範囲に含まれるセルが 1 つのみである場合は、使用できるのはこのオプションだけになります。
   * **範囲の最初のセル：**&#x200B;選択する必要があるのは、範囲の左上のセルのみで、次に、データの方向を指定します。また、リクエストに複数の期間が含まれる場合、期間の方向を選択して、期間と期間の間のセルをいくつかスキップするかどうかを選択します。
   * **リストから選択：**&#x200B;データの追加先のリストからデータを選択します。
1. 「**[!UICONTROL リストから選択]**」を有効にする場合は、使用可能な項目をリストから選択するか、「**[!UICONTROL 追加]**」をクリックします。

   When you click **[!UICONTROL Add]**, the [!UICONTROL Select From List] form displays a list of available dimension items for the current request date range, limited to the first 10,000 items. これらの項目を検索することもできます。または、「**[!UICONTROL その他...]**」をクリックして[!UICONTROL 「検索」フォーム]を表示し、ディメンションのより詳細な検索を行います。
1. 「[!UICONTROL リストから選択]」で、「**[!UICONTROL OK]**」をクリックします。
1. 「[!UICONTROL ページを選択]」フォームでフィルターを保存して、「**[!UICONTROL OK]**」をクリックします。
