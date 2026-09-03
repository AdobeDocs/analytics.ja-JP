---
description: Report BuilderでのAnalysis Workspace テンプレートとレポートの詳細。
title: Adobe Analytics での広告データのレポート
feature: Advertising Analytics
exl-id: bbc830d9-e168-471d-a1ba-308277aab415
TQID: https://experienceleague.adobe.com/BOly6gaT1ybHWDppJzhi9ILClvJ9UoLzkGFua1gS1lo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: a9364d69-0c51-44bf-8b5f-6d99c04493b8id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 350
ht-degree: 9%

---

# 広告データのレポート

この記事では、Analysis Workspace レポートとReport Builderでのレポートについて詳しく説明します。

>[!NOTE]
>
>検索エンジンデータがAnalytics レポートの入力を開始するには、少なくとも24時間待つ必要があります。 Adobe Advertising dataでは時間単位の精度はサポートされていないため、Analytics レポートでは時間単位の精度に関するデータは返されません。

## 有料検索レポート {#section_8173F42B2C784F41B9FD82CBB66F9ADF}

このレポートでは、検索エンジン統合を実装するユーザーは誰でも、Analytics内の検索エンジンデータにアクセスできます。 **[!UICONTROL Workspace]** > **[!UICONTROL レポート]** > **[!UICONTROL 獲得]** > **[!UICONTROL Advertising Analytics：有料検索]**&#x200B;からアクセスできます

>[!NOTE]
>
>Advertising アカウントを実装していない場合でも、有料検索レポートはすべての顧客に表示されます。 プロビジョニングされていない会社の有料検索レポートを開こうとすると、検索エンジンアカウントを設定していないことを示すエラーメッセージが表示されます。 「**[!UICONTROL 今すぐ設定]**」を選択すると、[Advertising アカウント設定](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)画面に移動します。

![](assets/aa_aw.png)  ![](assets/aa_aw2.png) ![](assets/aa_aw3.png) ![](assets/aa_aw4.png)  ![](assets/aa_aw5.png) ![](assets/aa_aw6.png)

| テーブル/ビジュアライゼーション | 説明 |
|--- |--- |
| 広告のトレンド | AMO インプレッション数、AMO クリック数、AMO コストの日次トレンドの概要。 |
| 広告プラットフォーム | 上位2つのプラットフォーム（Google Ads、Microsoft Advertising）のコストのドーナツチャート。 |
| 広告プラットフォーム合計 | AMO インプレッション数、AMO クリック数、AMO コスト、AMO Avg別に分類されたトッププラットフォームのフリーフォームテーブル。 AMO平均順位 品質スコアです。 |
| アカウント | 積み重ねコストの領域。 |
| アカウント合計 | 関連する指標ごとに分類された上位アカウントのフリーフォームテーブル。 |
| キャンペーン | キャンペーンコストを棒グラフで表示。 |
| キャンペーン合計 | 関連する指標ごとに分類された上位のキャンペーンのフリーフォームテーブル。 |
| グループ | コストのツリーマップ。 |
| グループ合計 | 関連する指標ごとに分類された、上位の広告グループのフリーフォームテーブル。 |
| 広告 | インプレッション数、クリック数、コストを示す横棒グラフ。 |
| 広告合計 | 上位の広告のフリーフォームテーブルを関連する指標で分類。 |
| キーワード | すべてのキーワード/一致タイプの組み合わせに対するインプレッション数、クリック数、コストの散布図。 |
| キーワード合計 | 上位のキーワード/一致タイプの組み合わせのフリーフォームテーブルを、関連する指標ごとに分類します。 |

## Report Builder {#section_8E0371CF81144C33990D909685D1726E}

Advertising Analytics アカウントを設定すると、Advertising Analytics レポートが使用できるようになります。
