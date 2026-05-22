---
description: Adobe Audience Manager（Adobe Audience Manager）は、ファーストパーティ、セカンドパーティ/パートナー、サードパーティデータの統合から、独自のオーディエンスプロファイルを構築するのに役立つ強力なデータ管理基盤です。 広告主にとって、これらのオーディエンスプロファイルは、あらゆるデジタルチャネルで使用すべき最も価値のあるセグメントを定義するのに役立ちます。
solution: Analytics
title: Audience Analytics の概要
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
TQID: 'https://experienceleague.adobe.com/WPB1fEJx1MaWpUNRCZ48ghAVyKyc5IwoGOdgQQ-tPhI'
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
subfeature_v2: id: a97e0d8c-238a-47ee-8d81-16bd45309bed
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: df401a2a-327d-468c-a5e4-b7b7ccd071a0id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 522
ht-degree: 11%

---

# Audience Analytics の概要

Adobe Audience Manager（Adobe Audience Manager）は、ファーストパーティ、セカンドパーティ/パートナー、サードパーティデータの統合から、独自のオーディエンスプロファイルを構築するのに役立つ強力なデータ管理基盤です。 広告主にとって、これらのオーディエンスプロファイルは、あらゆるデジタルチャネルで使用すべき最も価値のあるセグメントを定義するのに役立ちます。

Audience Analyticsとの連携により、デモグラフィック情報（性別や収入レベルなど）、サイコグラフィック情報（興味や趣味など）、CRM データ、広告インプレッションデータなどのAdobe Audience Managerのオーディエンスデータを任意のAnalytics ワークフローに組み込むことができます。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/audience-manager/audience-analytics-integrate-aam-segments-into-analytics){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## 主なメリット {#benefits}

Audience Analyticsとの連携には、次の主な利点があります。

* これは、DMP（Data Management Platform）と分析エンジンの間で、市場で初めて製品レベルで連携したものです。
* セグメントは、Adobe Audience ManagerからAdobe Analyticsにリアルタイムで共有され、オーディエンスの発見、セグメンテーション、最適化に活用されます。
* あらゆるAdobe Audience Managerセグメントは、デフォルトで共有されており、Analyticsで顧客プロファイルを完全に強化します。
* ソリューション管理者は、コードの変更を最小限に抑えながら、ユーザーインターフェイスを通じた統合を実現できます。
* Audience Manager データ書き出し制御に準拠するセグメントのみが共有されます。

## Audience Analyticsの仕組み {#works}

![](assets/mc-aud-dataflow.png)

1. 訪問者がデジタルプロパティにアクセスするたびに、ヒット数が収集され、Analyticsに送信されます。
1. [ サーバーサイド転送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)を使用すると、Analyticsが受け取る各ヒットは、リアルタイムで自動的にAdobe Audience Managerに送信されます。
1. Audience Analyticsとの統合により、ヒットごとに訪問者のオーディエンスメンバーシップがAdobe Audience Managerで検索され、セグメント IDのリストがAnalyticsに返され、リアルタイムで処理されます。

Adobe Audience Managerのセグメントは同じヒット単位で挿入されるため、Adobe Audience Managerで使用可能な訪問者に関するデータを見逃すことなく、そのヒットに関する最新の情報を確認することができます。 これはAppMeasurement プラグインよりも優れています。プラグインでは、これらのセグメントを（現在のヒットではなく）次のヒットでのみ使用できます。

また、Adobe Audience Manager セグメント IDは、Analytics レポートで英数字IDを確認する必要がないように、わかりやすい名前に自動的に分類されます。

## 前提条件 {#prerequisites}

次の前提条件が満たされていることを確認します。

* あなたはAudience ManagerとAdobe Analyticsの両方のお客様です。
* あなたはAudience Manager管理者です。
* ID サービス v1.5 以降を使用している。
* Adobe Audience ManagerとAdobe Analyticsのレポートスイートは、同じCX Enterprise組織にマッピングされます。
* [サーバー側転送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)を使用していて、[Audience Management モジュール](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=ja)（DIL コードなし） - AppMeasurement 1.5 以降を実装している。

これらの前提条件は、[Audience Analytics ワークフロー](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)に記載されています。
