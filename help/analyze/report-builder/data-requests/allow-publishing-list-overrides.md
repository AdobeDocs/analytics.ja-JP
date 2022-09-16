---
description: レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。
title: 発行リストの上書きの許可
feature: Report Builder
role: User, Admin
exl-id: a7bd6cdb-397a-45ba-88ff-c3b3c7062005
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 100%

---

# 発行リストの上書きの許可

レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。

発行リストは Analytics 管理ツールで設定しておく必要があります。

Analytics リファレンスの[発行リスト](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/publishing-list.html?lang=ja)を参照してください。

この機能を有効にするには、[!UICONTROL リクエストウィザード：ステップ 1] ウィンドウを開きます。

「[!UICONTROL 発行リストの上書きを許可]」を有効にすると、発行リスト内で各受信者に割り当てられたレポートスイートが、このリクエスト用に指定されたレポートスイートの代わりに使用されます。ワークブックに複数のレポートスイートが含まれている場合でも、この発行リストに関連付けられた 1 つのレポートスイート ID が使用される点にご注意ください。

このレポートスイート変更機能は、セルから選択したレポートスイート ID に対しては適用されません。

>[!NOTE]
>
>予定レポートを複数の発行リストに対して送信する場合、リストごとにレポートが 1 回実行されます。変数となっているレポートスイートは、発行リストに割り当てられたレポートスイートに置き換えられます。
