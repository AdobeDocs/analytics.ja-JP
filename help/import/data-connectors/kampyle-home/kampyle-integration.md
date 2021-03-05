---
description: KampyleデータコネクタとAdobe Analyticsを使用します。
title: 統合の使用
uuid: b39c1334-ac0f-431b-a34f-27ff9b068e33
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 96%

---


# 統合の使用 {#using-the-integration}

デプロイ後は、この統合で提供されている追加機能を使用できるようになります。以下は、Adobe Analytics 内でこの統合を活用するために実行するアクションです。

>[!NOTE]
>
>Adobe Analytics レポート内で Kampyle 応答データが表示され始めるまでに 24 ～ 48 時間かかる場合があります。

## フィードバックとオンサイトの行動データの混在 {#mix-feedback-and-onsite-behavior-data}

Reports &amp; Analytics レポートをフィードバックディメンション別に分類できます。

Adobe Reports &amp; Analytics を使用し、レポートで使用できる多数のフィードバックディメンションを掘り下げて調べることができます。以下のレポートは、特定のフィードバックカテゴリ別に掘り下げ、フィードバックの説明で分類した例です。Reports &amp; Analytics（訪問回数および顧客サービスの問い合わせ）と Kampyle（平均フィードバックグレード）の両方の指標が並べて表示され、分析が容易になります。

![](assets/feedback_category_report.png)

## フィードバックディメンション別のセグメント {#segment-by-feedback-dimension}

フィードバックのディメンションに基づいてセグメントを作成できます。

この統合の主な特長は、Kampyle フィードバックディメンションに基づいて Adobe Analytics セグメントを作成できる機能です。例えば、グレード 1 または 2 が与えられた訪問のみを含むセグメントを作成できます。これに「フィードバックグレード - 低」という名前を付けることができます。このセグメントの定義は次のようになります。

![](assets/segment_feedback.png)

このセグメントは、ほぼすべてのレポートに適用できます。例として、ここに示す訪問別滞在時間レポートなどがあります。

![](assets/time_spent_per_visit.png)
