---
description: Data Warehouse リクエストを作成する方法について手順を説明します。
title: レポートの送信先の設定リクエストのData Warehouse
feature: Data Warehouse
source-git-commit: 393355cd971f264da3e3e1b8736f5752fc4bdc62
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 13%

---

# スケジュールリクエストのData Warehouseオプションの設定

{{release-limited-testing}}

設定リクエストを作成する際には、様々な設定オプションをData Warehouseできます。 次の情報では、リクエストのスケジュールオプションを設定する方法について説明します。

リクエストの作成を開始する方法と、その他の重要な設定オプションへのリンクについて詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

スケジュール・リクエストのオプションをData Warehouseするには：

1. Adobe Analyticsでのリクエストの作成を開始するには、「 **[!UICONTROL ツール]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **追加**].

   詳しくは、 [Data Warehouseリクエストの作成](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 新しいData Warehouseリクエストページで、 [!UICONTROL **スケジュールオプション**] タブをクリックします。

   ![「レポートの宛先」タブ](assets/dw-scheduling-options.png) <!-- update screenshot -->

1. 以下のフィールドに入力します。

   | オプション | 関数 |
   |---------|----------|
   | 今すぐレポートを送信 | レポートを 1 回限りのレポートとして送信します。 このオプションを選択すると、すべてのスケジュールオプションが非表示になります。 |
   | 後で使用するようにスケジュール | レポート配信のスケジュール設定オプションを提供します。 すべてのオプションについては、以下で説明します。 |
   | レポート頻度 | レポートの配信頻度。 <p>次のオプションがあります。</p><ul><li>1 時間ごと</li><p>[!UICONTROL **1 時間ごと**] は、 [!UICONTROL **日付範囲**] オプションを [!UICONTROL **一般設定**] タブが [!UICONTROL **過去 1 時間**].</p><li>毎日</li><li>毎週</li><li>毎月</li><li>毎年</li></ul>  <!-- Is this valid? Was in the old docs: "To schedule Data Warehouse requests for Daily, Weekly, Monthly, or Yearly, make sure *Preset* is correctly selected" --> |
   | 毎月の繰り返し | レポートが送信されるまでの月間隔。 |
   | 日付 | レポートが送信される各月の日付。<p>このオプションを使用できる場合、 [!UICONTROL **月の週**] および [!UICONTROL **曜日**] オプションは無効です。 を選択します。 [!UICONTROL **代替形式**] ボタンを使用して切り替えることができます。 </p> |
   | 月間通算週 | レポートを送信する各月の週。 <p>次のオプションがあります。</p><ul><li>最初</li><li>2 番目</li><li>第 3</li><li>第 4</li><p>4 週間目（5 週間の月も含む）にレポートを送信します。 選択 [!UICONTROL **最後**] を設定します。</p><li>最後</li></ul><p>このオプションを使用できる場合、 [!UICONTROL **日**] オプションが無効です。 を選択します。 [!UICONTROL **代替形式**] ボタンを使用して切り替えることができます。 </p> |
   | 曜日 | レポートを送信する曜日。 <p>このオプションを使用できる場合、 [!UICONTROL **日**] オプションが無効です。 を選択します。 [!UICONTROL **代替形式**] ボタンを使用して切り替えることができます。 </p> |
   | 開始日 :  | 新しいスケジュールを開始する日付。 |
   | 時刻 | レポートを送信する時刻。 |
   | 配信終了オプション | スケジュールされた配信を終了するタイミングを選択します。 終了しない、特定の回数を超えた後に終了する、特定の日付に終了するなどを選択できます。 |

   {style="table-layout:auto"}

1. 引き続き、 [!UICONTROL **通知 E メール**] タブをクリックします。 詳しくは、 [通知リクエスト用の通知電子メールのData Warehouse](/help/export/data-warehouse/create-request/dw-request-email.md).

