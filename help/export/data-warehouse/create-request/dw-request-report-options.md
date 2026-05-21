---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: Data Warehouse リクエストのレポートオプションの設定
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
TQID: https://experienceleague.adobe.com/WngJlzAVsWsC9dzQ2Dg-78FqUjXxkU9SUnJVzhFECXs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 454
ht-degree: 17%

---

# Data Warehouse リクエストのレポートオプションの設定

Data Warehouse を作成する際には、様々な設定オプションを使用できます。 次の情報では、リクエストのレポートオプションを設定する方法について説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

Data Warehouse リクエストのレポートオプションを設定するには：

1. まだ作成していない場合は、**[!UICONTROL ツール]**／**[!UICONTROL Data Warehouse]**／[!UICONTROL **追加**]&#x200B;を選択して、Adobe Analytics でリクエストの作成を開始します。

   詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

1. 新しいData Warehouse リクエストページで、「[!UICONTROL **レポートのオプション**]」タブを選択します。

   ![&#x200B; レポート宛先タブ &#x200B;](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **ファイル名**] | レポートを特定します。 <p>ファイル名に次の特殊文字のいずれかが使用されている場合、リクエストを保存できません：<code>! &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ &#39; { } \| ～</code> </p><p>%文字は、次のように「R」、「rsid」、「id」が続く場合にのみ使用できます：<code>%R</code>, <code>%rsid</code>、および<code>%id</code>.</p> |
   | [!UICONTROL **レポート日付範囲をファイル名**]&#x200B;に追加 | 日付範囲をレポートファイル名に追加します。 <p>例えば、2024年5月1日から2024年5月7日までのデータをリクエストする場合、ファイル名には20240501 - 20240507の日付範囲が含まれます。</p> |
   | [!UICONTROL **CSV**] | スプレッドシートでデータを表示するために、CSV ファイル形式でレポートを配信します。 |
   | [!UICONTROL **Tableau （TDE）**] | Tableau データ抽出（TDE）ファイル形式でレポートを提供します。この形式を使用すると、Tableau内の追加データのデータとレイヤーを視覚化できます。 |
   | [!UICONTROL **レポートを圧縮ファイル （ZIP）として送信**] | 圧縮（ZIP）ファイル形式でレポートを配信します。 [&#x200B; レポートの宛先](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)としてメールを使用する場合は、このオプションを有効にすることをお勧めします。 |
   | [!UICONTROL **すべての行を返す**] | 有効にすると、すべての行がレポートに含まれます。 含める行数を指定するには、このオプションを無効にします。 |
   | [!UICONTROL **レポートのコメントの開始**] | レポートに含めるコメントを追加します。 コメントはレポートの先頭に表示されます。 |
   | [!UICONTROL **指標で並べ替え**] | Data Warehouseで、指標の値が降順で並べ替えられたランク付きの内訳レポートを提供します。 指標別に並べ替えることで、Data Warehouse レポートの解釈が容易になり、これらのレポートを他のAnalyticsの分類レポートビューと比較しやすくなります。<p>詳しくは、[指標による並べ替え](/help/export/data-warehouse/sorting-by-metric.md)を参照してください。</p> |
   | [!UICONTROL **マニフェストファイルを送信**] | レポートに含まれるファイルに関するメタデータが含まれます。<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **デジタル署名ファイルを送信**] | レポートの受信者は、ファイルがAdobeから送信されたもので、変更されていないことを確認できます。 |
   | [!UICONTROL **レポートにデータがない場合は、空のファイルを送信します**] | レポートにデータが含まれていない場合でも、レポートを送信します。 |

   {style="table-layout:auto"}

1. 引き続き、[!UICONTROL **スケジュール設定オプション**] タブでData Warehouse リクエストの設定を行います。 詳しくは、[Data Warehouse リクエストのスケジュール設定オプションの設定](/help/export/data-warehouse/create-request/dw-request-scheduling.md)を参照してください。
