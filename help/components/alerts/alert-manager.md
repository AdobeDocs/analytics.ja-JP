---
description: アラートの管理方法を説明します。
title: アラートの管理
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
TQID: https://experienceleague.adobe.com/ch83E4k1pJ3CpnAn54buMAqFLAHCVMBC8HZkHvGRlmU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 599
ht-degree: 21%

---

# アラートの管理


中央の[!UICONTROL  アラート ]管理インターフェイスからアラートをフィルタリング、タグ付け、削除、名前の変更、コピー、有効、無効、更新、エクスポートできます。 アラートを管理するには：

* メインインターフェイスで「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL アラート]**」を選択します。

アラートマネージャーは、[ セグメントマネージャー](/help/components/segmentation/segmentation-workflow/seg-manage.md)と[計算指標マネージャー](/help/components/calculated-metrics/workflow/cm-manager.md)のような構造になっています。


## アラートマネージャー

アラートマネージャーには、次のインターフェイス要素があります。

![フィルターインターフェイス](assets/alerts-manager.png)

### アラートリスト

アラート リスト ➊には、所有しているすべてのアラート、すべてのプロジェクトに対してスコープ付けされたアラート、および共有されたアラートが表示されます。 リストには、次の列があります。

| 列 | 説明 |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | ![Star](/help/assets/icons/Star.svg)を優先するか、![StarOutline](/help/assets/icons/StarOutline.svg)をアラートから除外するかを選択します。 |
| **[!UICONTROL タイトルと説明]** | アラートを編集するには、タイトルリンクを選択します。これにより、[ アラートビルダー](alert-builder.md#alert-builder)が開きます。 |
| **[!UICONTROL タイプ]** | アラートの種類：Adobe Analytics データアラートまたはServer呼び出し使用状況アラート。 |
| **[!UICONTROL 有効]** | アラートは有効または無効です。 |
| **[!UICONTROL レポートスイート]** | このアラートが適用されるレポートスイート。 |
| **[!UICONTROL 所有者]** | アラートの所有者。 管理者以外のユーザーには、自分が所有するアラートまたは自分と共有されているアラートのみが表示されます。 |
| **[!UICONTROL タグ]** | このアラートのタグ。 |
| **[!UICONTROL 有効期限]** | アラートの有効期限が切れるように設定されている日時。 |
| **[!UICONTROL 変更日時]** | アラートが最後に変更された日時。 |

<!-- 

When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul>

-->

![ColumnSetting](/help/assets/icons/ColumnSetting.svg) を使用して、表示する列を指定します。

### アクションバー

アクション バー➋を使用して、アラートに対してアクションを実行できます。 アクションバーには、次のアクションが含まれます。

| アイコン | アクション | 説明 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 追加]** | [ アラートビルダー](alert-builder.md#alert-builder)を使用して、別のアラートを追加します。 |
| ![検索](/help/assets/icons/Search.svg) | [!UICONTROL *タイトルで検索*] | リストでアラートが選択されていない場合は、この検索フィールドを使用してアラートを検索します。 |
| ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL タグ]** | 選択したアラートにタグを付けます。 **[!UICONTROL タグのアラート]** ダイアログで、選択したアラートのタグを選択または選択解除します。 選択したアラートのタグを保存するには、**[!UICONTROL 保存]**&#x200B;を選択します。 |
| ![削除](/help/assets/icons/Delete.svg) | **[!UICONTROL 削除]** | 選択したアラートを削除します。 確認メッセージが表示されます。 |
| ![編集](/help/assets/icons/Edit.svg) | **[!UICONTROL 名前変更]** | 選択した1つのアラートの名前を変更します。 選択すると、アラートの名前をインラインで変更できます。 |
| ![コピー](/help/assets/icons/Copy.svg) | **[!UICONTROL コピー]** | 選択したアラートをコピーします。 新しいアラートが、同じ名前とサフィックス `(Copy)`で作成されます。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 有効]**&#x200B;または&#x200B;**[!UICONTROL 無効]** | 選択したアラートを有効または無効にします。 |
| ![更新](/help/assets/icons/Refresh.svg) | **[!UICONTROL 更新]** | アラートの有効期限日を更新します。 有効期限は、元の有効期限に関係なく、このオプションを選択した日から1年間延長されます。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL CSV に書き出し]** | アラートを`Alerts List.csv` ファイルにエクスポートします。 |


### アクティブなフィルターバー

フィルターバー➌には、フィルターパネルからアラートのリスト（存在する場合）に適用されたアクティブなフィルターが表示されます。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を使用すると、フィルターをすばやく削除できます。 複数のフィルターを指定した場合は、「**[!UICONTROL すべて削除]**」を使用すると、すべてのフィルターを削除できます。


### フィルターパネル

![ フィルター](/help/assets/icons/Filter.svg) **[!UICONTROL フィルター]**&#x200B;左側のパネル ➍を使用して、アラートのリストをフィルターできます。 フィルターパネルには、フィルターのタイプと、特定のフィルターを適用するアラートの数が表示されます。


1. 「![フィルター](/help/assets/icons/Filter.svg)」を選択して、フィルターパネルを開きます。 アラートリストの空き容量が必要な場合は、![ フィルター](/help/assets/icons/Filter.svg)をもう一度選択してパネルを閉じることができます。
1. 使用可能なフィルターセクションからフィルターを選択します。


#### タグフィルターセクション

{{tagfiltersection}}


#### レポートスイートフィルターセクション

{{reportsuitefiltersection}}


#### 所有者フィルターセクション

{{ownerfiltersection}}


#### 有効ステータスのフィルターセクション

{{enabledstatusfiltersection}}


#### タイプのフィルターセクション

{{typefiltersection}}


#### その他のフィルターのフィルターセクション

{{otherfiltersfiltersection}}



## アラートを編集

アラートは

* [[!UICONTROL  アラート ] リスト ](#alerts-list)で、アラートのタイトルを選択します。

[ アラートビルダー](alert-builder.md#alert-builder)を使用して、アラートを編集します。

## アラートのトラブルシューティング

アラートに関する問題のトラブルシューティングを行う場合は、JID （Job Instance ID）番号をAdobe サポートに提供します。 JID番号は、受信したアラートメール通知の下部にあります。

![アラートメール](assets/alerts-email.PNG)


<!--

# Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

The Alerts manager is structured very much like the [Segment Manager](/help/components/segmentation/segmentation-workflow/seg-manage.md) and the [Calculated Metric Manager](/help/components/calculated-metrics/calcmetric-workflow/cm-manager.md).

 ![](assets/alert-manager.png)

## Create alerts

To create alerts from the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select [!UICONTROL **Add**] (or [!UICONTROL **Create new alert**] if you don't have any existing alerts).

1. Select the alert type that corresponds to the alert that you want to create:

   * [!UICONTROL **Analytics data alert**]: An alert to notify you when abnormal events occur in your data. 

     If you select this option, continue with [Create alerts](/help/components/alerts/alert-builder.md) for more details about creating alerts.

   * [!UICONTROL **Server call usage alert**]: An alert to notify you of the risk or occurrence of an overage in your server call consumption and commitment data. 

     If you select this option, continue with [Server call usage alerts](/help/admin/tools/server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >You must be an Analytics administrator or a user with the Server call usage permission in order to have access to server call usage. 

## Manage existing alerts

You can perform various actions on existing alerts, such as tagging, renaming, deleting, and so forth.

To manage existing alerts in the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select one or more alerts that you want to manage.

   ![](assets/alert-manager-tasks.png)

1. In the action bar, select any of the following options:

   | Action | Function |
   |---------|----------|
   | [!UICONTROL **Tag**] | Apply a tag to an alert. This helps you to organize alerts for ease of use. |
   | [!UICONTROL **Delete**] | Deletes the alert. |
   | [!UICONTROL **Rename**] | Renames the alert. |
   | [!UICONTROL **Approve**] | Mark the alert as Approved. |
   | [!UICONTROL **Copy**] | Creates a copy (duplicate) of the alert. |
   | [!UICONTROL **Disable**] | Disables an alert that is currently enabled. |
   | [!UICONTROL **Enable**] | Enables an alert that is currently disabled. |
   | [!UICONTROL **Renew**] | Renews the alert expiration date. This extends the  expiration date to be 1 year from the day you selected this option, regardless of the original expiration date. |
   | [!UICONTROL **Export to CSV**] | Exports the alert to a .CSV file. |

## Edit an alert

To edit an existing alert:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select the alert name in the [!UICONTROL **Title and description**] column.

1. Edit the alert as desired. 

   Following are some of the things you can do when editing an alert:

   * Add alerts to other report suites
   * Add or modify the description
   * Modify the time granularity
   * Modify the recipients 
   * Modify the expiration date
   * Modify the metrics and filters

1. Select [!UICONTROL **Save**].

## Configure columns 

You can configure the information displayed for each alert in the Alerts manager by configuring the columns that are displayed.

To configure the visible columns in the Alerts manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Alerts]**. 

1. In the Alert manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Alerts manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Title and description | These values are provided in the Alert builder. To edit the title and description, select the title link to open the Alert builder.  |
   | Favorites  | Displays star icons next to each alert, allowing you to mark alerts as favorites. |
   | Type | Shows whether the alert is an Analytics data alert or a Server call usage alert. |
   | Enabled | Shows whether the alert is currently enabled or disabled. |
   | Report suite | Indicates in which report suite the alert was last saved.  |
   | Owner | Indicates who owns the alert. As a non-admin, you can see only alerts you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the alert, either by you or by people who shared the alert with you.  |
   | Expiration date | Shows the date and time when the alert is set to expire. |
   | Date modified | Indicates the date when the alert was last modified.  |

   {style="table-layout:auto"}
   
   
    When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> 
   
-->

