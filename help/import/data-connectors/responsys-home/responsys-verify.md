---
description: デプロイメント後は、以下を確認し、統合によってデータが正常に転送されたことを検証する必要があります。
title: 統合の確認
uuid: 5f0f9f69-e932-4472-8578-dd3af1315c0c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%

---


# 統合の確認 {#verifying-the-integration}

デプロイメント後は、以下を確認し、統合によってデータが正常に転送されたことを検証する必要があります。

1. 統合アクティビティログを表示します。
   1. Adobe Experience Cloud で、**[!UICONTROL サポート]**／**[!UICONTROL 統合アクティビティログ]**&#x200B;に移動します。

      ![](assets/integration_activity_log.png)

   1. 「**[!UICONTROL 分類データは正常にインポートされました]**」、「**[!UICONTROL 指標データは正常にインポートされました]**」、「**[!UICONTROL 指標データは正常にエクスポートされました]**」などのエントリを探します。これらのエントリは、デプロイメントが成功してから 1 日以内に表示されます。
1. Adobe Analytics 内でレポートデータを表示します。

   1. **[!UICONTROL カスタムコンバージョン]**／**[!UICONTROL カスタムコンバージョン 1 ～ 10]**／**[!UICONTROL メッセージ ID レポート]**&#x200B;に移動します。

      ![](assets/reporting.png)

   1. Responsys レポートを探します。このデータは、デプロイメントが成功してから 24 ～ 48 時間以内に表示されます。
