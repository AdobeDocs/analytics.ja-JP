---
description: Adobe Analyticsに関する一般的な概要情報（Analytics インターフェイスに関する情報や、管理者、アナリスト、ユーザーおよび開発者向けの入門情報を含む）です。
title: 管理者、アナリスト、エンドユーザーおよび開発者向けの基本を学ぶ
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: f23e0c74072d38d5c6559288b2ced60d98634fac
workflow-type: tm+mt
source-wordcount: '1812'
ht-degree: 34%

---

# 管理者、アナリスト、エンドユーザーおよび開発者向けの基本を学ぶ

一般的な組織には、管理者、アナリスト、エンドユーザーの 3 種類のAdobe Analyticsユーザーがあります。

管理者はAdobe Analyticsを実装および設定します。アナリストはAnalysis Workspaceを使用してプロジェクトを設定し分析を作成し、エンドユーザーは独自の分析を作成するか、アナリストと協力して顧客に関する実用的なインサイトを得ます。

以下の情報では、各ユーザーがAdobe Analyticsを使い始める方法の概要を説明します。

## はじめに（管理者向け）

Analytics 管理者は、組織に最も適した実装方法を選択する責任を負います。

Adobe Analyticsの実装後、管理者は様々な設定タスクを実行して、アナリストやエンドユーザーがAdobe Analyticsを最大限に活用できるようにする必要があります。 また、管理者は、Analytics 環境を定期的に監視して、システムが効率的に動作しているかを確認する必要があります。

### 収集するデータのタイプの決定

Adobe Analyticsでは、複数のチャネルタイプからデータを収集し、統合して、意味のあるリアルタイムの顧客インサイトを提供できます。

データを収集できるサポート対象チャネルの一部を次に示します。

* 携帯電話

* 物のインターネット

* TV

* 音声アシスタント

* 接続車

* その他（新しくサポートされるチャネルが定期的に追加される）

The [実装方法](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ja) 収集できるデータのタイプを選択します。

### Adobe Analytics の実装

Web サイトやモバイルアプリにAdobe Analyticsを実装する場合、様々な実装方法を使用できます。

使用可能な各メソッドについて詳しくは、 [Adobe Analyticsの実装](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ja).

| | 実装方法 |
|---------|---------|
| **Web サイト** | <ul><li>Web SDK 拡張機能（推奨）</li><li>Web SDK</li><li>Analytics 拡張機能</li><li>レガシー JavaScript</li></ul> |
| **モバイルアプリ** | <ul><li>Mobile SDK 拡張機能（推奨）</li><li>Analytics 拡張機能</li></ul> |

{style="table-layout:auto"}

### Adobe Analyticsの設定

Analytics 管理者は、組織内のユーザーがAdobe Analyticsを使用できるようにする前に、次の作業を実行する必要があります。

| タスク | 使用目的 | 詳細情報 |
|---------|----------|---------|
| 管理者の役割を定義する | Adobe Analyticsは、様々な種類の管理者をサポートしています | [Adobe Analytics の管理者の役割](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| 権限の定義 | Analytics 管理者は、Adobe Analytics、レポートスイートツールおよび Analytics ツール用のAdmin Consoleで製品プロファイルを割り当てる必要があります。 | [Admin Console での Analytics 権限](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=ja) |
| レポートスイートの設定と会社の設定の定義 | レポートスイートは、Adobe Analyticsがレポートの生成に使用するデータのサイロです。<p>管理者が [仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ja) を追加して、さらにセグメントデータを取得します。</p> | <ul><li>[レポートスイートの作成](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[カンパニー設定の概要](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| データのインポート | Adobe Analyticsのデータソースを使用すると、追加のオンラインまたはオフラインデータをレポート用にインポートできます。 | [データソースの概要](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| 分類でデータを分類する | 分類を使用すると、変数をより有効に利用するためにデータを分類でき、1 つの変数により多くのコンテンツを含めることができます。 | |
| コンポーネントの管理 | 各コンポーネントタイプのデータディクショナリと管理領域を使用して、Analytics の実装で使用可能なコンポーネント、および組織で承認されるコンポーネントを定義します。<p>これは、組織内でコンポーネントが効果的に使用されるようにする継続的なアクティビティです。 </p> | <ul><li>[データ要素の概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=ja)</li><li>[計算指標マネージャー](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[セグメントの管理](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=ja)</li><li>[Analysis Workspace でカスタム日付範囲を作成](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=ja)</li></ul> |
| 異常値の検出 | 異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。 | [異常値検出の概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=ja) |
| 貢献度分析 | 貢献度分析は、選択した指標の統計的な異常値を自動で発見し、予期せぬ顧客の行動や範囲外の値、特定セグメントにおける特定指標の突然の上昇や下降など、相関する原因を特定することで、データ内の隠れたパターンを発見するための機能です。 | [貢献度分析のトークン - 概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=ja) |
| Analytics のセグメント化 | Analytics 機能、Adobe Experience Cloud、Adobe Targetおよびその他の統合Adobe製品を使用して、強力で重要な閲覧者セグメントを作成、管理、共有し、レポートに適用できます。 | [Analytics のセグメント化](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=ja) |
| オーディエンスをAudience Managerに公開 | | |
| 統合 | Adobe Analyticsの他のアプリケーションから情報を表示できます。 <p>一般的な統合を以下に示します。</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=ja">Media Analytics</a></li> | |

{style="table-layout:auto"}

### Adobe Analyticsの監視

Adobe Analytics環境の監視に役立つ様々な機能が利用できます。

Analytics 管理者は、Analytics 環境の重要な側面を監視するのに役立つ、以下の機能について認識しておく必要があります。

| タスク | 使用目的 | 詳細情報 |
|---------|----------|---------|
| レポートアクティビティマネージャー | レポートアクティビティマネージャーでは、組織内の各レポートスイートのレポート処理能力を確認できます。レポート消費に関する詳細な可視性を提供し、ピーク時のレポート作成時に容量の問題を簡単に診断および修正できます。 | [レポートアクティビティマネージャー](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| サーバーコールの使用状況 | 「ヒット」または「イメージリクエスト」とも呼ばれます。処理するデータをアドビのサーバーに送信するインスタンスです。サーバーコールの使用状況ダッシュボードを使用して、サーバーコールの使用状況データを追跡し、契約上の制限と比較できます。 超過使用を防ぐためにアラートを設定できます。 | [サーバーコールの使用状況の概要](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| ログファイル | ユーザーがログインした時間、ユーザーの使用量、アクセス、レポートスイート、管理者による変更を確認するのに役立つログファイルです。 | [ログ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=ja) |

{style="table-layout:auto"}

## アナリスト向けの基礎知識

組織内の誰でもAdobe Analyticsを使用して、Web サイトやアプリをまたいだ顧客の行動に関する実用的なインサイトを得ることができますが、Adobe Analyticsはデータアナリストを念頭に置いて設計されています。

Adobe AnalyticsとAnalysis Workspaceの機能を最大限に活用するためにアナリストが理解しておくべき主なタスクと機能を次に示します。

| 機能 | 使用目的 | 詳細情報 |
|---------|----------|---------|
| Analysis Workspaceでプロジェクトをビルドおよび共有する | Analysis Workspace は分析をすばやく構築してインサイトを共有できる、柔軟なブラウザーツールです。ドラッグ&amp;ドロップのインターフェイスを使用して、分析の作成、ビジュアライゼーションの追加を行い、データを活用、データセットをキュレーション、組織内の任意のユーザーとプロジェクトを共有およびスケジュールできます。<p>データアナリストは、多くの場合、組織内のユーザー向けにAnalysis Workspaceでプロジェクトを作成します。</p><p>プロジェクトを作成した後、アナリストはこれらのプロジェクトを [エンドユーザー](#end-users)（非アナリスト）データを要求し、データの解釈方法を理解するのに役立つ組織内。</p> | <ul><li>[プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| アトリビューション | アナリストは、Analysis Workspaceで様々なアトリビューションモデルとルックバックウィンドウを使用して、ディメンション項目が成功イベントのクレジットを取得する方法をカスタマイズできます。<p>線形アトリビューションモデルでは、コンバージョンに至るすべてのタッチポイントに同等のクレジットが与えられ、ファーストタッチでは、ファーストタッチポイントにフルクレジットが与えられます。 他の多くのアトリビューションモデルが使用可能です。これには、統計的手法を使用してクレジットの最適な配分を動的に決定するアルゴリズムモデルが含まれます。 </p> | [アトリビューションモデルとルックバックウィンドウ](/help/analyze/analysis-workspace/attribution/models.md) |
| 異常値の検出 | Analysis Workspaceの統計モデリングでは、指標を分析し、値の下限、上限、期待される範囲を決定することで、データ内の予期しないトレンドを自動的に見つけます。 予期しないスパイクまたは下落が発生した場合にレポートします。 | [異常値検出の概要](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| 貢献度分析 | Analysis Workspaceを使用して、統計的異常値を説明し、オーディエンスセグメント間の指標に関する予期しない顧客行動、範囲外の値、急激なスパイクや急激な下降の背後にある相関関係を特定します。 | [貢献度分析のトークン - 概要](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| インテリジェントアラート | 1 つのアラートで複数の指標を示すデータの異常値および「積み重ね」アラートに基づいて、アラートを作成および管理します。 | [インテリジェントアラートの概要](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| データの書き出し | Data Warehouseおよびデータフィードを使用すると、Google Cloud Platform、Azure RBAC、Azure SAS、Amazon S3 など、様々なクラウドの宛先にデータを書き出すことができます。 | [Analytics 書き出しガイド](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=ja) |
| Activity Map | Activity Map は Adobe Analytics のアプリケーションであり、視覚的なオーバーレイを使用してリンクアクティビティをランク付けし、Web ページに対するオーディエンスのエンゲージメントを監視するリアルタイム分析のダッシュボードを提供するよう設計されています。<p>Activity Map を使用すると、様々なビューを設定することにより、顧客アクティビティの増加を視覚的に特定し、マーケティングイニシアチブを数量化して、オーディエンスのニーズや行動に合わせて対応することができます。</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=ja) |
| Report Builder | Report Builder は Microsoft Excel のアドインです。Report Builder を使用すると、Excel ワークシートに挿入された Adobe Analytics データからカスタマイズしたリクエストを作成できます。リクエストはセルから動的に参照できます。さらに、Report Builder によるデータの表示形式は更新やカスタマイズが可能です。 | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=ja) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## はじめに（エンドユーザー向け）

プロフェッショナルなアナリストでないエンドユーザーは、組織内のアナリストと協力してAdobe AnalyticsとAnalysis Workspaceの最大限の力を活用したり、Analysis Workspaceの基本を学んで顧客に関する実用的なインサイトを得たりできます。

### アナリストとの連携

通常、様々なサイトにわたる顧客の行動に関する詳細を学びたいと考えている組織のユーザーは、専門的なアナリストではありません。

理想的には、これらのユーザーは [アナリスト](#analysts) 組織内で次の操作をおこないます。

1. 分析の要件を定義するには、顧客について学びたいことをアナリストに説明します。

1. 分析をレビューし、目標を満たしていることを確認します。

1. 分析から得られたデータについて話し合います。

1. 必要に応じて、解析を時間の経過と共に変更します。

### Analysis Workspaceでの分析の作成

Adobe Analyticsから実用的なインサイトを得るために、データアナリストである必要はありません。

一部のユーザーは、データアナリストと協力して、 Analysis Workspaceでプロジェクトを設定し、データの解釈方法を説明すると便利です。詳しくは、 [アナリストとの連携](#work-with-analysts)を使用すると、他のユーザーも、プロジェクトの構築やデータ自体の解釈に慣れている場合があります。

Analysis Workspace では、分析をすばやく作成してインサイトを収集し、他のユーザーと共有できます。ドラッグ＆ドロップのブラウザーインターフェイスを使用して、分析の作成、データを活用するためのビジュアライゼーションの追加、データセットのキュレーション、選択した任意のユーザーとのプロジェクトの共有とスケジュールを行うことができます。

Analysis Workspaceで分析を作成する方法について詳しくは、 [Analysis Workspaceの概要](/help/analyze/analysis-workspace/home.md).

## 開発者向け入門ガイド

[Analytics API を使用すると、アドビのサーバーを直接呼び出し、ユーザーインターフェイスで実行できるほぼすべてのアクションを実行できます。](https://developer.adobe.com/analytics-apis/docs/2.0/)

レポートを作成して、データに関する重要な質問を調べたり、インサイトを得たり、回答したりすることができます。また、セグメントや計算指標の作成など、Adobe Analytics のコンポーネントを管理することもできます。