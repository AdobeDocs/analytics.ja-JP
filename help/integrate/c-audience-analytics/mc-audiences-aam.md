---
description: Adobe Audience Manager（Adobe Audience Manager）は、ファーストパーティ、セカンドパーティ/パートナー、サードパーティのデータ統合から独自のオーディエンスプロファイルを作成するのに役立つ、強力なデータ管理プラットフォームです。 広告主の場合、これらのオーディエンスプロファイルは、あらゆるデジタルチャネルにわたって使用する最も価値のあるセグメントを定義するのに役立ちます。
solution: Experience Cloud
title: Audience Analytics の概要
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 9%

---

# Audience Analytics の概要

Adobe Audience Manager（Adobe Audience Manager）は、ファーストパーティ、セカンドパーティ/パートナー、サードパーティのデータ統合から独自のオーディエンスプロファイルを作成するのに役立つ、強力なデータ管理プラットフォームです。 広告主の場合、これらのオーディエンスプロファイルは、あらゆるデジタルチャネルにわたって使用する最も価値のあるセグメントを定義するのに役立ちます。

Audience Analyticsの統合を導入すると、人口統計情報（性別や収入レベルなど）、心理統計情報（興味や趣味など）、CRM データ、広告インプレッションデータなどのAdobe Audience Manager オーディエンスデータを任意の Analytics ワークフローに組み込むことができます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/audience-manager/audience-analytics-integrate-aam-segments-into-analytics){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## 主なメリット  {#benefits}

Audience Analyticsの統合には、次のような主なメリットがあります。

* Data Management Platform （DMP）と Analytics エンジンの製品化された統合としては、マーケットプレイスで初めてです。
* セグメントは、Adobe Audience Managerから Analytics にリアルタイムで共有され、オーディエンスの検出、セグメント化および最適化を知らせます。
* すべてのAdobe Audience Manager セグメントはデフォルトで共有され、Analytics で顧客プロファイルが完全に強化されます。
* ソリューション管理者は、最小限のコード変更で、ユーザーインターフェイスを通じて統合を有効にできます。
* Audience Manager データ書き出しのコントロールに準拠したセグメントのみが共有されます。

## Audience Analyticsの仕組み {#works}

![](assets/mc-aud-dataflow.png)

1. 訪問者がデジタルプロパティにアクセスするたびに、ヒットが収集され、Analytics に送信されます。
1. [ サーバーサイド転送 ](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md) を使用すると、Analytics が受け取る各ヒットがリアルタイムでAdobe Audience Managerに自動的に送信されます。
1. Audience Analytics統合を通じて、ヒットごとに、訪問者のオーディエンスメンバーシップがAdobe Audience Managerで検索され、セグメント ID のリストが Analytics に返されて、リアルタイムに処理されます。

Adobe Audience Manager セグメントは同じヒットに基づいて挿入されるので、訪問者に関してAdobe Audience Managerで利用できるすべてのデータが欠落することなく、そのヒットの最新の状態に保つことができます。 プラグインは現在のヒットではなく、次のヒットの際にのみこれらのセグメントを使用可能にできるので、これはAppMeasurement プラグインよりも優れています。

さらに、Analytics レポートで英数字の ID を確認する必要がないように、Adobe Audience Managerのセグメント ID がわかりやすい名前に自動的に分類されます。

## 前提条件 {#prerequisites}

次の前提条件が満たされていることを確認します。

* Audience ManagerとAdobe Analyticsの両方のお客様です。
* あなたはAudience Manager管理者です。
* ID サービス v1.5 以降を使用している。
* Adobe Audience ManagerおよびAdobe Analytics レポートスイートが、同じExperience Cloud組織にマッピングされている。
* [サーバー側転送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)を使用していて、[Audience Management モジュール](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=ja)（DIL コードなし） - AppMeasurement 1.5 以降を実装している。

これらの前提条件は、[Audience Analytics ワークフロー](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)に記載されています。
