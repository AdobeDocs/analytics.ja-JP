---
description: アラートを管理.
title: アラートマネージャーの概要
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 86580b3c149c0feb1d70d9ba197cf0810e472586
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 6%

---

# アラートマネージャー

アラートマネージャーでは、既存のアラートを管理できます。 タグ付け、名前の変更、削除など、アラートに対して様々な管理タスクを実行できます。

アラートマネージャーは、[ セグメントマネージャー ](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=ja) および [ 計算指標マネージャー ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=ja) と非常に似た構造になっています。

![](assets/alert-manager.png)

## アラートの作成

アラート・マネージャからアラートを作成するには、次の手順に従います。

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]** を選択して、Adobe Analyticsのアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. [!UICONTROL **追加**] （または既存のアラートがない場合は [!UICONTROL **新しいアラートの作成**]）を選択します。

1. 作成するアラートに対応するアラートタイプを選択します。

   * [!UICONTROL **Analytics データアラート**]：データに異常なイベントが発生した場合に通知するアラート。

     このオプションを選択した場合、アラートの作成の詳細については、[ アラートの作成 ](/help/components/c-alerts/alert-builder.md) に進みます。

   * [!UICONTROL **サーバーコールの使用状況アラート**]：サーバーコールの使用状況とコミットメントデータに超過のリスクや発生があることを通知するアラート。

     このオプションを選択した場合は、[ サーバーコールの使用状況アラート ](/help/admin/admin/c-server-call-usage/scu-alerts.md) に進みます。

     >[!NOTE]
     >
     >サーバーコールの使用状況にアクセスするには、Analytics 管理者またはサーバーコールの使用状況アクセス権を持つユーザーである必要があります。

## 既存アラートの管理

タグ付け、名前の変更、削除など、既存のアラートに対して様々なアクションを実行できます。

アラート・マネージャで既存のアラートを管理するには：

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]** を選択して、Adobe Analyticsのアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. 管理する 1 つ以上のアラートを選択します。

   ![](assets/alert-manager-tasks.png)

1. アクションバーで、次のいずれかのオプションを選択します。

   | アクション | 関数 |
   |---------|----------|
   | [!UICONTROL **タグ**] | アラートにタグを適用します。 これにより、アラートを整理して使いやすくすることができます。 |
   | [!UICONTROL **削除**] | アラートを削除します。 |
   | [!UICONTROL **名前変更**] | アラートの名前を変更します。 |
   | [!UICONTROL **承認**] | アラートを承認済みとしてマークします。 |
   | [!UICONTROL **コピー**] | アラートのコピー（複製）を作成します。 |
   | [!UICONTROL **無効**] | 現在有効になっているアラートを無効にします。 |
   | [!UICONTROL **有効にする**] | 現在無効になっているアラートを有効にします。 |
   | [!UICONTROL **更新**] | アラートの有効期限を更新します。 これにより、元の有効期限に関係なく、このオプションを選択した日から 1 年間に有効期限が延長されます。 |
   | [!UICONTROL **CSV に書き出し**] | アラートを.CSV ファイルに書き出します。 |

## アラートの編集

既存のアラートを編集するには：

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]** を選択して、Adobe Analyticsのアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. [!UICONTROL **タイトルと説明**] 列のアラート名を選択します。

1. 必要に応じてアラートを編集します。

   アラートを編集する際に実行できる操作の一部を次に示します。

   * 他のレポートスイートへのアラートの追加
   * 説明を追加または変更
   * 時間の精度の変更
   * 受信者の変更
   * 有効期限の変更
   * 指標とフィルターの変更

1. 「[!UICONTROL **保存**]」を選択します。

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


