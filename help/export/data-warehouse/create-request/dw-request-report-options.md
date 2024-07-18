---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: Data Warehouseリクエストのレポートオプションの設定
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 22%

---

# Data Warehouseリクエストのレポートオプションの設定

Data Warehouse を作成する際には、様々な設定オプションを使用できます。次の情報は、リクエストのレポートオプションを設定する方法を示しています。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

Data Warehouseリクエストのレポートオプションを設定するには：

1. まだ作成していない場合は、**[!UICONTROL ツール]**／**[!UICONTROL Data Warehouse]**／[!UICONTROL **追加**]&#x200B;を選択して、Adobe Analytics でリクエストの作成を開始します。

   詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

1. 新しいData Warehouseリクエスト ページで、「[!UICONTROL **レポートオプション**]」タブを選択します。

   ![ 「レポートの宛先」タブ ](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **ファイル名**] | レポートを識別します。 <p>ファイル名に次の特殊文字が使用されている場合、リクエストを保存できません：<code>! &quot; # $ &amp; &#39; （） * +、/ : ; > = &lt; ?@ [ ] \ ^ &#39; { } \| ～</code> </p><p>% 文字は、次のように「R」、「rsid」または「id」が後に付いている場合にのみ使用できます。<code>%R</code>, <code>%rsid</code>、および <code>%id</code>。</p> |
   | [!UICONTROL **レポートの日付範囲をファイル名に追加**] | レポート ファイル名に日付範囲を追加します。 <p>例えば、2024 年 5 月 1 日から 2024 年 5 月 7 日までのデータをリクエストした場合、ファイル名には 20240501 ～ 20240507 の日付範囲が含まれます。</p> |
   | [!UICONTROL **CSV**] | レポートを CSV ファイル形式で配信して、スプレッドシートでデータを表示します。 |
   | [!UICONTROL **Tableau （TDE）**] | Tableau Data Extract （TDE）ファイル形式でレポートを配信します。Tableau 内で追加データのデータやレイヤーを視覚化するために使用できます。 |
   | [!UICONTROL **レポートを圧縮ファイル（ZIP）として送信**] | レポートを圧縮（ZIP）ファイル形式で配信します。 メールを [ レポートの宛先 ](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) として使用する場合は、このオプションを有効にすることをお勧めします。 |
   | [!UICONTROL **すべての行を返す**] | 有効にすると、すべての行がレポートに含まれます。 含める行数を指定するには、このオプションを無効にします。 |
   | [!UICONTROL **報告書コメントの冒頭**] | レポートに含めるコメントを追加します。 レポートの先頭にコメントが表示されます。 |
   | [!UICONTROL **指標で並べ替え**] | ランク付けされた分類レポートをData Warehouseで、指標の値を降順で並べ替えて提供します。 指標で並べ替えると、Data Warehouse レポートが解釈しやすくなり、他の Analytics 分類レポート表示と比較しやすくなります。<p>詳しくは、[ 指標で並べ替え ](/help/export/data-warehouse/sorting-by-metric.md) を参照してください。</p> |
   | [!UICONTROL **マニフェストファイルの送信**] | レポートに含まれるファイルに関するメタデータを含みます。<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **デジタル署名ファイルの送信**] | ファイルがAdobeから送信されたものであり、変更されていないことをレポートの受信者が確認できるようにします。 |
   | [!UICONTROL **レポートにデータがない場合、空のファイルを送信する**] | レポートにデータが含まれていない場合でも、レポートを送信します。 |

   {style="table-layout:auto"}

1. Data Warehouseリクエストの設定を「[!UICONTROL **スケジュールオプション**]」タブで続けます。 詳しくは、[Data Warehouseリクエストのスケジュールオプションの設定 ](/help/export/data-warehouse/create-request/dw-request-scheduling.md) を参照してください。
