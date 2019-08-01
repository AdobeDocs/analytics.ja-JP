---
description: 統合ウィザードを完了したら、接続するQualtrics調査ごとに統合をアクティブ化する必要があります。
seo-description: 統合ウィザードを完了したら、接続するQualtrics調査ごとに統合をアクティブ化する必要があります。
seo-title: Qualtricsリサーチスイートでの統合の有効化
solution: Analytics
subtopic: Qualtrics
title: Qualtricsリサーチスイートでの統合の有効化
topic: Data Connectors
uuid: 2cc6fa4a- d17e-4560- bd5b-1790851d6274
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Enabling the Integration in Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

統合ウィザードを完了したら、接続するQualtrics調査ごとに統合をアクティブ化する必要があります。

1. Qualtrics Research Suiteにログインします。
1. On the **[!UICONTROL My Surveys]** tab, click the **[!UICONTROL Edit]** button for the survey that you want to integrate.
1. **[!UICONTROL アドバンスオプション]** メニューをクリックし、「 **[!UICONTROL Adobe Analytics]**」を選択します。（このオプションが表示されない場合は、必要な権限の取得について管理者に問い合わせてください）。

   ![](assets/advanced_options.png)

1. Select the Adobe Analytics Configuration, then click **[!UICONTROL Save]**. 設定が使用できない場合は、Adobe統合ウィザードをまだ完了していません。
   1. The **[!UICONTROL Include Partial Responses]** checkbox can be used to indicate that you’d like to capture data into Adobe Analytics after each partial survey screen is completed. チェックしないと、完全に完了した調査にのみデータが転送されます。
   1. **[!UICONTROL «送信タイムスタンプ付きの送信タイムスタンプ»]** チェックボックスは、タイムスタンプ付きのデータを受信するように設定されているレポートスイートと統合する場合にのみ使用してください（一般的ではありません）。
   ![](assets/integration_config.png)

