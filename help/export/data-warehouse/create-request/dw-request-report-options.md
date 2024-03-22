---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: レポートリクエストのレポートオプションのData Warehouseを設定する
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 19%

---

# レポートリクエストのレポートオプションのData Warehouseを設定する

Data Warehouse を作成する際には、様々な設定オプションを使用できます。次の情報では、リクエストのレポートオプションを設定する方法を説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

レポート・リクエストのレポート・オプションをData Warehouseするには、次の手順に従います。

1. まだリクエストを作成していない場合は、「 Adobe Analytics 」を選択して、リクエストの作成を開始します。 **[!UICONTROL ツール]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **追加**].

   詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

1. 新しいData Warehouseリクエストページで、 [!UICONTROL **レポートのオプション**] タブをクリックします。

   ![「レポートの宛先」タブ](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **ファイル名**] | レポートを識別します。 <p>ファイル名に次の特殊文字が使用されている場合、リクエストは保存できません。 <code>! &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ?@ [ ] \ ^ &#39; { } \| ～</code> </p><p>%文字は、次のように、「R」、「rsid」、「id」の後に付く場合にのみ使用できます。 <code>%R</code>, <code>%rsid</code>、および <code>%id</code>。</p> |
   | [!UICONTROL **ファイル名にレポートの日付範囲を追加**] | レポートファイル名に日付範囲を追加します。 <p>例えば、2024 年 5 月 1 日から 2024 年 5 月 7 日までのデータを要求した場合、ファイル名には20240501 ～ 20240507の日付範囲が含まれます。</p> |
   | [!UICONTROL **CSV**] | レポートを CSV ファイル形式で配信し、データをスプレッドシートで表示します。 |
   | [!UICONTROL **Tableau(TDE)**] | レポートを Tableau Data Extract(TDE) ファイル形式で配信します。この形式は、Tableau 内の追加データのデータやレイヤーを視覚化するために使用できます。 |
   | [!UICONTROL **レポートを圧縮ファイル (ZIP) として送信**] | レポートを圧縮 (ZIP) ファイル形式で配信します。 電子メールを [レポートの宛先](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **すべての行を返す**] | 有効にすると、すべての行がレポートに含まれます。 このオプションを無効にして、含める行数を指定します。 |
   | [!UICONTROL **レポートコメントの開始**] | レポートに含めるコメントを追加します。 レポートの先頭にコメントが表示されます。 |
   | [!UICONTROL **指標で並べ替え**] | 指標値を降順で並べ替えた、Data Warehouseでランク分類レポートを提供します。 指標で並べ替えると、Data Warehouse レポートが解釈しやすくなり、他の Analytics 分類レポート表示と比較しやすくなります。<p>詳しくは、 [指標で並べ替え](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **マニフェストファイルの送信**] | レポートに含まれるファイルに関するメタデータが含まれます。<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **電子署名ファイルの送信**] | レポートの受信者は、ファイルがAdobeから送信されたもので、変更されていないことを確認できます。 |
   | [!UICONTROL **レポートにデータがない場合は空のファイルを送信**] | レポートにデータが含まれていない場合でもレポートを送信します。 |

   {style="table-layout:auto"}

1. 引き続き、 [!UICONTROL **スケジュールオプション**] タブをクリックします。 詳しくは、 [スケジュールリクエストのData Warehouseオプションの設定](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
