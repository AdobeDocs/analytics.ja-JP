---
description: ブックマークされたレポートおよびダッシュボードレポートはすべて、リクエストウィザードの手順 1 でディメンションとして表示され、Report Builderリクエストとしてインポートできるようになりました。
title: ブックマークされたレポートおよびダッシュボードレポートのインポート
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 65%

---

# ブックマークされたレポートおよびダッシュボードレポートのインポート

{{legacy-arb}}

ブックマークされたレポートおよびダッシュボードレポートはすべて、リクエストウィザードの手順 1 でディメンションとして表示され、Report Builderリクエストとしてインポートできるようになりました。

ブックマークされたレポートを選択すると、リクエストウィザードでは、このブックマークされたレポートを定義するすべてのディメンションおよび指標が自動的に選択状態になります。日付範囲、精度、選択したセグメントも、選択したブックマークに基づいて更新されます。

リクエストウィザードの手順 1 では、次のようにダッシュボードおよびそのレポートレットが表示されます。

![ リクエストウィザードの手順 1 を示すスクリーンショット/2 でダッシュボードの取得とブックマークの取得をハイライト表示 ](assets/import_dashboard_reportlet.png)

「**[!UICONTROL ダッシュボードを取得]**」または「**[!UICONTROL ブックマークを取得]**」をクリックすると、既存のダッシュボードまたはブックマークの設定情報が取得され、リクエストウィザードの設定に反映されます。

>[!NOTE]
>
>データのみがインポートされるので、ブックマークにチャートが含まれている場合や、ダッシュボードレポートレットがチャートのみで構成されている場合は、チャートの作成に使用されているデータのみがインポートされます。

ダッシュボードレポートレット（またはブックマーク）をインポートしてリクエストを作成すると、そのリクエストはレポートレット（またはブックマーク）のプライマリディメンションに関連付けられます。その結果、リクエストを編集する場合、ツリービューではダッシュボードレポートレットのツリービューノード（またはブックマークノード）は選択されず、代わりにプライマリディメンションが選択された状態になります。

