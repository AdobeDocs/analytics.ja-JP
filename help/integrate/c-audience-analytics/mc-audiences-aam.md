---
description: Adobe Audience Manager（Adobe Audience Manager）は、ファーストパーティ、セカンドパーティ/パートナー、サードパーティのデータ統合から独自のオーディエンスプロファイルを作成するのに役立つ、強力なデータ管理プラットフォームです。 広告主の場合、これらのオーディエンスプロファイルを利用すれば、デジタルチャネル全体で最も効果的なセグメントを定義できます。
solution: Experience Cloud
title: Audience Analytics の概要
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 42%

---

# Audience Analytics の概要

Adobe Audience Manager（Adobe Audience Manager）は、ファーストパーティ、セカンドパーティ/パートナー、サードパーティのデータ統合から独自のオーディエンスプロファイルを作成するのに役立つ、強力なデータ管理プラットフォームです。 広告主の場合、これらのオーディエンスプロファイルを利用すれば、デジタルチャネル全体で最も効果的なセグメントを定義できます。

Audience Analyticsの統合を行うと、人口統計情報（性別や所得水準など）、心理学的情報（興味や趣味など）、CRM データ、広告インプレッションデータなどのAdobe Audience Manager オーディエンスデータを任意の Analytics ワークフローに組み込むことができます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://video.tv.adobe.com/v/25450?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## 主なメリット  {#benefits}

Audience Analytics 統合には次の主要なメリットがあります。

* 市場で初めて製品化されたデータ管理プラットフォーム（DMP）と分析エンジンの統合製品です。
* セグメントは、Adobe Audience Managerから Analytics にリアルタイムで共有され、オーディエンスの検出、セグメント化および最適化を知らせます。
* すべてのAdobe Audience Manager セグメントはデフォルトで共有され、Analytics で顧客プロファイルが完全に強化されます。
* ソリューション管理者は、ユーザーインターフェイスから統合を有効にすることができ、コードの変更は最小限で済みます。
* Audience Manager のデータエクスポートコントロールに準拠するセグメントのみが共有されます。

## Audience Analyticsの仕組み {#works}

![](assets/mc-aud-dataflow.png)

1. デジタルプロパティに訪問者が訪問するたびに、ヒットが収集されて Analytics に送信されます。
1. [ サーバーサイド転送 ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md) を使用すると、Analytics が受け取る各ヒットがリアルタイムでAdobe Audience Managerに自動的に送信されます。
1. Audience Analyticsの統合により、ヒットごとに、訪問者のオーディエンスメンバーシップがAdobe Audience Managerで検索され、セグメント ID のリストが Analytics に返されて、リアルタイムに処理されます。

Adobe Audience Manager セグメントは同じヒットに基づいて挿入されるので、訪問者に関してAdobe Audience Managerで利用できるすべてのデータが欠落することなく、そのヒットの最新の状態に保つことができます。 AppMeasurement プラグインでは、これらのセグメントを次のヒットでのみ使用できます（現在のヒットでは使用できません）。Analytics データ収集は、この点で AppMeasurement プラグインより優れています。

さらに、Analytics レポートで英数字の ID を確認する必要がないように、Adobe Audience Managerのセグメント ID がわかりやすい名前に自動的に分類されます。

## 前提条件 {#prerequisites}

次の前提条件を満たしていることを確認します。

* Audience Manager と Adobe Analytics の両方のユーザーである。
* Audience Manager 管理者である。
* ID サービス v1.5 以降を使用している。
* Adobe Audience ManagerおよびAdobe Analytics レポートスイートが、同じExperience Cloud組織にマッピングされている。
* [サーバー側転送](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)を使用していて、[Audience Management モジュール](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=ja)（DIL コードなし） - AppMeasurement 1.5 以降を実装している。

これらの前提条件は、[Audience Analytics ワークフロー](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)に記載されています。
