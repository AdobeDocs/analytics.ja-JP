---
description: Data Warehouse リクエストを作成する方法について手順を説明します。
title: レポートリクエストのレポートオプションのData Warehouseを設定する
feature: Data Warehouse
source-git-commit: 42c95198a4d4389308c78c312b5bb37572350cc1
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 16%

---

# レポートリクエストのレポートオプションのData Warehouseを設定する

{{release-limited-testing}}

設定リクエストを作成する際には、様々な設定オプションをData Warehouseできます。 次の情報では、リクエストのレポートオプションを設定する方法を説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

レポート・リクエストのレポート・オプションをData Warehouseするには、次の手順に従います。

1. Adobe Analyticsでのリクエストの作成を開始するには、「 **[!UICONTROL ツール]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **追加**].

   詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 新しいData Warehouseリクエストページで、 [!UICONTROL **レポートのオプション**] タブをクリックします。

   ![「レポートの宛先」タブ](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | ファイル名 | レポートを識別します。 |
   | ファイル名にレポートの日付範囲を追加 | レポートファイル名に日付範囲を追加します。 <p>例えば、2024 年 5 月 1 日から 2024 年 5 月 7 日までのデータを要求した場合、ファイル名には20240501 ～ 20240507の日付範囲が含まれます。</p> |
   | CSV | レポートを CSV ファイル形式で配信し、データをスプレッドシートで表示します。 |
   | Tableau(TDE) | レポートを Tableau Data Extract(TDE) ファイル形式で配信します。この形式は、Tableau 内の追加データのデータやレイヤーを視覚化するために使用できます。 |
   | レポートを圧縮ファイル (ZIP) として送信 | レポートを圧縮 (ZIP) ファイル形式で配信します。 電子メールを [レポートの宛先](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | 表の行数 | レポートに含めることができる行の数。 すべての行を含める場合は 0 を使用します（これがデフォルトの選択です）。 <!-- when would you want to limit the rows? To improve performance? Do we have recommendations? --> |
   | コメント | レポートに含めるコメントを追加します。 レポートの先頭にコメントが表示されます。 |
   | 指標で並べ替え | 指標値を降順で並べ替えた、Data Warehouse のランク分類レポートを提供します。指標で並べ替えると、Data Warehouse レポートが解釈しやすくなり、他の Analytics 分類レポート表示と比較しやすくなります。<p>詳しくは、 [指標で並べ替え](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | マニフェストファイルを送信 | レポートに含まれるファイルに関するメタデータが含まれます。<!-- What kind of metadata is included in the manifest file? --> |
   | 電子署名ファイルの送信 | レポートの受信者は、ファイルがAdobeから送信されたもので、変更されていないことを確認できます。 |
   | レポートにデータがない場合は空のファイルを送信 | レポートにデータが含まれていない場合でもレポートを送信します。 |

   {style="table-layout:auto"}

1. 引き続き、 [!UICONTROL **スケジュールオプション**] タブをクリックします。 詳しくは、 [スケジュールリクエストのData Warehouseオプションの設定](/help/export/data-warehouse/create-request/dw-request-scheduling.md).