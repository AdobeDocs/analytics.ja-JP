---
description: Analysis Workspace プロジェクトからデータをダウンロードする様々な方法について説明します。
title: プロジェクトとデータのダウンロード
feature: Curate and Share
role: User, Admin
exl-id: 085013dc-8263-4fc8-9492-99f0ecadf14b
TQID: https://experienceleague.adobe.com/J8dtgju7PdHVywseS7KVuCfboHN3lj08sClKiEB7Wvk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e318d41c-1d01-4c1e-9b18-1f61d435ceee
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 24842ee0a9fd32e3f55424b184680f417c7fbfd7
workflow-type: tm+mt
source-wordcount: 1131
ht-degree: 25%

---

# プロジェクトとデータのダウンロード

Analysis Workspace プロジェクトとデータをローカルデバイスにダウンロードできます。 このダウンロードは、データのコピー、CSV （コンマ区切り値データ）ファイル、またはPDF（ポータブルドキュメントフォーマット）ドキュメントに使用できます。

* ダウンロードしたファイルにビジュアライゼーションを含める場合は、「PDF」オプションを選択します。
* プレーンテキストデータが必要な場合は、「CSVとコピー済みデータ」オプションを選択します。

Adobe Analytics データを書き出す他の方法については、[書き出しガイド &#x200B;](/help/export/home.md)を参照してください。

## プロジェクトをPDFまたはCSV ファイルとしてダウンロード

![「CSV をダウンロード」および「PDF をダウンロード」オプションをハイライト表示するプロジェクトドロップダウンメニュー](assets/download-project.png)

### プロジェクトをPDF ファイルとしてダウンロード

PDFとしてプロジェクトをダウンロードする際は、次の点を考慮してください。

* プロジェクトがワークステーションにダウンロードされるまで、プロジェクトを離れないでください。 PDFをレンダリングするためにAdobe サーバー上でプロジェクトを再実行するため、ダウンロードには数分かかる場合があります。 ダウンロードのレンダリング中も、引き続きプロジェクトに変更を加えることができます。 PDFのレンダリングに5分以上かかる場合は、代わりに[PDF](../curate-share/send-schedule-files.md)に電子メールを送信するように求められます。
* ダウンロードは、ページ番号が適用されない単一ページとしてレンダリングされます。
* PDFには、Analysis Workspaceのブラウザーページに表示される内容が含まれています。 切り捨てられたコンテンツを避けるには、![&#x200B; サイズ変更](/help/assets/icons/Resize.svg)を選択して、カスタムサイズのビジュアライゼーションまたはパネルのサイズを自動的に変更します。
* フリーフォームテーブル内の[&#x200B; ハイパーリンク &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)は、ダウンロードしたPDFでクリックできます。

プロジェクトをPDF ファイルとしてダウンロードするには：

1. 「**[!UICONTROL プロジェクト]**」 > 「**[!UICONTROL PDFをダウンロード]**」を選択します。

   緑色のバーが表示され、次のメッセージが表示されます。![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL ダウンロードがリクエストされました。 お待ちください。]**

1. ダウンロードの準備が整うと、緑色のバーが表示され、次のメッセージが表示されます。![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *プロジェクトの名前&#x200B;*PDFの準備ができました。]**

1. 緑色のバーで「**[!UICONTROL ダウンロード]**」を選択します。

   ブラウザーの設定に応じて、PDFは以前に設定したフォルダーに自動的にダウンロードされるか、PDFがダウンロードされるフォルダーを選択するように求められます。

   ファイル名は、*プロジェクト名*～*レポートスイート名*～*日付*&#x200B;で構成されています。 例：`Example Project - Omni-Channel - Luma - Jun 30, 2025.pdf`。

### プロジェクトをCSV ファイルとしてダウンロード

1. **[!UICONTROL プロジェクト]**/**[!UICONTROL CSVをダウンロード]**&#x200B;を選択します。

   ブラウザーの設定に応じて、CSV ファイルは以前に設定したフォルダーに自動的にダウンロードされるか、CSV ファイルがダウンロードされるフォルダーを選択するように求められます。

   ファイル名は、*プロジェクト名*～*レポートスイート名*～*日付*&#x200B;で構成されています。 例：`Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`。

## ビジュアライゼーション内のデータをクリップボードにコピーする

コンテキストメニューの「**[!UICONTROL クリップボードにコピー]**」オプションを使用すると、Analysis Workspaceからデータをすばやくコピーして、サードパーティツールに貼り付けることができます。

* 表示されたテーブルデータをコピーする場合は、テーブルヘッダーを選択し、コンテキストメニューから「**データをクリップボードにコピー**」を選択します。
* データのサブセットをコピーする場合は、テーブルで選択し、コンテキストメニューから「**選択範囲をクリップボードにコピー**」を選択します。

>[!TIP]
>
>ホットキー&#x200B;**_cmd + c_** （macOS）または&#x200B;**_ctrl + c_** （Windows）を使用して、選択範囲をクリップボードにコピーできます。 次に、**_cmd + v_** （macOS）または&#x200B;**_ctrl + v_** （Windows）を使用して、データを貼り付けます。


![「選択内容をクリップボードにコピー」オプション。](assets/copy-clipboard.png){zoomable="yes"}

## ビジュアライゼーション内のデータをCSV ファイルとしてダウンロードする

コンテキストメニューの「CSVとしてダウンロード」オプションを使用すると、任意のビジュアライゼーションのデータテーブルまたはデータソースをCSVとしてダウンロードできます。

それには、次の手順を実行します。

* 任意のテーブルまたはビジュアライゼーションのヘッダーから、コンテキストメニューから「**[!UICONTROL データをCSVとしてダウンロード]**」を選択します。 これにより、テーブルに表示されたデータやビジュアライゼーションの基になるデータソースが CSV 形式でダウンロードされます。

<!--
Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* テーブル内で、コンテキストメニューから「**[!UICONTROL 選択をCSV]**&#x200B;としてダウンロード」を選択します。 このオプションでは選択内容のみがダウンロードされ、表示されているテーブル全体はダウンロードされません。

![「データを CSV 形式でダウンロード」オプション](assets/download-data-as-csv.png)

## 項目をCSV ファイルとしてダウンロード

表内の表示される400行を超えるデータを分析する場合は、表見出しまたは任意の行のコンテキストメニューから&#x200B;**項目をCSV （_Dimension名_）**&#x200B;としてダウンロードを選択します。 このオプションでは、選択したディメンションに対して、並べ替えオプションとフィルターを適用した最大 50,000 個のディメンション項目（テーブルの並べ替えに基づく）を書き出します。 テーブルの上部からこのオプションを選択すると、テーブルの最初のディメンションが書き出されます。

![「項目を CSV としてダウンロード（ページ）」オプション](assets/download-items-as-csv.png)

フリーフォームテーブルには制限は適用されません。 最適なパフォーマンスを確保するために、20列未満のテーブルでこのオプションを使用することをお勧めします。

>[!TIP]
>
> ディメンションが 50,000 項目を超える場合は、異なる並べ替え指標が適用されたファイルをダウンロードするか、セグメントを適用します。 例えば、あるダウンロードでは訪問回数の降順で並べ替え、2 回目のダウンロードでは訪問回数の昇順で並べ替えます。 この説明は、ロングテールの項目を取得するのに役立ちます。

プロジェクト内で複数のタスクを使用できます。また、ダウンロードの処理中に、同じタブで新しい Workspace プロジェクトに移動することもできます。 新しいブラウザータブを開くと、ダウンロードは一時停止します。 Workspace を完全に終了するか、ブラウザータブを閉じると、ダウンロードはキャンセルされます。


### ダウンロードした項目ファイル {#items-file}

フリーフォームテーブルの次の機能は、ダウンロードしたファイルに適用されます。

* すべてのパネルセグメントがフィルターとして適用されます。
* テーブルで選択されたディメンションの&#x200B;**上**&#x200B;の分類は、各列よりも上のフィルターとして適用されます。
* テーブル内で選択されたディメンションよりも&#x200B;**下**&#x200B;の分類は削除されます。

![Excel で開かれた、ダウンロードした .csv ファイル。](assets/download-items-file.png)

### ダウンロード通知 {#notifications}

ファイルがダウンロードされると、次の通知が表示されます。

* 青い&#x200B;**[!UICONTROL _テーブル名&#x200B;_-_Dimension _.csvがリクエストされました。_x _%完了]**&#x200B;進行状況を示します。 いつでもダウンロードをキャンセルするには、「**[!UICONTROL ダウンロードをキャンセル]**」を選択します。 メッセージを閉じる場合は、![CrossSize100](/help/assets/icons/CrossSize100.svg)を選択します。これにより、ダウンロードがキャンセルされません。
* ファイルのダウンロードが完了すると、緑色の&#x200B;**[!UICONTROL _テーブル名&#x200B;_-_Dimension _.csvがダウンロードされました]**。 ファイルは、ブラウザー用に設定されたダウンロードフォルダーにダウンロードされます。

一度に複数のダウンロードをリクエストする場合、前のダウンロードが完了するまで、追加のダウンロードがキューに入れられるという通知が届きます。


## FAQ

| 質問 | 回答 |
| --- | --- |
| ダウンロードしたPDFが1 ページのみなのはなぜですか？ | [PDFのダウンロード &#x200B;](#download-as-csv-or-pdf)機能では、ダウンロードしたPDFにページネーションを設定できません。 |
| **[!UICONTROL 項目をCSV]**&#x200B;としてダウンロードするオプションを使用して、50,000件以上の項目を書き出せますか？ | 各ダウンロードには最大 50,000 個のディメンションアイテムを含めることができますが、テーブルの種類を変更してテールがより長いアイテムを取得したり、フィルターを適用して特定のアイテムをダウンロードしたりできます。 |
| 「**[!UICONTROL ビジュアライゼーションをコピー]**」は何を実行しますか？ | [!UICONTROL **クリップボードにデータをコピー**]&#x200B;または&#x200B;[!UICONTROL **クリップボードに選択範囲をコピー**]&#x200B;とは異なり、**[!UICONTROL ビジュアライゼーションをコピー]** コンテキストメニューオプションは書き出しオプションではありません。 このオプションを使用すると、Workspaceのある場所から別の場所に[&#x200B; ビジュアライゼーション &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)または[&#x200B; パネル &#x200B;](/help/analyze/analysis-workspace/c-panels/panels.md#context-menu)をコピーできます。 例えば、同じプロジェクト内のパネル間の移動、または別のプロジェクト間の移動などです。 |



<!--

# Download 

There are several ways to export data from Analysis Workspace. The method you choose depends on what set of data you want to analyze and who needs to access it.

Exported data can be in the form of copied data, CSV, or PDF. A PDF is typically preferred if you want visualizations included in the file. CSV and copied data is preferred if you simply want plain-text data.

## Download a project as CSV or PDF

Consider the following when downloading projects:

* When downloading projects as a CSV or PDF, the project can be saved or unsaved when you request a project download. However, only saved projects can be [scheduled](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). 

* When downloading projects as a PDF:
  * Downloads can take several minutes to export because the project is re-run on Adobe servers before rendering in PDF format. We recommend not leaving the project until the PDF downloads in your browser. However, you can continue to make changes to the project while you wait. If a PDF takes longer than 5 minutes to render, you will be prompted to email it instead.
  * Downloads are rendered as a single page with no pagination applied.
  * PDF renderings contain what is on the page in Workspace. If a project has custom-sized visualizations and panels, you need to change them to be auto-sized (button in top-right corner) so that there will be no truncated content.
  * Any [hyperlinks](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) that exist within freeform tables are not functional in the downloaded PDF. 

To download a project as a CSV or PDF file:

1. Do either of the following, depending on what format you want to download the project in:

   * **PDF:** Select **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.

     Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.

   * **CSV:** Select **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**. 

     Choose this option if you want plain-text data.

   ![](assets/download-project.png)

1. (Conditional) If you chose to download a PDF, a message is shown after the project is ready to be downloaded. Click [!UICONTROL **Download**].
1. Click the **[!UICONTROL Download this file]** icon and save the file to a folder of your choice.

## Copy data to clipboard (hotkey: cmd + c)

The right-click option **[!UICONTROL Copy to clipboard]** lets you quickly copy data from Workspace and paste it in a third-party tool. 

* If you want the displayed table copied, right-click the table header and choose **Copy data to clipboard**. 
* If you want a subset of data copied, make a selection in the table and then right-click > **Copy selection to clipboard**.

>[!TIP]
>
>You can use the hotkey `Ctrl+C` to copy your selection to the clipboard, then use `Ctrl+V` to paste it into a third-party tool.

![](assets/copy-selection.png)

## Download data as CSV

The right-click option **[!UICONTROL Download data as CSV]** allows you to download a table of data or the data source of any visualization as a CSV.

* From the header of any table or visualization, right-click and choose **[!UICONTROL Download data as CSV]**. This downloads the displayed data in the table or the underlying data source for a visualization as a CSV. 

  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.

* Within a table, right-click and choose **[!UICONTROL Download selection as CSV]**. Only the selection is downloaded with this option, as opposed to the full, displayed table.

![](assets/download-data-viz.png)

## Download items as CSV

If you want to analyze more than the visible 400 rows of data in a table, right-click the table header or any row and select **Download items as CSV (_Dimension name_)**. This option exports up to 50,000 dimension items (based on the table sort) for the selected dimension, with filters and segments applied. If you chose this option from the top of the table, the first dimension in the table will be exported. While no limits are enforced in the freeform table, it is recommended that the Download items option be used in tables with less than 20 columns to ensure optimal performance.

>[!TIP]
>
> If your dimension exceeds 50,000 items, download the file with different sort metrics applied or apply a filter. For example, sort descending by Visits in one download and then ascending by Visits in a second download. This tip can help you retrieve longer-tail items.

You can multi-task within the project and even navigate to a new Workspace project in the same tab while the download is in progress. The download pauses if you open a new browser tab. The download is canceled if you leave Workspace completely or close the browser tab.

![](assets/download-items.png)

### Downloaded items file 

Features of the table will be applied to the downloaded file as follows:

* All panel segments are applied as filters.
* Breakdowns **above** the selected dimension in the table are applied as filters above each column. 
* Breakdowns **below** the selected dimension in the table are removed.

In the example above, Page items are downloaded with the panel segment (New Visitors Customers) and components above (Marketing Channel = Email) applied as filters, and the components below (Mobile Device Type) removed from the downloaded CSV.

![](assets/downloaded-file.png)

### Download notifications

As the file downloads, you will see an informational notification with the progress. At any time, you can cancel the download by clicking **[!UICONTROL Cancel download]**. Closing the toast **will not** cancel the download. 

Once the file completes, you will see a completion notification and the file will download to your browser.

If you request more than one download at a time, you will receive a notification that each additional download will be queued until the prior download completes.

![](assets/toast.png)

## FAQ

| Question | Answer |
| --- | --- |
| Why is my downloaded PDF one page? | Workspace does not paginate downloaded PDFs at this time. |
| Can I export more than 50,000 items with the "Download items as CSV" option? | While each download can contain up to 50,000 dimension items, you can change the sort of your table to retrieve longer tail items, or apply a filter to download more specific items. |
| What does **[!UICONTROL Copy visualization]** do? | Unlike [!UICONTROL **Copy data to clipboard**] or [!UICONTROL **Copy selection to clipboard**], the **[!UICONTROL Copy visualization]** right-click option is not an export option. It allows you to copy a visualization or panel from one place in Workspace to another. For example, from one panel to another in the same project, or from one project to another project. [Intra-linking video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |

-->