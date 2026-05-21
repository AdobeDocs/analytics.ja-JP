---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: Data Warehouse リクエストのレポートの宛先を設定する
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
TQID: https://experienceleague.adobe.com/3M2cNjsk8KP356ES66AaXpSXJ6IvxWDtFcx7gYvlKeQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 292
ht-degree: 33%

---

# Data Warehouse リクエストのスケジューリングオプションの設定

Data Warehouse を作成する際には、様々な設定オプションを使用できます。 次の情報では、リクエストのスケジューリングオプションを設定する方法について説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

Data Warehouse リクエストのスケジューリングオプションを設定するには：

1. まだ作成していない場合は、**[!UICONTROL ツール]**／**[!UICONTROL Data Warehouse]**／[!UICONTROL **追加**]&#x200B;を選択して、Adobe Analytics でリクエストの作成を開始します。

   詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

1. 新しいData Warehouse リクエストページで、「[!UICONTROL **スケジュール設定オプション**]」タブを選択します。

   ![ レポート宛先タブ ](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **今すぐレポートを送信**] | レポートを1回限りのレポートとして送信します。 このオプションを選択すると、すべてのスケジュール設定オプションが非表示になります。 |
   | [!UICONTROL **後のスケジュール**] | レポート配信のスケジュール設定オプションを提供します。 すべてのオプションについて以下に説明します。 |
   | [!UICONTROL **レポート頻度**] | レポートの配信頻度。 <p>次のオプションがあります。</p><ul><li>1 時間ごと</li><p>[!UICONTROL **時間単位**]&#x200B;は、[!UICONTROL **一般設定**] タブの&#x200B;[!UICONTROL **日付範囲**] オプションが&#x200B;[!UICONTROL **過去1時間**]&#x200B;に設定されている場合にのみ使用できます。</p><li>毎日</li><li>毎週</li><li>毎月</li><li>毎年</li></ul><p>選択した頻度に応じて、追加のオプションが表示されます。</p> |
   | [!UICONTROL **開始日：**] | 新しいスケジュールを開始する日付。 |
   | [!UICONTROL **日の時刻**] | レポートを送信する時刻。 |
   | [!UICONTROL **配信オプションの終了**] | スケジュールされた配信を終了するタイミングを選択します。 終了しない、特定の回数で終了する、特定の日付で終了する、のいずれかを選択できます。 |

   {style="table-layout:auto"}

1. 引き続き、[!UICONTROL **通知メール**] タブでData Warehouse リクエストの設定を行います。 詳しくは、[Data Warehouse リクエストの通知メールの設定](/help/export/data-warehouse/create-request/dw-request-email.md)を参照してください。
