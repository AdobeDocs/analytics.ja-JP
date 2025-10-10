---
description: Advertising Analytics で使用する、Experience Cloud をマッピングしたレポートスイートを設定します。
title: Advertising Analytics 用のレポートスイートの有効化
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 47%

---

# Advertising Analytics 用のレポートスイートの有効化

Analytics でAdvertising Analyticsの検索データを表示するには、Experience Cloudにマッピングされた各レポートスイートをAdvertising Analytics レポート用に設定する必要があります。

1. **[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]** に移動します。

1. Experience Cloud の組織にマッピングされているレポートスイートを選択します。
1. **[!UICONTROL 設定の編集]**／**[!UICONTROL Advertising Analytics 設定]**&#x200B;をクリックします。

   ![レポート](assets/aa-reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID とは、検索データが挿入される Adobe Advertising Cloud （Adobe Media Optimizer とも呼ばれます）変数を指します。

1. 「**[!UICONTROL Advertising Analyticsに慣れていない？ Advertising Analyticsについて詳しくは]** ここをクリックしてください。

1. AMO ID 変数で使用する変数の配分と有効期限を設定します。 コンバージョン変数（eVar）を使用することで、Adobe Analytics は成功イベントを具体的な変数値と紐づけることができます。成功イベントが発生するまでに変数が変化することがあります。その場合、どの変数値にイベントのクレジットが付与されるかは、配分の設定によって決まります。

   | 設定 | 定義 |
   |--- |--- |
   | **[!UICONTROL 配分]** | 次の範囲を選択：<br/> **[!UICONTROL 元の値（最初）]**：表示される最初の値は、その変数の後続の値に関係なく、完全な配分クレジットを取得します。 <br/>**[!UICONTROL  最新（最後） ]**：表示された最後の値は、以前に発生した変数に関係なく、成功イベントの完全な配分クレジットを取得します。 |
   | **[!UICONTROL 有効期限]** | eVar値の有効期限が切れる（つまり、成功イベントのクレジットを受け取らなくなる）期間またはイベントを指定できます。  eVar の有効期限が切れた後に成功イベントが発生した場合、「なし」値がそのイベントのクレジットを受け取ることになります。つまり、アクティブな eVar がないということを示します。 |

1. 「**[!UICONTROL Advertising Analytics レポートを有効にする]**」（初回時）、または「**[!UICONTROL Advertising Analytics レポートを更新]**」（2 回目以降）をクリックします。これで、レポートスイートが Advertising Analytics 検索データを受け取ることができます。これで、[Advertising アカウントの作成 ](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) を行う準備が整いました。
