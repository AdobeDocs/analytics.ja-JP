---
description: 'null'
title: Advertising Analytics 用のレポートスイートの有効化
uuid: 934f0e02-b5d7-4eca-93d8-92f95bd7014a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Advertising Analytics 用のレポートスイートの有効化

Advertising Analytics検索データをAnalyticsで表示するには、Advertising Analyticsレポート用にExperience cloudにマッピングされた各レポートスイートを設定する必要があります。

1. [レポートスイートを組織にマッピング](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html)します。
1. Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.

1. Select the report suite that is [mapped to your Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html).
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Advertising Analytics Configuration]**.

   ![](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO IDは、検索データの挿入先となるAdobe Advertising cloud変数を指します。

1. 変数の配分と AMO ID 変数で使用する有効期限を設定します。コンバージョン変数（eVar）を使用することで、Adobe Analytics は成功イベントを具体的な変数値と紐づけることができます。成功イベントが発生するまでに変数が変化することがあります。その場合、どの変数値にイベントのクレジットが付与されるかは、配分の設定によって決まります。

   | 設定 | 定義 |
   |--- |--- |
   | 元の値（最初） | 最初の値にクレジットのすべての配分が付与されます。それ以降の値は関係ありません。 |
   | 最新（最後） | 最後の値に成功イベントのクレジットのすべての配分が付与されます。その前にどのような変数が発生したかは関係ありません。 |
   | 有効期限 | eVar 値の有効期限が切れる（成功イベントのクレジットを受け取らなくなる）までの期間またはイベントを指定できます。eVar の有効期限が切れた後に成功イベントが発生した場合、「なし」がそのイベントのクレジットを受け取ることになります。つまり、アクティブな eVar がないということを示します。 |

1. Click **[!UICONTROL Enable Advertising Analytics Reporting]** (first time), or **[!UICONTROL Update Advertising Analytics Reporting]** (subsequent times). これで、レポートスイートが Advertising Analytics 検索データを受け取ることができます。[アカウントを作成できる](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)状態ではありません。

