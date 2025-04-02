---
description: アラートを管理。
title: アラートマネージャーの概要
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 86580b3c149c0feb1d70d9ba197cf0810e472586
workflow-type: ht
source-wordcount: '638'
ht-degree: 100%

---

# アラートマネージャー

アラートマネージャーでは、既存のアラートを管理できます。タグ付け、名前変更、削除など、アラートに対して様々な管理タスクを実行できます。

アラートマネージャーは、[セグメントマネージャー](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=ja)や[計算指標マネージャー](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=ja)と非常によく似た構造になっています。

![](assets/alert-manager.png)

## アラートの作成

アラートマネージャーからアラートを作成するには：

1. **[!UICONTROL コンポーネント]**／**[!UICONTROL アラート]**&#x200B;を選択して、Adobe Analytics のアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. 「[!UICONTROL **追加**]」を選択します（既存のアラートがない場合は、「[!UICONTROL **新しいアラートを作成**]」を選択します）。

1. 作成するアラートに対応するアラートタイプを選択します。

   * [!UICONTROL **Analytics データアラート**]：データに異常なイベントが発生した際に通知するアラート。

     このオプションを選択した場合は、[アラートの作成](/help/components/c-alerts/alert-builder.md)に進んで、アラートの作成の詳細を確認してください。

   * [!UICONTROL **サーバーコールの使用状況アラート**]：サーバーコールの消費量とコミットメントデータの超過のリスクや発生件数を通知するアラート。

     このオプションを選択した場合は、[サーバーコールの使用状況アラート](/help/admin/admin/c-server-call-usage/scu-alerts.md)に進みます。

     >[!NOTE]
     >
     >サーバーコールの使用状況にアクセスするには、Analytics 管理者またはサーバーコールの使用状況のアクセス権を持つユーザーである必要があります。

## 既存のアラートの管理

タグ付け、名前変更、削除など、既存のアラートに対して様々なアクションを実行できます。

アラートマネージャーで既存のアラートを管理するには：

1. **[!UICONTROL コンポーネント]**／**[!UICONTROL アラート]**&#x200B;を選択して、Adobe Analytics のアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. 管理するアラートを 1 つ以上選択します。

   ![](assets/alert-manager-tasks.png)

1. アクションバーで、次のいずれかのオプションを選択します。

   | アクション | 関数 |
   |---------|----------|
   | [!UICONTROL **タグ**] | アラートにタグを適用します。これにより、アラートを使いやすく整理できます。 |
   | [!UICONTROL **削除**] | アラートを削除します。 |
   | [!UICONTROL **名前変更**] | アラートを名前変更します。 |
   | [!UICONTROL **承認**] | アラートを承認済みとしてマークします。 |
   | [!UICONTROL **コピー**] | アラートのコピー（複製）を作成します。 |
   | [!UICONTROL **無効にする**] | 現在有効になっているアラートを無効にします。 |
   | [!UICONTROL **有効にする**] | 現在無効になっているアラートを有効にします。 |
   | [!UICONTROL **更新**] | アラートの有効期限日を更新します。これにより、元の有効期限日に関係なく、このオプションを選択した日から有効期限日が 1 年間延長されます。 |
   | [!UICONTROL **CSV に書き出し**] | アラートを .CSV ファイルに書き出します。 |

## アラートの編集

既存のアラートを編集するには：

1. **[!UICONTROL コンポーネント]**／**[!UICONTROL アラート]**&#x200B;を選択して、Adobe Analytics のアラートマネージャーにアクセスします。

   ![](assets/alert-manager.png)

1. [!UICONTROL **タイトルと説明**]&#x200B;列でアラート名を選択します。

1. 必要に応じてアラートを編集します。

   アラートの編集時に実行できる操作の一部を以下に示します。

   * 他のレポートスイートにアラートを追加
   * 説明を追加または変更
   * 時間の精度を変更
   * 受信者を変更
   * 有効期限を変更
   * 指標とフィルターを変更

1. 「[!UICONTROL **保存**]」を選択します。

## 列の設定

表示される列を設定して、アラートマネージャーで各アラートに表示される情報を設定できます。

アラートマネージャーで表示される列を設定するには：

1. Adobe Analytics で、「**[!UICONTROL コンポーネント]**」タブを選択し、「**[!UICONTROL アラート]**」を選択します。

1. アラートマネージャーで、**列をカスタマイズ** アイコン ![列をカスタマイズアイコン](assets/customize-columns-icon.png) を選択し、アラートマネージャーに表示する列を選択します。

   次の列を表示できます。

   | 列タイトル | 説明 |
   |---|---|
   | タイトルと説明 | これらの値は、アラートビルダーで指定されます。タイトルと説明を編集するには、タイトルリンクを選択してアラートビルダーを開きます。 |
   | お気に入り | 各アラートの横に星アイコンが表示され、アラートをお気に入りとしてマークできます。<!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | タイプ | アラートが Analytics データアラートであるか、サーバーコールの使用状況アラートであるかが表示されます。 |
   | 有効 | アラートが現在有効であるか、無効であるかが表示されます。 |
   | レポートスイート | アラートを最後に保存したレポートスイートが示されます。 |
   | 所有者 | アラートの所有者が示されます。管理者以外のユーザーには、自分が所有しているアラート、または自分と共有されていたアラートのみが表示されます。 |
   | タグ | 自分または自分とアラートを共有している人物によって指標に適用されたタグが表示されます。 |
   | 有効期限 | アラートの有効期限に設定した日時が表示されます。 |
   | 変更日 | アラートを最後に変更した日付が示されます。 |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


