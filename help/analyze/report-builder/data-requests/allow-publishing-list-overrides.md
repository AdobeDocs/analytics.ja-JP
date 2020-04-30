---
description: レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。
title: 発行リストの上書きの許可
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 発行リストの上書きの許可

レポートをスケジュールする場合、その配信に使用する発行リストを選択できます。

発行リストは Analytics 管理ツールで設定しておく必要があります。

Analytics リファレンスの[発行リスト](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/publishing-list.html)を参照してください。

この機能を有効にするには、ウィンドウに移動 [!UICONTROL Request Wizard: Step 1] します。

If you enable [!UICONTROL Allow Publishing List Override], the report suite assigned to each recipient in the publishing list replaces the report suite for this request. ワークブックに複数のレポートスイートが含まれている場合でも、この発行リストに関連付けられた 1 つのレポートスイート ID が使用される点にご注意ください。

このレポートスイート変更機能は、セルから選択したレポートスイート ID に対しては適用されません。

>[!NOTE]予定レポートを複数の発行リストに対して送信する場合、各リストに対してレポートが一度実行されます。対象レポートスイートは、発行リストに割り当てられたレポートスイートに置き換えられます。

