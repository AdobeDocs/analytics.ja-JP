---
description: Adobe Audience Manager（AAM）は、ファーストパーティ、セカンドパーティ／パートナーおよびサードパーティのデータ統合から一意のオーディエンスプロファイルを構築できる強力なデータ管理プラットフォームです。広告主の場合、これらのオーディエンスプロファイルを利用すれば、デジタルチャネル全体で最も効果的なセグメントを定義できます。
solution: Experience Cloud
title: Audience Analytics の概要
uuid: 86ef9391-dd6a-495f-a10e-e98bc069dde4
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '464'
ht-degree: 100%

---

# Audience Analytics の概要

Adobe Audience Manager（AAM）は、ファーストパーティ、セカンドパーティ／パートナーおよびサードパーティのデータ統合から一意のオーディエンスプロファイルを構築できる強力なデータ管理プラットフォームです。広告主の場合、これらのオーディエンスプロファイルを利用すれば、デジタルチャネル全体で最も効果的なセグメントを定義できます。

Audience Analytics を統合したら、デモグラフィック情報（性別、所得水準など）、サイコグラフィック情報（興味や趣味）、CRM データ、広告インプレッションデータといった AAM オーディエンスのデータを、任意の Analytics ワークフローに組み込むことができます。

## 主要なメリット {#section_94816D17283349E0BA28521BE55BB868}

Audience Analytics 統合には次の主要なメリットがあります。

* 市場で初めて製品化されたデータ管理プラットフォーム（DMP）と分析エンジンの統合製品です。
* セグメントは AAM から Analytics にリアルタイムで共有され、オーディエンスの検出、セグメント化および最適化が通知されます。
* デフォルトですべての AAM セグメントが共有されるので、Analytics の顧客プロファイルが充実します。
* ソリューション管理者は、ユーザーインターフェイスから統合を有効にすることができ、コードの変更は最小限で済みます。
* Audience Manager のデータエクスポートコントロールに準拠するセグメントのみが共有されます。

## 仕組み {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. デジタルプロパティに訪問者が訪問するたびに、ヒットが収集されて Analytics に送信されます。
1.  [サーバー側転送](/help/admin/admin/c-server-side-forwarding/ssf.md)では、Analytics が受け取った各ヒットが AAM にリアルタイムで自動的に送信されます。
1. Audience Analytics 統合を通じて、各ヒットについて訪問者のオーディエンスメンバーシップが AAM で検索され、リアルタイムで処理するためにセグメント ID のリストが Analytics に返されます。

AAM セグメントは同じヒットごとに挿入されるので、AAM で使用可能な訪問者に関するどのデータも欠落することなく、ヒットに対して最新の状態が保たれます。AppMeasurement プラグインでは、これらのセグメントを次のヒットでのみ使用できます（現在のヒットでは使用できません）。Analytics データ収集は、この点で AppMeasurement プラグインより優れています。

また、AAM セグメント ID はわかりやすい名前に自動的に分類されるので、Analytics レポートで英数字の ID を参照する必要はありません。

## 前提条件 {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

次の前提条件を満たしていることを確認します。

* Audience Manager と Adobe Analytics の両方のユーザーである。
* Audience Manager 管理者である。
* ID サービス v1.5 以降を使用している。
* AAM および Adobe Analytics レポートスイートが、[同じ Experience Cloud 組織にマッピングされている](https://docs.adobe.com/content/help/ja-JP/core-services/interface/about-core-services/report-suite-mapping.html)。
* [サーバー側転送](/help/admin/admin/c-server-side-forwarding/ssf.md)を使用していて、[Audience Management モジュール](https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html)（DIL コードなし） - AppMeasurement 1.5 以降を実装している。

これらの前提条件は、[Audience Analytics ワークフロー](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)に記載されています。
