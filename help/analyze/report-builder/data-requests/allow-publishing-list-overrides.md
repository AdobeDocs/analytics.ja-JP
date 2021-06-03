---
description: レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。
title: 発行リストの上書きの許可
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
feature: Report Builder
role: Business Practitioner, Administrator
exl-id: a7bd6cdb-397a-45ba-88ff-c3b3c7062005
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 95%

---

# 発行リストの上書きの許可

レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。

発行リストは Analytics 管理ツールで設定しておく必要があります。

Analytics リファレンスの[発行リスト](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/publishing-list.html)を参照してください。

この機能を有効にするには、[!UICONTROL リクエストウィザード：ステップ 1] ウィンドウを開きます。

「[!UICONTROL 発行リストの上書きを許可]」を有効にすると、発行リスト内で各受信者に割り当てられたレポートスイートが、このリクエスト用に指定されたレポートスイートの代わりに使用されます。ワークブックに複数のレポートスイートが含まれている場合でも、この発行リストに関連付けられた 1 つのレポートスイート ID が使用される点にご注意ください。

このレポートスイート変更機能は、セルから選択したレポートスイート ID に対しては適用されません。

>[!NOTE]
>
>予定レポートを複数の発行リストに対して送信する場合、各リストに対してレポートが一度実行されます。対象レポートスイートは、発行リストに割り当てられたレポートスイートに置き換えられます。
