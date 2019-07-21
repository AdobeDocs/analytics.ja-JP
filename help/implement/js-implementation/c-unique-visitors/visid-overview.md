---
description: アドビでは Cookie を使用して個別のブラウザーおよびデバイスを追跡しています。
keywords: Analytics の導入
seo-description: アドビでは Cookie を使用して個別のブラウザーおよびデバイスを追跡しています。
seo-title: 個別訪問者の特定
solution: Analytics
subtopic: 訪問者数
title: 個別訪問者の特定
topic: 開発者と導入
uuid: ed4dee75- ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 個別訪問者の特定

アドビでは cookie を使用して個別のブラウザーおよびデバイスを追跡しています。

## Analytics 訪問者 ID の順序 {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics は、訪問者を識別するための様々な手段を提供しています。次の表に、Analytics で訪問者が識別される方法を優先順で示します。

| 使用順序 | クエリパラメーター（収集方法） | 次の場合に存在 |
|---|---|---|
| ![](assets/step1_icon.png) | [vid（s.visitorID）](../../../implement/js-implementation/c-unique-visitors/visid-custom.md#concept_4A2000F4B6ED41E99CA6118A6D74ECE8) | s.visitorID が設定されている場合 |
| ![](assets/step2_icon.png) | [aid（s_vi Cookie）](../../../implement/js-implementation/c-unique-visitors/visid-analytics.md#concept_74F6B4B9B2FA415AB5D029A1F8F099BC) | 訪問者 ID サービスを展開する前に訪問者が既に s_vi cookie を持っていた、または訪問者 ID 猶予期間が設定済みである。 |
| ![](assets/step3_icon.png) | [mid（Experience Cloud 訪問者 ID サービスによって設定される AMCV_ Cookie）](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 訪問者のブラウザーが cookie（ファーストパーティ）を受け入れる場合 |
| ![](assets/step4_icon.png) | [fid（H.25.3 以降の代替の cookie、または JavaScript 版 AppMeasurement）](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#concept_EBCBF9EB390E45A2BA20DB6BE931C505) | 訪問者のブラウザーが cookie（ファーストパーティ）を受け入れる場合 |
| ![](assets/step5_icon.png) | [IP アドレス、ユーザーエージェント、ゲートウェイ IP アドレス](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | 訪問者のブラウザーが cookie を受け入れない場合 |

多くの場合、2 ～ 3 の異なる ID が表示されますが、Analytics では前述の表に現れる最初の ID を正式な訪問者 ID として使用します。例えば、（「vid」クエリパラメーターに含まれる）カスタム訪問者 ID を設定している場合、その ID が同様にヒットした他の ID に先立って使用されます。

>[!NOTE]
>
>各Analytics訪問者IDは、Adobeサーバー上の訪問者プロファイルに関連付けられています。訪問者プロファイルは、少なくとも 13 ヶ月操作が実行されなかった場合、訪問者 ID cookie の有効期限にかかわらず削除されます。
