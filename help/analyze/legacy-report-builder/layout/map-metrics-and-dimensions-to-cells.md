---
description: セルの範囲を選択する方法、セルを選択する方法、マッピングの問題のトラブルシューティングについて説明します。
title: 指標およびディメンションのセルへのマッピングについて説明します
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: User, Admin
exl-id: e63fc679-39eb-417b-9a2b-6620db63a824
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 69%

---

# 指標およびディメンションのセルへのマッピング

{{legacy-arb}}

スプレッドシートへの項目のマッピングを開始する前に、スプレッドシートが保護されていないことを確認してください。ワークシートの保護によってユーザーの操作が妨げられると、スプレッドシートでセルを選択できなくなります。まず、シートの保護を解除してから、セルのマッピングを追加してください。

マッピングする領域とセルの数は、選択した指標、精度、日付範囲、設定したフィルターによって異なります。 例えば、[!UICONTROL &#x200B; サイト指標 &#x200B;]/[!UICONTROL &#x200B; トラフィックレポート &#x200B;] を選択し、[!UICONTROL &#x200B; 週 &#x200B;] 精度を設定し、[!UICONTROL &#x200B; 過去 2 週間 &#x200B;] の日付範囲を設定した場合、[!UICONTROL &#x200B; リクエストウィザード：手順 2] で 3 つのセルをマッピングするように求められます（[!UICONTROL &#x200B; カスタムレイアウト &#x200B;] を使用する場合）。 リクエストは、1 週目のデータと 2 週目のデータを取得します。各データポイント値はページビューの値と等しくなります。 3 つ目のセルは行ヘッダーとなります。この行ヘッダーは、「[!UICONTROL フォーマットオプション]」を使用して設定できます。

互換性のない場所をスプレッドシートに誤ってマッピングすると、Report Builderでエラーが発生します。

詳しくは、次の項を参照してください。

* [セルの範囲の選択 ](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [セル選択のテクニック ](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [マッピングの問題](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## セルの範囲の選択 {#section_1E37FB46DA194FB7A1050B8833A48AC6}

[!UICONTROL リクエストウィザード：ステップ 2] で、トレンドリクエストに対して「[!UICONTROL カスタムレイアウト]」を有効にすると、セルの一定の範囲にリクエストをマッピングすることができます。

マッピングする項目の横にある **[!UICONTROL 範囲セレクター]** ![select_cell_icon.png](assets/select_cell_icon.png) をクリックします。

* **範囲内のすべてのセル：**&#x200B;[!UICONTROL カスタムレイアウト]スタイルのリクエストに対して、セルの範囲を選択する必要があります。
* **範囲の最初のセル：**&#x200B;範囲の左上にあたるセルを選択します。その後、「[!UICONTROL 範囲の方向]」が表示されるので、そこで入力セルと出力セル（列または行）について、縦方向または横方向を指定します。Report Builderにセルを選択させるには、このオプションを使用します。
* **範囲の方向：**&#x200B;列または行としてセル範囲の方向を指定します。
* **範囲の先頭のセルを選択：**&#x200B;セル参照を表示します。

## 細胞の選別テクニック {#section_760421C3D7F84D67A639174710C93B22}

**[!UICONTROL 範囲選択]**&#x200B;アイコン ![select_cell_icon.png](assets/select_cell_icon.png) をクリックして日付を設定できます。

 をクリックし、スプレッドシートで選択したいセル範囲をマウスでクリック＆ドラッグして、データを選択します。連続した選択領域が、黒の枠線で囲まれます。

![](assets/twenty_cells.gif)

離れた行を選択した場合は、各行の周りに細い白の枠線が表示されます。

![](assets/twoXten_cells_highlighted.gif)

1 つのリクエスト内で離れた複数の行をマッピングするには、[!UICONTROL Ctrl] キーを使用して、選択したいセルの上でカーソルをクリックおよびドラッグします。例えば、40 セル分の連続した領域 1 つではなく、それぞれ 10 セル分の 4 つの領域に対してリクエストを作成するような場合に、これを実行します。

![](assets/map4.png)

セルの選択後、[!UICONTROL 範囲の選択]フォームの&#x200B;**[!UICONTROL 範囲選択アイコン]**&#x200B;を再度クリックして、[!UICONTROL リクエストウィザード：ステップ 2] に戻ります。

## マッピングの問題のトラブルシューティング{#section_CC1BCF841291447EB3A994EB08F3A099}

既にアクティブなマッピングがあるセルに誤ってマッピングすると、範囲選択アイコンの横のテキストボックスにセル参照が表示されません。 [!UICONTROL OK] をクリックすると、Report Builderに次のエラーが表示されます。*選択した範囲は、別のリクエストの範囲と重なっています。*&#x200B;選択を変更してください。

* このセルを使用する必要がある場合は、セル（複数の場合もあります）を右クリックして、「**[!UICONTROL リクエストを削除]**」を選択します。

このメッセージが表示されないようにするには、次の 2 つの方法があります。

* リクエストとマッピングが設定されたセルへの書式を設定して、見た目で区別できるようにします。
* マッピングを含むスプレッドシートの領域を確認します。

リクエストが埋め込まれている領域を確認するには、次の方法があります。

* [!UICONTROL リクエストマネージャー]を起動し、表示される個々のリクエストをクリックします。リクエストをクリックすると、リクエストがマッピングされているスプレッドシート内のセルが強調表示されます。
* リクエストマネージャーを起動し、新しいマッピングのために使用するセルを選択し、「[!UICONTROL シートから取得]」をクリックします。[!UICONTROL リクエストマネージャー]によって、選択されたセルと交差する出力項目があるリクエストがリスト内で選択されます。選択されるリクエストがない場合は、そのセルを使用することができます。
* スプレッドシートでセルを選択し、右クリックでコンテキストメニューを表示し、「[!UICONTROL リクエストを編集]」を選択できるかどうかを確認します。選択できる場合は、そのセルに関連付けられたリクエストが存在します。
