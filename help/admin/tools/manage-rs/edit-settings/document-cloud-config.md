---
description: Adobe AnalyticsでDocument Cloud データを表示できます
title: Document Cloud レポートの設定
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
TQID: https://experienceleague.adobe.com/2X5YQxmTsMYdnwSWVL4EMr1K1aV9UM6FRMHa2P--Xuc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 140
ht-degree: 28%

---

# Document Cloud レポートの設定

PDF固有のディメンションと指標をAdobe Analyticsで使用できるように設定できます。

## PDF レポートを有効にするときに追加されたコンポーネント

PDF レポートが適切に設定されている場合、Adobe Analyticsでは次のディメンションと指標を使用できます。

**ディメンション：**

* PDF 検索語

* PDF ズームレベル

* PDF アクション

* PDF ページ番号

* PDF ファイル名

**指標：**

* PDF ビュー

* PDF ページビュー

* PDF ダウンロード

* PDF 検索

* PDF ブックマーク使用

* PDF コピーテキスト

* PDF 印刷

## Adobe AnalyticsでPDF レポートを有効にする

1. **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **`<select report suite>`** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Document Cloud Management]** > [!UICONTROL **Document Cloud Reporting**]&#x200B;に移動します。

1. Adobe Document Cloud Management ページで、[!UICONTROL **PDF レポートを有効にする**]&#x200B;を選択します。

1. Adobe Analyticsにデータを送信するようにAdobe Document Cloudを設定するには、[Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html)を使用します。
