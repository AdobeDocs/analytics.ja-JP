---
description: アラートを管理.
title: アラートマネージャーの概要
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 49324ef7fd45adeef2c31167d0444a7e67041d6d
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 35%

---

# アラートマネージャー

アラートマネージャーは、[ セグメントマネージャー ](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=ja) および [ 計算指標マネージャー ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=ja) と非常に似た構造になっています。

![](assets/alert-manager.png)

## アラートマネージャーへのアクセス

1. Adobe Analyticsで、[!UICONTROL **コンポーネント**]/[!UICONTROL **アラート**] を選択します。

## アラートマネージャーで使用可能なアクション

アラートマネージャーでは、次の操作を実行できます。

* 「**[!UICONTROL + 追加]**」をクリックすると、アラートビルダーにアクセスします。
* アラートのタグ付け。これにより、アラートを使いやすく整理できます。
* アラートの削除。
* アラートの名前の変更。
* アラートの承認。
* アラートのコピー。
* アラートの有効化／無効化。
* アラートの有効期限の&#x200B;**更新**。1 つまたは複数のアラートが選択されている場合、「**[!UICONTROL 更新]**」をクリックすることで更新できます。これにより、元の有効期限にかかわらず、「**[!UICONTROL 更新]**」がクリックされた日から 1 年先に有効期限が延長されます。
* アラートの .CSV ファイルへの書き出し。
* アラートタイトルのダブルクリックによるアラートの編集。
* アラートの検索。
* 他のレポートスイートへのアラートの追加。
* アラートの所有者の指定／変更。
* 他のフィルターの追加。
* アラートの&#x200B;**有効期限**&#x200B;の定義。

## 列の設定

アラート・マネージャで各アラートに表示される情報を構成するには、表示される列を構成します。

アラート・マネージャで表示可能な列を構成するには、次の手順に従います。

1. Adobe Analyticsで、「**[!UICONTROL コンポーネント]**」タブを選択し、「**[!UICONTROL アラート]**」を選択します。

1. アラートマネージャーで **列のカスタマイズ** アイコン ![ 列のカスタマイズ ](assets/customize-columns-icon.png) を選択し、アラートマネージャーに表示する列を選択します。

   次の列を表示できます。

   | 列タイトル | 説明 |
   |---|---|
   | タイトルと説明 | これらの値は、アラートビルダーで提供されます。 タイトルと説明を編集するには、タイトルリンクを選択してアラートビルダーを開きます。 |
   | お気に入り | 各アラートの横に星アイコンが表示され、アラートをお気に入りとしてマークできます。<!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | タイプ | アラートが Analytics データアラートかサーバーコールの使用状況アラートかを表示します。 |
   | 有効 | アラートが現在有効か無効かを表示します。 |
   | レポートスイート | アラートが最後に保存されたレポートスイートを示します。 |
   | 所有者 | アラートの所有者を示します。 管理者以外のユーザーには、自分が所有しているアラートまたは自分と共有されていたアラートのみが表示されます。 |
   | タグ | 自分または自分とアラートを共有したユーザーによってアラートに適用されたタグを表示します。 |
   | 有効期限 | アラートの有効期限が切れるように設定された日時を表示します。 |
   | 変更日 | アラートが最後に変更された日付を示します。 |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


