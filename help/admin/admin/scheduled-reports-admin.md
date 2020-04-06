---
description: 管理者レベルのユーザーは、組織全体の予定レポートを表示および管理できます。
title: 予定レポートキュー
topic: Reports
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 予定レポートキュー

管理者レベルのユーザーは、組織全体の予定レポートを表示および管理できます。

**[!UICONTROL Analytics]**／**[!UICONTROL Components]**／**[!UICONTROL Scheduled Reports]**

予定レポートマネージャーの管理者レベルの機能には次のものがあります。

* 組織内のすべての [予定レポートを表示する](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) オプション。
* [組織全体の高度なフィルター機能](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) 。
* 新しい「レポ [ートキュー](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) 」タブ。このタブでは、レポートサーバーで実行するためにキューに登録されているすべてのレポートをリストします。
* レポートキ [ューインターフェイス](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) でのスケジュールIDの公開。

## Show all Scheduled Reports {#section_3F167CAAEEC24140B476CF95B7402690}

このタブ **[!UICONTROL Report List]** では、自分で **[!UICONTROL Show All Scheduled Reports]** スケジュールしたものに加えて、組織内でも構いません。

>[!NOTE] この列 **[!UICONTROL Report Name]** には、予定されているレポートの名前が表示され、列には、[アドバンスオプション]で設 **[!UICONTROL File Name]** 定したカスタムファイル名が配信されます。 その結果、同じレポートタイプの複数のレポートをスケジュールし、それぞれにカスタマイズした名前を指定した場合、予定レポートマネージャーには、同じレポート名で異なるファイル名の複数のエントリが表示されます。 これは、スケジュールされるバックエンドレポートが同じなので、「レポート名」列にはすべてのレポートに同じレポート名が付けられますが、ファイル名は（設定どおりに）カスタマイズされるからです。

![](assets/show_all_scheduled_reports.png)

## 高度なフィルタリング機能 {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## レポートキュー {#section_03C866115D354BB182E90BF4D52F1E0B}

このキューを使用すると、キューを「詰まらせている」予定レポートを管理したり、削除したりできます。 （通常、レポートは4時間後にタイムアウトになります）。

![](assets/scheduled_reports_2.png)

レポートキューでは、「予定レポートを1回スキップ」する機能も提供されます。 Just click the blue icon in the **[!UICONTROL Manage]** column.

## スケジュール ID {#section_568B70F4228C4229977CB85D2DCD53A1}

Having the **[!UICONTROL Schedule ID]** exposed in the Report Queue interface helps when you need to contact Adobe Client Care for resolution of a scheduled reports issue.

![](assets/schedule_id.png)
