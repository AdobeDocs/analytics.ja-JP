---
description: Advertising Analytics で使用する、Experience Cloud をマッピングしたレポートスイートを設定します。
title: Advertising Analytics 用のレポートスイートの有効化
uuid: 934f0e02-b5d7-4eca-93d8-92f95bd7014a
translation-type: ht
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: ht
source-wordcount: '283'
ht-degree: 100%

---


# Advertising Analytics 用のレポートスイートの有効化

Advertising Analytics の検索データを Analytics で表示するには、Experience Cloud をマッピングした各レポートスイートを Advertising Analytics レポート用に設定する必要があります。

1. [レポートスイートを組織にマッピング](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/report-suite-mapping.html)します。
1. **[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;に移動します。

1. Experience Cloud の組織にマッピングされているレポートスイートを選択します。
1. **[!UICONTROL 設定の編集]**／**[!UICONTROL Advertising Analytics 設定]**&#x200B;をクリックします。

   ![レポート](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID は、検索データの挿入先となる Adobe Advertising Cloud 変数を参照します。

1. 変数の配分と AMO ID 変数で使用する有効期限を設定します。コンバージョン変数（eVar）を使用することで、Adobe Analytics は成功イベントを具体的な変数値と紐づけることができます。成功イベントが発生するまでに変数が変化することがあります。その場合、どの変数値にイベントのクレジットが付与されるかは、配分の設定によって決まります。

   | 設定 | 定義 |
   |--- |--- |
   | 元の値（最初） | 最初の値にクレジットのすべての配分が付与されます。それ以降の値は関係ありません。 |
   | 最新（最後） | 最後の値に成功イベントのクレジットのすべての配分が付与されます。その前にどのような変数が発生したかは関係ありません。 |
   | 有効期限 | eVar 値の有効期限が切れる（成功イベントのクレジットを受け取らなくなる）までの期間またはイベントを指定できます。eVar の有効期限が切れた後に成功イベントが発生した場合、「なし」がそのイベントのクレジットを受け取ることになります。つまり、アクティブな eVar がないということを示します。 |

1. 「**[!UICONTROL Advertising Analytics レポートを有効にする]**」（初回時）、または「**[!UICONTROL Advertising Analytics レポートを更新]**」（2 回目以降）をクリックします。これで、レポートスイートが Advertising Analytics 検索データを受け取ることができます。[アカウントを作成できる](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)状態ではありません。

