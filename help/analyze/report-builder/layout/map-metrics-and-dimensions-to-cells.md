---
description: スプレッドシートへの項目のマッピングを開始する前に、スプレッドシートが保護されていないことを確認してください。ワークシートの保護によってユーザーの操作が妨げられると、スプレッドシートでセルを選択できなくなります。まず、シートの保護を解除してから、セルのマッピングを追加してください。
seo-description: スプレッドシートへの項目のマッピングを開始する前に、スプレッドシートが保護されていないことを確認してください。ワークシートの保護によってユーザーの操作が妨げられると、スプレッドシートでセルを選択できなくなります。まず、シートの保護を解除してから、セルのマッピングを追加してください。
seo-title: 指標とディメンションのセルへのマッピング
solution: Analytics
title: 指標とディメンションのセルへのマッピング
topic: Report Builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 指標とディメンションのセルへのマッピング

スプレッドシートへの項目のマッピングを開始する前に、スプレッドシートが保護されていないことを確認してください。ワークシートの保護によってユーザーの操作が妨げられると、スプレッドシートでセルを選択できなくなります。まず、シートの保護を解除してから、セルのマッピングを追加してください。

マッピングできる領域およびセルの数は、選択した指標、精度、日付範囲および設定したフィルターによって異なります。例えば、[!UICONTROL サイト指標]／[!UICONTROL トラフィックレポート]を選択し、精度に「[!UICONTROL 週]」を設定し、日付範囲に「[!UICONTROL 過去 2 週間]」を設定した場合、[!UICONTROL リクエストウィザード：ステップ 2] で 3 つのセルをマッピングするように求められます（[!UICONTROL カスタムレイアウト]を使用している場合）。リクエストによって、第 1 週目のデータと第 2 週目のデータが取得されます。この際、各データポイントの値は、ページビューの値と同じになります。3 つ目のセルは行ヘッダーとなります。この行ヘッダーは、「[!UICONTROL フォーマットオプション]」を使用して設定できます。

スプレッドシートで互換性のない場所を誤ってマッピングした場合は、Report Builder でエラーが表示されます。

詳細は以下の節に説明されています。

* [セルの範囲の選択](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [セル選択のテクニック](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [マッピングの問題](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Select a Range of Cells {#section_1E37FB46DA194FB7A1050B8833A48AC6}

[!UICONTROL リクエストウィザード：ステップ 2] で、トレンドリクエストに対して「[!UICONTROL カスタムレイアウト]」を有効にすると、セルの一定の範囲にリクエストをマッピングすることができます。

**[!UICONTROL 範囲セレクター]**![select_ cell_ icon. pngをクリックします](assets/select_cell_icon.png)

をクリックします。

* ** All Cells in Range:** Requires you to select a group of cells for a [!UICONTROL Custom Layout] style request.

* ** First Cell of Range:** Lets you select the top-left cell of the range, and displays the [!UICONTROL Range] orientation to specify the horizontal or vertical orientation of input and output cells (column or row). このオプションを使用すると、Report Builder によってセルが自動的に選択されます。

* **範囲の方向:**セル範囲を列または行として指定できます。
* **範囲の先頭のセルを選択：**&#x200B;セル参照を表示します。

## Techniques for selecting cells {#section_760421C3D7F84D67A639174710C93B22}

**[!UICONTROL 範囲選択]** アイコン ![をクリックして、データを選択します。"_ cell_ icon. png"](assets/select_cell_icon.png)

 をクリックし、スプレッドシートで選択したいセル範囲をマウスでクリック＆ドラッグして、データを選択します。連続した選択領域が、黒の枠線で囲まれます。

![](assets/twenty_cells.gif)

離れた行を選択した場合は、各行の周りに細い白の枠線が表示されます。

![](assets/twoXten_cells_highlighted.gif)

1 つのリクエスト内で離れた複数の行をマッピングするには、[!UICONTROL Ctrl] キーを使用して、選択したいセルの上でカーソルをクリックおよびドラッグします。例えば、40 セル分の連続した領域 1 つではなく、それぞれ 10 セル分の 4 つの領域に対してリクエストを作成するような場合に、これを実行します。

![](assets/map4.png)

セルの選択後、**[!UICONTROL 範囲の選択]フォームの**[!UICONTROL 範囲選択アイコン]を再度クリックして、[!UICONTROL リクエストウィザード：ステップ 2] に戻ります。

## Issues when mapping {#section_CC1BCF841291447EB3A994EB08F3A099}

有効なマッピングが既に存在するセルに対して誤ってマッピングした場合は、範囲選択アイコンの隣にあるテキストボックスにセル参照が表示されません。「[!UICONTROL OK]」をクリックすると、Report Builder に「選択した範囲は別のリクエストの範囲と交差します。選択を変更してください。」というエラーが表示されます。

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

このメッセージが表示されないようにするには、次の 2 つの方法があります。

* リクエストとマッピングが設定されたセルへの書式を設定して、見た目で区別できるようにします。
* マッピングを含むスプレッドシートの領域を確認します。

リクエストが埋め込まれている領域を確認するには、次の方法があります。

* [!UICONTROL リクエストマネージャー]を起動し、表示される個々のリクエストをクリックします。リクエストをクリックすると、リクエストがマッピングされているスプレッドシート内のセルが強調表示されます。
* リクエストマネージャーを起動し、新しいマッピングのために使用するセルを選択し、「[!UICONTROL シートから取得]」をクリックします。[!UICONTROL リクエストマネージャー]によって、選択されたセルと交差する出力項目があるリクエストがリスト内で選択されます。選択されるリクエストがない場合は、そのセルを使用することができます。

* スプレッドシートでセルを選択し、右クリックでコンテキストメニューを表示し、「[!UICONTROL リクエストを編集]」を選択できるかどうかを確認します。選択できる場合は、そのセルに関連付けられたリクエストが存在します。

