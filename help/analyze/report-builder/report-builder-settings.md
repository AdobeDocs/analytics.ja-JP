---
title: Report Builderの設定
description: Report Builderの設定を行う方法について説明します。
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
TQID: https://experienceleague.adobe.com/aHEmYs37KDXtaoAbFiI6WBCvmdhN0RrMWDl-CeEotKw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 257
ht-degree: 29%

---

# Report Builder の設定


「**設定**」ペインを使用して、UI で表示される言語やオフラインモードで動作するかどうかなど、アプリケーションレベルの設定を行います。 設定は直ちに適用され、変更されるまで、今後のすべてのセッションに対して設定されます。

Report Builder 設定を変更するには

1. **設定** アイコンを選択します。

1. オフライン モードを無効にする[有効にする](#off-line-mode)、[言語を選択](#language)または[ トラブルシューティングを有効にする](#troubleshooting)に変更を加えます。

1. 「**[!UICONTROL 適用]**」を選択します。

   ![Report Builderの日付範囲ペインに「キャンセルして適用」ボタンが表示されている。](./assets/report-builder-settings.png){zoomable="yes"}

## オフラインモード

オフラインモードでデータブロックを作成および編集する場合、データは取得されません。 代わりに、シミュレーションデータを使用して、リクエストの実行を待たずに迅速に作業できるようにします。 オンラインに戻ったら、![更新](/help/assets/icons/Refresh.svg) **[!UICONTROL データブロックを更新]**&#x200B;または![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL すべてのデータブロックを更新]**&#x200B;し、実際のデータでデータブロックを更新します。

オフラインモードを有効にするには

1. 「![設定](/help/assets/icons/Setting.svg)」を選択します。

1. **[!UICONTROL オフライン モードを有効にする]**&#x200B;をオンに切り替えます。

1. **[!UICONTROL 指標データ]**&#x200B;のフィールドに正の整数を入力します。

1. 「**[!UICONTROL 適用]**」を選択します。


## 言語

Report Builder インターフェイスの言語を選択できます。 サポートされているすべてのCustomer Journey Analytics言語を使用できます。

Report Builder インターフェイスで使用する言語を選択するには：

1. **[!UICONTROL 言語]** ドロップダウンメニューから言語を選択します。

1. **適用を選択します。**

## トラブルシューティング

**[!UICONTROL トラブルシューティング ログ]**&#x200B;設定では、すべてのクライアント/サーバーデータがローカル ファイルに記録されます。 このオプションを使用して、サポートチケットの解決に役立てます。

トラブルシューティングログを有効にするには、**[!UICONTROL Report Builder リクエストをローカルファイル]**&#x200B;に記録するを確認してください。

<!--
Use the **Settings** pane to configure application-level settings such as the language displayed by the UI or whether or not to work in off-line mode. The settings are applied immediately and they are set for all future sessions until they're changed.

To change Report Builder settings

1. Click the **Settings** icon.

1. Make changes to Enable off-line mode, select a Language, or enable Troubleshooting log settings.

1. Click **Apply**.

    ![Report Builder settings.](./assets/image38.png)

## Off-line mode

When creating and editing a data block in off-line mode, data is not retrieved. Instead, simulation data is used so that you can quickly create and edit a data block without waiting for the request to run. When you are back online, the *Refresh data block* command or *Refresh all data blocks* command refreshes the data blocks that you created with actual data.

To enable off-line mode

1. Click the **[!UICONTROL Settings]** icon.

1. Select **[!UICONTROL Enable off-line mod]e**.

1. Enter a positive integer in the **[!UICONTROL Display metric data as]** field.

1. Click **[!UICONTROL Apply]**.

## Language

You can choose the language for the Report Builder UI. All supported Adobe Analytics languages are available.

To select the language used in the Report Builder UI

 1. Click Settings.

 1. Select a language from the **[!UICONTROL Language]** drop down menu.

     ![Report Builder date range pane showing the Language list with English selected.](./assets/image39.png)

 1. Click **[!UICONTROL Apply].**

## Troubleshooting

Use the Troubleshooting setting to log all client/server data to a local file. Use this option to help resolve support tickets.

To enable the Troubleshooting option, select **[!UICONTROL Log report builder data block to web console]**.
-->