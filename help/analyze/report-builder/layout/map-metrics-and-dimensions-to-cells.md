---
description: スプレッドシートへの項目のマッピングを開始する前に、スプレッドシートが保護されていないことを確認してください。ワークシートの保護によってユーザーの操作が妨げられると、スプレッドシートでセルを選択できなくなります。まず、シートの保護を解除してから、セルのマッピングを追加してください。
title: 指標およびディメンションのセルへのマッピング
topic: Report builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 指標およびディメンションのセルへのマッピング

スプレッドシートへの項目のマッピングを開始する前に、スプレッドシートが保護されていないことを確認してください。ワークシートの保護によってユーザーの操作が妨げられると、スプレッドシートでセルを選択できなくなります。まず、シートの保護を解除してから、セルのマッピングを追加してください。

マッピングできる領域およびセルの数は、選択した指標、精度、日付範囲および設定したフィルターによって異なります。例えば、/を選択し、精度を設 [!UICONTROL Site Metric] 定し、の日付範囲を設 [!UICONTROL Traffic Report][!UICONTROL Week][!UICONTROL Last 2 Weeks][!UICONTROL Custom Layout][!UICONTROL Request Wizard: Step 2]定すると、（を使用している場合）3つのセルを リクエストによって、第 1 週目のデータと第 2 週目のデータが取得されます。この際、各データポイントの値は、ページビューの値と同じになります。Your third cell serves as the row heading, which you can configure using [!UICONTROL Format Options].

スプレッドシートで互換性のない場所を誤ってマッピングした場合は、Report Builder でエラーが表示されます。

詳しくは以下のセクションで説明されています。

* [セルの範囲の選択 ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [セル選択のテクニック ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [マッピングの問題 ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## セルの範囲の選択 {#section_1E37FB46DA194FB7A1050B8833A48AC6}

On the [!UICONTROL Request Wizard: Step 2], when you enable [!UICONTROL Custom Layout] for a trended request, you can map the request to a range of cells.

**[!UICONTROL Range Selector]**![ select_cell_icon.png](assets/select_cell_icon.png)

をクリックします。

* **範囲内のすべてのセル：** スタイルリクエストのセルのグループを選択する必要 [!UICONTROL Custom Layout] があります。
* **範囲の最初のセル：** 範囲の左上のセルを選択し、方向を表示して、入力セルと出力セル（列または行） [!UICONTROL Range] の水平方向または垂直方向を指定します。 このオプションを使用すると、Report Builder によってセルが自動的に選択されます。
* **範囲の方向：**&#x200B;列または行としてセル範囲の方向を指定します。
* **範囲の先頭のセルを選択：**&#x200B;セル参照を表示します。

## セル選択のテクニック {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

 をクリックし、スプレッドシートで選択したいセル範囲をマウスでクリック＆ドラッグして、データを選択します。連続した選択領域が、黒の枠線で囲まれます。

![](assets/twenty_cells.gif)

離れた行を選択した場合は、各行の周りに細い白の枠線が表示されます。

![](assets/twoXten_cells_highlighted.gif)

To map separate rows in one request, use the [!UICONTROL Control] key, then click and drag the cursor over the desired cells. 例えば、40 セル分の連続した領域 1 つではなく、それぞれ 10 セル分の 4 つの領域に対してリクエストを作成するような場合に、これを実行します。

![](assets/map4.png)

セルを選択した後、フォーム上 **[!UICONTROL Range Selector]** のを再度ク [!UICONTROL Range Selection] リックして、に戻ります [!UICONTROL Request Wizard: Step 2]。

## マッピングの問題 {#section_CC1BCF841291447EB3A994EB08F3A099}

有効なマッピングが既に存在するセルに対して誤ってマッピングした場合は、範囲選択アイコンの隣にあるテキストボックスにセル参照が表示されません。「[!UICONTROL OK]」をクリックすると、Report Builder に「選択した範囲は別のリクエストの範囲と交差します。選択を変更してください。」というエラーが表示されます。

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

このメッセージが表示されないようにするには、次の 2 つの方法があります。

* リクエストとマッピングが設定されたセルへの書式を設定して、見た目で区別できるようにします。
* マッピングを含むスプレッドシートの領域を確認します。

リクエストが埋め込まれている領域を確認するには、次の方法があります。

* Launch the [!UICONTROL Request Manager] and click on individual requests listed in the table. リクエストをクリックすると、リクエストがマッピングされているスプレッドシート内のセルが強調表示されます。
* Select cells in the spreadsheet you intend to use for a new mapping and click [!UICONTROL From Sheet]. The [!UICONTROL Request Manager] selects the request in the list which has an output item that intersects the selected cell. 選択されるリクエストがない場合は、そのセルを使用することができます。
* Select cells in the spreadsheet, right-click in the context menu and verify if [!UICONTROL Edit Request] is available. 選択できる場合は、そのセルに関連付けられたリクエストが存在します。
