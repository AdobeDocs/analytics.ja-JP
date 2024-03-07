---
description: Analytics インターフェイスに関する情報や、管理者、アナリスト、ユーザー、開発者向けの基本を学ぶ情報など、Adobe Analytics に関する一般的な概要情報です。
title: 管理者、アナリスト、エンドユーザーおよび開発者向けの基本を学ぶ
feature: Analytics Basics
exl-id: 11800de5-224a-4bd2-8cb1-a6318925db71
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '1691'
ht-degree: 99%

---

# 管理者、アナリスト、エンドユーザーおよび開発者向けの基本を学ぶ

一般的な組織には、次の 4 つのタイプの Adobe Analytics ユーザーがいます。

* **管理者：** Adobe Analytics を実装して設定します。

* **アナリスト：** Analysis Workspace を使用してプロジェクトを設定し、分析を作成します

* **エンドユーザー：**&#x200B;独自の分析を作成するか、アナリストと協力して分析を作成することにより、顧客に関する実用的なインサイトを取得します。

* **開発者：** Adobe Analytics 2.0 API を使用してアドビのサーバーを直接呼び出し、調査するレポートの作成、インサイトの取得、データに関する重要な質問への回答など、ユーザーインターフェイスで実行できるほとんどのアクションを実行します。

以下の情報は、これらの各ユーザーが Adobe Analytics の基本を学ぶ方法の概要を示しています。

## 管理者向けの基本を学ぶ

Analytics 管理者は、組織に最も適した実装方法を選択する責任があります。

Adobe Analytics を実装した後、管理者は様々な設定タスクを実行して、アナリストとエンドユーザーが Adobe Analytics の価値を最大限に活用できるようにする必要があります。また、管理者は Analytics 環境を定期的に監視して、システムが効率的に実行されていることを確認する必要があります。

### 収集するデータのタイプを決定

Adobe Analytics を使用すると、複数のチャネルタイプからデータを収集し、統合して、意味のあるリアルタイムの顧客インサイトを提供できます。

データを収集可能な、サポートされているチャネルの一部を以下に示します。

* 携帯電話

* IoT（モノのインターネット）

* TV

* 音声アシスタント

* コネクテッドカー

* その他（新しくサポートされるチャネルは定期的に追加されます）

選択した[実装方法](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ja)によって、収集できるデータのタイプが決定します。

### Adobe Analytics の実装

Adobe Analytics を web サイトやモバイルアプリに実装する場合は、様々な実装方法を使用できます。

使用可能な各方法について詳しくは、[Adobe Analytics の実装](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ja)を参照してください。

| | 実装方法 |
|---------|---------|
| **Web サイト** | <ul><li>Web SDK 拡張機能（推奨）</li><li>Web SDK</li><li>Analytics 拡張機能</li><li>レガシー JavaScript</li></ul> |
| **モバイルアプリ** | <ul><li>Mobile SDK 拡張機能（推奨）</li><li>Analytics 拡張機能</li></ul> |

{style="table-layout:auto"}

### Adobe Analytics の設定

Analytics 管理者は、組織内のユーザーが Adobe Analytics を使用できるようにする前に、次のタスクを完了する必要があります。

| タスク | 使用目的 | 詳細情報 |
|---------|----------|---------|
| 管理者の役割の定義 | Adobe Analytics は、様々なタイプの管理者をサポートします。 | [Adobe Analytics の管理者の役割](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html) |
| 権限を定義 | Analytics 管理者は、Admin Console で Adobe Analytics、レポートスイートツールおよび Analytics ツールの製品プロファイルを割り当てる必要があります。 | [Admin Console での Analytics 権限](/help/admin/admin-console/permissions/analytics-tools.md) |
| レポートスイートの設定とカンパニー設定の定義 | レポートスイートは、Adobe Analytics がレポートの生成に使用するデータのサイロです。<p>また、管理者は、[仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ja)を設定して、データをさらにセグメント化することもできます。</p> | <ul><li>[レポートスイートを作成](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=ja)</li><li>[カンパニー設定の概要](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html)</li></ul> |
| データの読み込み | Adobe Analytics データソースを使用すると、追加のオンラインまたはオフラインデータをレポート用に読み込むことができます。 | [データソースの概要](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html) |
| 分類を使用してデータを仕分ける | 分類を使用すると、データを仕分けて変数を有効に活用できるので、より多くのコンテンツを 1 つの変数に含めることができます。 | [分類の概要](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=ja) |
| コンポーネントの管理 | 各コンポーネントタイプのデータ要素と管理領域を使用して、Analytics の実装で使用可能なコンポーネントと組織で承認されるコンポーネントを定義します。<p>コンポーネントが組織内で効果的に使用されていることを確認するには、これを継続的なアクティビティにする必要があります。 </p> | <ul><li>[データ要素の概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html)</li><li>[計算指標マネージャー](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=ja)</li><li>[セグメントを管理](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=ja)</li><li>[Analysis Workspace でカスタム日付範囲を作成](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=ja)</li></ul> |
| 異常値の検出 | 異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。 | [異常値検出の概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=ja) |
| 貢献度分析 | 貢献度分析は、選択した指標の統計的な異常値を自動で発見し、予期せぬ顧客の行動や範囲外の値、特定セグメントにおける特定指標の突然の上昇や下降など、相関する原因を特定することで、データ内の隠れたパターンを発見するための機能です。 | [貢献度分析のトークン - 概要](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| Analytics のセグメント化 | Analytics 機能、Adobe Experience Cloud、Adobe Target および統合された他の Adobe 製品を使用して、強力かつ重要なオーディエンスセグメントを作成、管理、共有し、レポートに適用できます。 | [Analytics のセグメント化](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=ja) |
| Audience Manager へオーディエンスを公開 | Adobe Audience Manager は、ファーストパーティ、セカンドパーティ（パートナー）、サードパーティのデータ統合から一意のオーディエンスプロファイルを作成するのに役立つ強力なデータ管理プラットフォームです。 | [Audience Analytics の概要](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| 統合 | Adobe Analytics では、他のアプリケーションからの情報を表示できます。 <p>一般的な統合を以下に示します。</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=ja">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=ja">Media Analytics</a></li> | [Analytics の統合](https://experienceleague.adobe.com/docs/analytics/integration/home.html?lang=ja) |

{style="table-layout:auto"}

### Adobe Analytics を監視

Adobe Analytics 環境の監視に役立つ様々な機能を使用できます。

Analytics 管理者は、Analytics 環境の重要な側面の監視に役立つ以下の機能を認識しておく必要があります。

| タスク | 使用目的 | 詳細情報 |
|---------|----------|---------|
| レポートアクティビティマネージャー | レポートアクティビティマネージャーでは、組織内の各レポートスイートのレポート処理能力を確認できます。レポートの使用状況を詳細に把握し、ピーク時のレポート作成時の処理能力に関する問題を簡単に診断および修正できます。 | [レポートアクティビティマネージャー](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html) |
| サーバーコールの使用状況 | 「ヒット」または「イメージリクエスト」とも呼ばれます。処理するデータをアドビのサーバーに送信するインスタンスです。サーバーコールの使用状況ダッシュボードを使用して、サーバーコールの使用状況データを追跡し、契約上の制限と比較できます。超過を防ぐためにアラートを設定できます。 | [サーバーコールの使用状況の概要](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html) |
| ログファイル | ユーザーがログインした時間、ユーザーの使用量、アクセス、レポートスイート、管理者による変更を確認するのに役立つログファイルです。 | [ログ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html) |

{style="table-layout:auto"}

## マーケター向けの基本を学ぶ

組織内のすべてのユーザーが Adobe Analytics を使用して、web サイトやアプリ全体にわたる顧客の行動に関する実用的なインサイトを取得できますが、Adobe Analytics はデータアナリストを念頭に置いて設計されています。

Adobe Analytics と Analysis Workspace の機能を最大限に活用するために、アナリストが理解しておく必要がある主なタスクと機能を以下に示します。

| 機能 | 使用目的 | 詳細情報 |
|---------|----------|---------|
| Analysis Workspace でのプロジェクトの作成と共有 | Analysis Workspace は分析をすばやく構築してインサイトを共有できる、柔軟なブラウザーツールです。ドラッグ&amp;ドロップのインターフェイスを使用して、分析の作成、ビジュアライゼーションの追加を行い、データを活用、データセットをキュレーション、組織内の任意のユーザーとプロジェクトを共有およびスケジュールできます。<p>データアナリストは多くの場合、組織内のユーザー向けに Analysis Workspace でプロジェクトを作成する責任を負います。</p><p>プロジェクトを作成した後、アナリストは、データをリクエストした組織内の[エンドユーザー](#end-users)（非アナリスト）とこれらのプロジェクトを共有し、データの解釈方法を理解できるようにサポートします。</p> | <ul><li>[プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| アトリビューション | アナリストは、Analysis Workspace の様々なアトリビューションモデルとルックバックウィンドウを使用して、ディメンション項目で成功イベントのクレジットを取得する方法をカスタマイズできます。<p>線形アトリビューションモデルでは、コンバージョンに至るまでのすべてのタッチポイントに同等のクレジットが与えられますが、ファーストタッチでは最初のタッチポイントに完全なクレジットが与えられます。統計的手法を使用してクレジットの最適な配分を動的に決定するアルゴリズムモデルなど、他にも多くのアトリビューションモデルが使用可能です。 </p> | [アトリビューションモデルとルックバックウィンドウ](/help/analyze/analysis-workspace/attribution/models.md) |
| 異常値の検出 | Analysis Workspace の統計的モデリングでは、指標を分析し、値の下限、上限および予想される範囲を決定することで、データ内の予期しないトレンドを自動的に検出します。予期しないスパイクまたは下落が発生した場合にレポートします。 | [異常値検出の概要](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| 貢献度分析 | Analysis Workspace を使用して、データ内の非表示パターンを発見して統計的な異常値を明らかにし、予期しない顧客のアクション、範囲外の値、オーディエンスセグメント全体の指標の突然のスパイクや下落の背後にある相関関係を特定します。 | [異常値検出の概要](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)の[貢献度分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| インテリジェントアラート | データの異常値と、単一のアラートで複数の指標をキャプチャする「積み重ね」アラートに基づいてアラートを作成および管理します。 | [インテリジェントアラートの概要](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| データの書き出し | Data Warehouse とデータフィードを使用すると、Google Cloud Platform、Azure RBAC、Azure SAS、Amazon S3 などの様々なクラウドの宛先にデータを書き出すことができます。 | [Analytics 書き出しガイド](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=ja) |
| Activity Map | Activity Map は Adobe Analytics のアプリケーションであり、視覚的なオーバーレイを使用してリンクアクティビティをランク付けし、Web ページに対するオーディエンスのエンゲージメントを監視するリアルタイム分析のダッシュボードを提供するよう設計されています。<p>Activity Map を使用すると、様々なビューを設定することにより、顧客アクティビティの増加を視覚的に特定し、マーケティングイニシアチブを数量化して、オーディエンスのニーズや行動に合わせて対応することができます。</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=ja) |
| Report Builder | Report Builder は Microsoft Excel のアドインです。Report Builder を使用すると、Excel ワークシートに挿入された Adobe Analytics データからカスタマイズしたリクエストを作成できます。リクエストはセルから動的に参照できます。さらに、Report Builder によるデータの表示形式は更新やカスタマイズが可能です。 | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=ja) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## エンドユーザー向けの基本を学ぶ

プロフェッショナルなアナリストではないエンドユーザーは、組織内のアナリストと連携して Adobe Analytics と Analysis Workspace の機能を最大限に活用できます。または、顧客に関する実用的なインサイトを取得するために、Analytics Workspace の基本を学ぶこともできます。

### アナリストとの連携

通常、様々なサイトにわたる顧客の行動について詳しく知りたいと考えている組織内のユーザーは、プロフェッショナルなアナリストではありません。

理想的には、これらのユーザーは組織内の[アナリスト](#analysts)と連携して以下を行う必要があります。

1. 顧客について知りたい情報をアナリストに説明して、分析の要件を定義します。

1. 分析をレビューし、目標を満たしていることを確認します。

1. 分析から取得したデータについて説明します。

1. 必要に応じて、分析を時間の経過と共に変更します。

### Analysis Workspace での分析の作成

Adobe Analytics から実用的なインサイトを取得するために、データアナリストである必要はありません。

ユーザーによっては、[アナリストとの連携](#work-with-analysts)で説明しているように、データアナリストと連携して Analysis Workspace でプロジェクトを設定し、データの解釈方法を説明すると役立つと感じる場合があります。他のユーザーは、自分たちでプロジェクトを作成してデータを解釈することに慣れている場合があります。

Analysis Workspace では、分析をすばやく作成してインサイトを収集し、他のユーザーと共有できます。ドラッグ＆ドロップのブラウザーインターフェイスを使用して、分析の作成、データを活用するためのビジュアライゼーションの追加、データセットのキュレーション、選択した任意のユーザーとのプロジェクトの共有とスケジュールを行うことができます。

Analysis Workspace で分析を作成する方法について詳しくは、[Analysis Workspace の概要](/help/analyze/analysis-workspace/home.md)を参照してください。

## 開発者向けの基本を学ぶ

[Analytics API を使用すると、アドビのサーバーを直接呼び出し、ユーザーインターフェイスで実行できるほぼすべてのアクションを実行できます。](https://developer.adobe.com/analytics-apis/docs/2.0/)

レポートを作成して、データに関する重要な質問を調べたり、インサイトを得たり、回答したりすることができます。また、セグメントや計算指標の作成など、Adobe Analytics のコンポーネントを管理することもできます。
