---
description: Advertising Analytics ワークフローの概要
title: ワークフローの概要
exl-id: 00993c19-1e74-4a97-b16a-967feab13b32
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '164'
ht-degree: 100%

---

# ワークフローの概要

![](assets/step1_icon.png) Google と Bing の検索データを表示する Adobe Analytics レポートスイートを、Experience Cloud 組織にマッピングします。

[組織へのレポートスイートのマッピング](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/report-suite-mapping.html)を参照してください。

![](assets/step2_icon.png) [レポートスイートごとの Advertising Analytics レポートの有効化](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)

Experience Cloud 対応レポートスイートの [!UICONTROL Advertising Analytics] レポートを有効にします。

![](assets/step3_icon.png) [Advertising Analytics アカウントの設定](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)

Analytics 管理ツールで設定します。

![](assets/step4_icon.png) [Analytics での広告データのレポート](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md)

注意：検索データは、Adobe Analytics データセンターのタイムゾーンの午前 6 時ごろに検索エンジンから取り込まれます。この時点で AMO データが収集され、レポートスイートに挿入されます。さらに AMO データは Analytics へのデータ挿入の一環としてレポートスイートのタイムゾーンに変換されます。

レポートは以下で利用できます。

* Analysis Workspace：[!UICONTROL 有料検索パフォーマンス]テンプレート
* Reports &amp; Analytics
* Report Builder
* Analytics レポート API

![](assets/step5_icon.png) [広告アカウントの管理](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)

アカウントの状態をチェックして、アカウントを編集／一時停止できます。
