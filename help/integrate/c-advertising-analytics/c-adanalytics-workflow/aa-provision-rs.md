---
description: Advertising Analyticsで使用するCX Enterprise マッピング済みレポートスイートを設定します。
title: Advertising Analytics 用のレポートスイートの有効化
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
TQID: 'https://experienceleague.adobe.com/sGEXiz2RiDhf9p-2df76o-XxBERTKPB-O-rZeIb4BBI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 18%

---

# Advertising Analytics 用のレポートスイートの有効化

AnalyticsでAdvertising Analyticsの検索データを表示するには、Advertising Analytics レポート用にCX Enterpriseでマッピングされた各レポートスイートを設定する必要があります。

1. **[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]** に移動します。

1. CX Enterprise組織にマッピングされているレポートスイートを選択します。
1. **[!UICONTROL 設定の編集]**／**[!UICONTROL Advertising Analytics 設定]**&#x200B;をクリックします。

   ![レポート](assets/aa-reporting.png)

1. 「**[!UICONTROL Advertising Analyticsに慣れていない」を選択します。 Advertising Analyticsについて詳しくは、ここをクリックして]**&#x200B;の詳細をご覧ください。

1. AMO ID変数で使用する変数の割り当てと有効期限を設定します。 コンバージョン変数（eVar）を使用すると、Adobe Analyticsは成功イベントを特定の変数値に関連付けることができます。 変数が成功イベントに達する前に、複数の値が検出されることがあります。 このような場合、配分によって、イベントのクレジットを取得する変数値が決まります。

   | 設定 | 定義 |
   |--- |--- |
   | **[!UICONTROL 配分]** | 次の範囲で選択：<br/> **[!UICONTROL 元の値（最初）]**：表示された最初の値は、その変数の後続の値に関係なく、完全な割り当てのクレジットを取得します。 <br/>**[!UICONTROL 直近（最後） &#x200B;]**：最後に表示された値は、その前に実行された変数に関係なく、成功イベントに対する完全な割り当てクレジットを取得します。 |
   | **[!UICONTROL 有効期限]** | EVarの値が期限切れになるまでの期間またはイベントを指定できます（つまり、サクセスイベントのクレジットを受け取ることができなくなります）。  eVar の有効期限が切れた後に成功イベントが発生した場合、「なし」値がそのイベントのクレジットを受け取ることになります。つまり、アクティブな eVar がないということを示します。 |

1. 「**[!UICONTROL Advertising Analytics レポートを有効にする]**」（初回）または「**[!UICONTROL Advertising Analytics レポートを更新]**」（後回）をクリックします。 これで、レポートスイートでAdvertising Analytics検索データを受け取る準備が整いました。 これで、[Advertising アカウントを作成する準備が整いました](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)。
