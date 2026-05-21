---
description: 管理者レベルのユーザーは、組織全体の予定レポートを表示および管理できます。
title: 予定レポートキュー
feature: Admin Tools
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
exl-id: 7287e6c7-e354-48a0-9343-35dccfc46e63
role: Admin
TQID: https://experienceleague.adobe.com/HL78cbB5NqKCjv4NvZ5OiqjfbwBjI0KAC8hEr8Afd2U
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 51%

---

# 予定レポートキュー

管理者レベルのユーザーは、組織全体の予定レポートを表示および管理できます。

**[!UICONTROL Analytics]**／**[!UICONTROL コンポーネント]**／**[!UICONTROL すべてのコンポーネント]**／**[!UICONTROL 予定レポート]**

予定レポートマネージャーの管理者レベルの機能には次のものがあります。

* 組織内のすべてのスケジュール済みレポート [&#128279;](/help/components/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690)を表示するオプション。
* 組織全体で[高度なフィルタリング機能](/help/components/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275)。
* レポートサーバーで実行のためにキューに入れられているすべてのレポートを一覧表示する新しい[&#x200B; レポートキュー](/help/components/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) タブ。
* レポートキューインターフェイスで[&#x200B; スケジュール ID](/help/components/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1)を公開しています。

## スケジュール済みのすべてのレポートを表示 {#section_3F167CAAEEC24140B476CF95B7402690}

「**[!UICONTROL レポートリスト]**」タブでは、自身でスケジュールしたレポートに加えて、組織の&#x200B;**[!UICONTROL すべての予定レポートを表示]**&#x200B;できます。

>[!NOTE]
>
>「**[!UICONTROL レポート名]**」列にはスケジュールされているレポートの名前が表示され、「**[!UICONTROL ファイル名]**」列には「アドバンス配信」オプションで設定したカスタムファイル名が表示されます。 その結果、同じレポートタイプの複数のレポートをスケジュールし、それぞれにカスタマイズされた名前を指定すると、スケジュールされたレポートマネージャーには、同じレポート名で異なるファイル名を持つ複数のエントリが表示されます。 これは、スケジュールされているバックエンドレポートが同じであるため、「レポート名」列には、カスタマイズされたファイル名（設定されている）以外のすべてのレポート名が同じになります。

![](assets/show_all_scheduled_reports.png)

## 高度なフィルタリング機能 {#section_206A52A85DE84947AAB3AD082FBF6275}

例えば、1 時間ごとにスケジュールされたすべてのレポートをフィルタリングする場合は、**[!UICONTROL アドバンス]**&#x200B;フィルターで&#x200B;**[!UICONTROL 「頻度」「完全に一致する」「1 時間ごと」]**&#x200B;を指定して、「**[!UICONTROL 適用]**」をクリックします。

![](assets/advanced_filtering_schedl_reports.png)

## レポートキュー {#section_03C866115D354BB182E90BF4D52F1E0B}

このキューを使用すると、キューが「詰まっている」スケジュール済みレポートを管理および削除できます。 （通常、レポートは4時間後にタイムアウトします）。

![](assets/scheduled_reports_2.png)

レポートキューでは、「スケジュールされたレポートを1回スキップ」することもできます。 「**[!UICONTROL 管理]**」列にある青色のアイコンをクリックします。

## スケジュール ID {#section_568B70F4228C4229977CB85D2DCD53A1}

レポートキューインターフェイスで公開された&#x200B;**[!UICONTROL スケジュール ID]** は、予定レポートの問題を解決するために Adobe Client Care に連絡する必要がある場合に役立ちます。

![](assets/schedule_id.png)
