---
description: Data Warehouse リクエストの作成方法について手順を説明します。
title: Data Warehouse リクエストのレポートの宛先を設定する
feature: Data Warehouse
exl-id: e5f8acaa-156f-41fb-a0fc-bc5475f1f3b7
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 33%

---

# Data Warehouseリクエストのスケジュールオプションの設定

Data Warehouse を作成する際には、様々な設定オプションを使用できます。次の情報では、リクエストのスケジュールオプションを設定する方法について説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

Data Warehouseリクエストのスケジュールオプションを設定するには：

1. まだ作成していない場合は、**[!UICONTROL ツール]**／**[!UICONTROL Data Warehouse]**／[!UICONTROL **追加**]&#x200B;を選択して、Adobe Analytics でリクエストの作成を開始します。

   詳しくは、[Data Warehouse リクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md)を参照してください。

1. 新しいData Warehouseリクエスト ページで、「[!UICONTROL **スケジュールオプション**] タブを選択します。

   ![ 「レポートの宛先」タブ ](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **今すぐレポートを送信**] | レポートを 1 回限りのレポートとして送信します。 このオプションを選択すると、すべてのスケジュールオプションが非表示になります。 |
   | [!UICONTROL **後で実行するスケジュール**] | レポート配信のスケジュールを設定するオプションを提供します。 すべてのオプションについて以下で説明します。 |
   | [!UICONTROL **レポート頻度**] | レポートが配信される頻度。 <p>次のオプションがあります。</p><ul><li>1 時間ごと</li><p>[!UICONTROL **毎時**] は、「[!UICONTROL **一般設定**]」タブの [!UICONTROL **日付範囲**] オプションが [!UICONTROL **過去 1 時間**] に設定されている場合にのみ使用できます。</p><li>毎日</li><li>毎週</li><li>毎月</li><li>毎年</li></ul><p>選択した頻度によっては、追加のオプションが表示されます。</p> |
   | [!UICONTROL **開始日**] | 新しいスケジュールを開始する日付。 |
   | [!UICONTROL **時間帯**] | レポートを送信する時刻です。 |
   | [!UICONTROL **配信終了オプション**] | スケジュールされた配信を終了するタイミングを選択します。 終了しない、特定の回数だけ終了する、特定の日付に終了するのいずれかを選択できます。 |

   {style="table-layout:auto"}

1. Data Warehouseリクエストの設定を「[!UICONTROL **通知メール**]」タブで続けます。 詳しくは、[Data Warehouseリクエストの通知メールの設定 ](/help/export/data-warehouse/create-request/dw-request-email.md) を参照してください。
