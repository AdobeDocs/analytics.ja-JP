---
description: アラートを作成、編集または削除します。
title: アラートマネージャー（Analysis Workspace）
feature: Alerts
role: User, Admin
exl-id: c33a9a30-f53f-443c-96b7-6a87d03573c7
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---


# アラートの管理

アラートマネージャーでは、既存のアラートを管理できます。 タグ付け、名前の変更、削除など、アラートに対して様々な管理タスクを実行できます。

アラートマネージャーは、[ セグメントマネージャー ](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=ja) および [ 計算指標マネージャー ](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=ja) と非常に似た構造になっています。

## アラートの作成

アラート・マネージャからアラートを作成するには、次の手順に従います。

1. **[!UICONTROL コンポーネント]**/**[!UICONTROL アラート]** を選択して、Adobe Analyticsのアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. [!UICONTROL **追加**] （または既存のアラートがない場合は [!UICONTROL **新しいアラートの作成**]）を選択します。

1. 作成するアラートに対応するアラートタイプを選択します。

   * [!UICONTROL **Analytics データアラート**]：データに異常なイベントが発生した場合に通知するアラート。

     このオプションを選択した場合、アラートの作成の詳細については、[ アラートの作成 ](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md) に進みます。

   * [!UICONTROL **サーバーコールの使用状況アラート**]：サーバーコールの使用状況とコミットメントデータに超過のリスクや発生があることを通知するアラート。

     このオプションを選択した場合は、[ サーバーコールの使用状況アラート ](/help/admin/admin/c-server-call-usage/scu-alerts.md) に進みます。

     >[!NOTE]
     >
     >サーバーコールの使用状況にアクセスするには、Analytics 管理者またはサーバーコールの使用状況アクセス権を持つユーザーである必要があります。




## 既存アラートの管理

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
