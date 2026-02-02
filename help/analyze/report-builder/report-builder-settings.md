---
title: Report Builderの設定
description: Report Builderの設定を行う方法について説明します。
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 28%

---

# Report Builder の設定


「**設定**」ペインを使用して、UI で表示される言語やオフラインモードで動作するかどうかなど、アプリケーションレベルの設定を行います。設定は直ちに適用され、変更されるまで、今後のすべてのセッションに対して設定されます。

Report Builder 設定を変更するには

1. **設定** アイコンを選択します。

1. [&#x200B; オフラインモードの無効化の有効化 &#x200B;](#off-line-mode)、[&#x200B; 言語の選択 &#x200B;](#language)、または [&#x200B; トラブルシューティングの有効化 &#x200B;](#troubleshooting) を変更します。

1. 「**[!UICONTROL 適用]**」を選択します。

   ![&#x200B; 「キャンセルして適用」ボタンを表示するReport Builderの日付範囲ペイン。](./assets/report-builder-settings.png){zoomable="yes"}

## オフラインモード

オフラインモードでデータブロックを作成および編集する場合、データは取得されません。 代わりに、リクエストの実行を待たずにすばやく作業できるように、シミュレーションデータを使用します。 オンラインに戻ったら、「![&#x200B; 更新 &#x200B;](/help/assets/icons/Refresh.svg) **[!UICONTROL データブロックを更新]**」または「![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL すべてのデータブロックを更新]**」を選択して、データブロックを実際のデータで更新します。

オフラインモードを有効にするには

1. 「![設定](/help/assets/icons/Setting.svg)」を選択します。

1. **[!UICONTROL オフラインモードを有効にする]** をオンにします。

1. 「**[!UICONTROL 指標データを表示]** フィールドに正の整数を入力します。

1. 「**[!UICONTROL 適用]**」を選択します。


## 言語

Report Builder インターフェイスの言語を選択できます。 サポートされているCustomer Journey Analytics言語はすべて利用できます。

Report Builder インターフェイスで使用する言語を選択するには：

1. **[!UICONTROL 言語]** ドロップダウンメニューから言語を選択します。

1. 「**適用**」を選択します。

## トラブルシューティング

**[!UICONTROL トラブルシューティングログ]** 設定は、すべてのクライアント/サーバーデータをローカルファイルに記録します。 このオプションを使用して、サポートチケットの解決に役立てます。

トラブルシューティングログを有効にするには、「**[!UICONTROL Report Builder リクエストをローカルファイルに記録]**」をオンにします。

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