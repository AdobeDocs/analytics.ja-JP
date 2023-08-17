---
description: Adobe Analyticsに関する一般的な概要情報
title: Adobe Analyticsの概要
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: 1c6cc23c9cb6b4b007d2f296ea23e697cc135bd4
workflow-type: tm+mt
source-wordcount: '3101'
ht-degree: 32%

---

# Adobe Analyticsの概要

Adobe Analyticsを使用すると、組織はデータを収集し、あらゆるデジタル顧客インタラクションから実用的なインサイトを得ることができます。 詳細な分析、汎用性の高いレポート作成、予測インテリジェンスにより、組織は顧客に対するより優れたエクスペリエンスを構築するために必要な洞察力に富んだ基盤を提供します。

## 主なメリット

次に、Adobe Analyticsが、顧客に対する貢献を促進するために組織が重要なインサイトを得るのに役立つ主な方法の一部を示します。

Adobe Analyticsのメリットについて詳しくは、 [Adobe Analytics製品ページ](https://business.adobe.com/products/analytics/adobe-analytics.html).

### Web 分析

Adobe Analyticsは、Web サイトトラフィックを分析するための次の複雑なセグメント化および予測ツールを提供します。

* [Analysis Workspaceでの Ad Hoc Analysis](/help/analyze/analysis-workspace/home.md)

* [フロー分析](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [高度なセグメント化](/https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)

### マーケティング分析

Adobe Analyticsは、顧客がブランドとどこでやり取りするか、顧客が好むチャネルやどのエクスペリエンスが共感を呼ぶかを把握するのに役立ちます。

Adobe Analyticsの次の主な機能は、これらのマーケティング機能を提供します。

* マルチチャネルデータの収集

* [オフラインデータの統合](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Analysis Workspaceでの Ad Hoc Analysis](/help/analyze/analysis-workspace/home.md)

### アトリビューション

アトリビューションを使用すると、組織は、カスタマージャーニー全体を通じて様々なインタラクションがコンバージョンに与える影響を確認できます。 Adobe Analyticsのアトリビューションは、線形モデルやファーストタッチモデルなど、より従来のアトリビューションオプションを提供するだけでなく、機械学習と高度な統計モデルを使用して、各タッチの正確な影響を把握します。

詳しくは、 [アトリビューションモデルとルックバックウィンドウ](/help/analyze/analysis-workspace/attribution/models.md).


### 予測分析

予測分析では、機械学習と高度な統計モデリングを使用して、顧客データの分析、パターンの検索、将来の行動（チャーンやコンバージョンの可能性など）の予測をおこないます。 これにより、データアナリストは、無駄になる可能性のある膨大なデータセットを活用できます。

Adobe Analyticsの次の主な機能は、次の予測機能を提供します。

* [異常値の検出](#anomaly-detection)

* [貢献度分析](#contribution-analysis)

* [インテリジェントアラート](#intelligent-alerts)

## Adobe Analytics使用の前提条件

Adobe Analyticsを使用する前に、次が必要です。

* 有効なAdobe Analyticsライセンス

  Adobe Analyticsにはサイトのライセンスが必要です。 詳しくは、Adobeアカウント担当者にお問い合わせください。 <!--is this phrased correctly? Is this important? -->

* サポートされているブラウザー

  Adobe Analyticsにアクセスする各ユーザーは、サポートされているブラウザーを使用する必要があります。 詳しくは、 [Adobe Analyticsの必要システム構成](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## Analytics インターフェイスについて

Adobe Analyticsインターフェイスは、次の主な領域で構成されています。

### 「ワークスペース」タブ

The [!UICONTROL Workspace] 「 」タブには、Analysis Workspaceプロジェクトのリストが表示されます。

1. Adobe Analyticsで、 [!UICONTROL **Workspace**] タブをクリックします。

   ![「ワークスペース」タブ](assets/landing-all2.png)

で使用できる機能の詳細については、 [!UICONTROL Workspace] タブ、詳しくは、 [Adobe Analytics Landing page](/help/analyze/landing.md).

### 「レポート」タブ

2023年12月31日（PT）をもって、アドビは Reports &amp; Analytics およびそれに付随するレポートと機能を廃止する予定です。

代わりに、 [!UICONTROL **レポート**] の左側のパネルの [!UICONTROL **Workspace**] タブをクリックします。 詳しくは、 *「レポート」タブに移動します。* in [Adobe Analytics Landing page](/help/analyze/landing.md).

### 「コンポーネント」タブ

The [!UICONTROL コンポーネント] タブには、データの分析を微調整したり、活用したりするのに役立つ機能が含まれています。

1. Adobe Analyticsで、 [!UICONTROL **コンポーネント**] 「 」タブで、「 [!UICONTROL **すべてのコンポーネント**].

   ![「ワークスペース」タブ](assets/components-tab.png)

2. 次の製品の機能のいずれかを選択して設定します。


   | 製品の機能 | 関数 | 詳細情報 |
   |---------|----------|----------|
   | セグメント  | Adobe Analytics では、Analytics 機能、Adobe Experience Cloud、Adobe Target および統合された他の Adobe 製品を使用して、強力かつ重要な閲覧者セグメントを構築、管理、共有し、レポートに適用できます。 | [Analytics のセグメント化](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=ja) |
   | 計算指標 | 計算指標および高度な計算（または派生）指標は、既存の指標から作成できるカスタム指標です。  マーケター、製品マネージャーおよびアナリストは、Analytics の実装を変更することなく、データを照会できます。 | [計算指標および高度な計算（派生）指標](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=ja) |
   | 日付範囲 | Analysis Workspaceには、分析の作成時にユーザーが使用できるデフォルト日付範囲のリストが含まれています。 また、カスタム日付範囲を作成して、Analysis Workspaceのユーザーが利用できるようにすることができます。 | [カスタム日付範囲を作成](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=ja) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | 仮想レポートスイート |  |  |
   | アラート | インテリジェントアラートでは、異常値検出とアラートシステムが統合され、アラートをより詳細に制御できます。 | [インテリジェントアラート](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | ターゲット | ターゲットでは、Web サイトのパフォーマンスを測定し、目標に対する達成度をトラッキングできます。ターゲットを作成する場合は、測定する属性指標や eVar を選択するか、選択した指標を使ってサイト全体を測定します。 <p>ターゲットは、Reports &amp; Analytics の一部です。 詳しくは、Reports &amp; Analytics の[提供終了のお知らせ](https://express.adobe.com/page/6WnF8JK6IRDhf/)を参照してください。</p> | [ターゲット](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | カレンダーイベント | 経時的にトレンドされたレポートでは、カレンダーイベントを使用すると、イベントを視覚的に表示し、キャンペーンなどのイベントがサイトへのトラフィック、売上高などの指標に影響を与えたかどうかを確認できます。 | [カレンダーイベント](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | 注釈 | Analysis Workspace の注釈を使用すると、コンテキストデータのニュアンスとインサイトを組織に効果的に伝えることができます。カレンダーイベントを特定のディメンションや指標に関連付けることができます。 | [注釈を管理](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | 分類セット | 分類セットは、分類とルールを管理するための単一のインターフェイスを提供します。 <p>分類とは、Analytics 変数データをカテゴリーにまとめ、レポートを生成する際に様々な方法でデータを表示する手法です。変数値と、その値に関連するメタデータとの間に関係を確立します。 分類は、トラッキングコード、prop、eVar など、ほとんどのカスタムディメンションで使用できます。</p> | [分類セットの概要](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=ja) |
   | 場所 | クラウドの宛先からAdobe Analytics分類データを読み込むには、まず分類データを収集する場所を追加して設定する必要があります。 ロケーションは、作成、編集または削除できます。 | [場所マネージャー](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | スケジュールされたプロジェクト | スケジュール済みプロジェクトを管理する場合、定期的なプロジェクトスケジュールを編集および削除できます。また、検索バーで、または左側のパネルのフィルターオプションを使用してスケジュールを検索し、タグ、承認済みスケジュール、所有者などでフィルタリングできます。 | [スケジュールされたプロジェクト](/help/components/scheduled-projects-manager.md) |
   | ブックマーク | ブックマークを使用すると、よく使用するレポートにすばやくアクセスできます。作成したブックマークは、Experience Cloud に保存され、Data Connectors などの統合機能で使用できます。 <p>ブックマークは Reports &amp; Analytics に含まれています。 詳しくは、Reports &amp; Analytics の[提供終了のお知らせ](https://express.adobe.com/page/6WnF8JK6IRDhf/)を参照してください。 | [ブックマークマネージャー](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | ダッシュボード | 指標を視覚化し、データを使用してインタラクティブな分析機能を提供するダッシュボードが作成されます。 ダッシュボード内の項目をクリックすると、データを迅速かつ容易にセグメント化して、分析から情報を引き出すことができます。 <p>ダッシュボードはData Workbenchの一部です。 Data Workbench [提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [ダッシュボードマネージャー](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | 予定レポート | 管理者レベルのユーザーは、組織全体で予定レポートの表示と管理をおこなうことができます。 | [予定レポートキュー](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | レポート設定 | これらの設定は、従来のAdobe Analytics製品を指します。Analysis Workspaceとその関連コンポーネントは除きます。 Analysis Workspaceの設定を調整するには、コンポーネント/環境設定に移動します。 |  |
   | 環境設定 | 作成するすべての新規プロジェクトまたはパネルに関する、Analysis Workspaceおよびその関連コンポーネントの設定を管理します。 既存のプロジェクトやパネルは影響を受けません。 | [環境設定](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

### 「概要」タブ

「ツール」タブ

1. Adobe Analyticsで、 [!UICONTROL **ツール**] 「 」タブで、「 [!UICONTROL **すべてのツール**].

   ![「ワークスペース」タブ](assets/tools-tab.png)

2. 次の製品の機能のいずれかを選択して設定します。

   | 製品の機能 | 関数 | 詳細情報 |
   |---------|----------|----------|
   | Data Warehouse | Data Warehouse は、データをフィルタリングして、保存用およびカスタムレポート用の Analytics データのコピーを参照できます。 <p>リクエストマネージャーを使用して、リクエストの表示、複製、優先順位の再設定をおこなうことができます。</p> | [Data Warehouse リクエストの管理](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | Activity Mapは、視覚的なオーバーレイを使用してリンクアクティビティをランク付けし、Web ページのオーディエンスのエンゲージメントを監視するためのリアルタイム分析のダッシュボードを提供するように設計されています。 様々なビューを設定して、顧客アクティビティの加速度を視覚的に特定し、マーケティングイニシアチブを数量化して、オーディエンスのニーズや行動に合わせて対応できます。 | [Activity Map の概要](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=ja) |
   | Recommendations Classic |  |  |
   | Search&amp;Promote |  |  |
   | Mobile Services |  |  |
   | Analytics ダッシュボード（モバイルアプリ） |  |  |
   | Report Builder |  |  |

   {style="table-layout:auto"}

### 「管理者」タブ

「管理者」タブ

1. Adobe Analyticsで、 [!UICONTROL **管理者**] 「 」タブで、「 [!UICONTROL **すべての管理者**].

   ![「ワークスペース」タブ](assets/admin-tab.png)

## 管理者、アナリストおよびエンドユーザー向けの基本を学ぶ

一般的な組織には、管理者、アナリスト、エンドユーザーの 3 種類のAdobe Analyticsユーザーがあります。

管理者はAdobe Analyticsを実装および設定します。アナリストはAnalysis Workspaceを使用してプロジェクトを設定し分析を作成し、エンドユーザーは独自の分析を作成するか、アナリストと協力して顧客に関する実用的なインサイトを得ます。

以下の節で、これらの各ユーザーがAdobe Analyticsを使い始める方法を説明します。

### はじめに（管理者向け）

Analytics 管理者は、組織に最も適した実装方法を選択する責任を負います。

Adobe Analyticsの実装後、管理者は様々な設定タスクを実行して、アナリストやエンドユーザーがAdobe Analyticsを最大限に活用できるようにする必要があります。

#### 収集するデータのタイプの決定

Adobe Analyticsでは、複数のチャネルタイプからデータを収集し、統合して、意味のあるリアルタイムの顧客インサイトを提供できます。

データを収集できるサポート対象チャネルの一部を次に示します。

* 携帯電話

* 物のインターネット

* TV

* 音声アシスタント

* 接続車

* その他（新しくサポートされるチャネルが定期的に追加される）

The [実装方法](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ja) 収集できるデータのタイプを選択します。

#### Adobe Analytics の実装

Web サイトやモバイルアプリにAdobe Analyticsを実装する場合、様々な実装方法を使用できます。

使用可能な各メソッドについて詳しくは、 [Adobe Analyticsの実装](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=ja).

| | 実装方法 |
|---------|---------|
| **Web サイト** | <ul><li>Web SDK 拡張機能（推奨）</li><li>Web SDK</li><li>Analytics 拡張機能</li><li>レガシー JavaScript</li></ul> |
| **モバイルアプリ** | <ul><li>Mobile SDK 拡張機能（推奨）</li><li>Analytics 拡張機能</li></ul> |

{style="table-layout:auto"}

#### Adobe Analyticsの設定

Analytics 管理者は、組織内のユーザーがAdobe Analyticsを使用できるようにする前に、次の作業を実行する必要があります。

| タスク | 使用目的 | 詳細情報 |
|---------|----------|---------|
| 管理者の役割を定義する | Adobe Analyticsは、様々な種類の管理者をサポートしています | [Adobe Analytics の管理者の役割](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| 権限の定義 | Analytics 管理者は、Adobe Analytics、レポートスイートツールおよび Analytics ツール用のAdmin Consoleで製品プロファイルを割り当てる必要があります。 | [Admin Console での Analytics 権限](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=ja) |
| レポートスイートの設定と会社の設定の定義 | レポートスイートは、Adobe Analyticsがレポートの生成に使用するデータのサイロです。<p>管理者が [仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=ja) を追加して、さらにセグメントデータを取得します。</p> | <ul><li>[レポートスイートの作成](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[カンパニー設定の概要](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| データのインポート | Adobe Analyticsのデータソースを使用すると、追加のオンラインまたはオフラインデータをレポート用にインポートできます。 | [データソースの概要](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| 分類でデータを分類する | 分類を使用すると、変数をより有効に利用するためにデータを分類でき、1 つの変数により多くのコンテンツを含めることができます。 | |
| コンポーネントの管理 | 各コンポーネントタイプのデータディクショナリと管理領域を使用して、Analytics の実装で使用可能なコンポーネント、および組織で承認されるコンポーネントを定義します。<p>これは、組織内でコンポーネントが効果的に使用されるようにする継続的なアクティビティです。 </p> | <ul><li>[データ要素の概要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=ja)</li><li>[計算指標マネージャー](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[セグメントの管理](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=ja)</li><li>[Analysis Workspace でカスタム日付範囲を作成](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=ja)</li></ul> |
| 異常値検出と貢献度分析 | | |
| 高度なセグメント化 | | |
| オーディエンスをAudience Managerに公開 | | |
| アトリビューション | | |
| レポートアクティビティマネージャー | | |
| 統合 | Adobe Analyticsの他のアプリケーションから情報を表示できます。 <p>一般的な統合を以下に示します。</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=ja">Media Analytics</a></li> | |

{style="table-layout:auto"}

### アナリスト向けの基礎知識

組織内の誰でもAdobe Analyticsを使用して、Web サイトやアプリをまたいだ顧客の行動に関する実用的なインサイトを得ることができますが、Adobe Analyticsはデータアナリストを念頭に置いて設計されています。

Adobe AnalyticsとAnalysis Workspaceの機能を最大限に活用するためにアナリストが理解しておくべき主なタスクと機能を次に示します。

| 機能 | 使用目的 | 詳細情報 |
|---------|----------|---------|
| Analysis Workspaceでプロジェクトをビルドおよび共有する | Analysis Workspace は分析をすばやく構築してインサイトを共有できる、柔軟なブラウザーツールです。ドラッグ&amp;ドロップのインターフェイスを使用して、分析の作成、ビジュアライゼーションの追加を行い、データを活用、データセットをキュレーション、組織内の任意のユーザーとプロジェクトを共有およびスケジュールできます。<p>データアナリストは、多くの場合、組織内のユーザー向けにAnalysis Workspaceでプロジェクトを作成します。</p><p>プロジェクトを作成した後、アナリストはこれらのプロジェクトを [エンドユーザー](#end-users)（非アナリスト）データを要求し、データの解釈方法を理解するのに役立つ組織内。</p> | <ul><li>[プロジェクトの作成](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[プロジェクトの共有](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| アトリビューション | アナリストは、Analysis Workspaceで様々なアトリビューションモデルとルックバックウィンドウを使用して、ディメンション項目が成功イベントのクレジットを取得する方法をカスタマイズできます。<p>線形アトリビューションモデルでは、コンバージョンに至るすべてのタッチポイントに同等のクレジットが与えられ、ファーストタッチでは、ファーストタッチポイントにフルクレジットが与えられます。 他の多くのアトリビューションモデルが使用可能です。これには、統計的手法を使用してクレジットの最適な配分を動的に決定するアルゴリズムモデルが含まれます。 </p> | [アトリビューションモデルとルックバックウィンドウ](/help/analyze/analysis-workspace/attribution/models.md) |
| 異常値の検出 | Analysis Workspaceの統計モデリングでは、指標を分析し、値の下限、上限、期待される範囲を決定することで、データ内の予期しないトレンドを自動的に見つけます。 予期しないスパイクまたは下落が発生した場合にレポートします。 | [異常値検出の概要](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| 貢献度分析 | Analysis Workspaceを使用して、統計的異常値を説明し、オーディエンスセグメント間の指標に関する予期しない顧客行動、範囲外の値、急激なスパイクや急激な下降の背後にある相関関係を特定します。 | [貢献度分析のトークン - 概要](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| インテリジェントアラート | 1 つのアラートで複数の指標を示すデータの異常値および「積み重ね」アラートに基づいて、アラートを作成および管理します。 | [インテリジェントアラートの概要](help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| データの書き出し | Data Warehouseおよびデータフィードを使用すると、Google Cloud Platform、Azure RBAC、Azure SAS、Amazon S3 など、様々なクラウドの宛先にデータを書き出すことができます。 | [Analytics 書き出しガイド](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=ja) |
| Activity Map | Activity Map は Adobe Analytics のアプリケーションであり、視覚的なオーバーレイを使用してリンクアクティビティをランク付けし、Web ページに対するオーディエンスのエンゲージメントを監視するリアルタイム分析のダッシュボードを提供するよう設計されています。<p>Activity Map を使用すると、様々なビューを設定することにより、顧客アクティビティの増加を視覚的に特定し、マーケティングイニシアチブを数量化して、オーディエンスのニーズや行動に合わせて対応することができます。</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=ja) |
| Report Builder | Report Builder は Microsoft Excel のアドインです。Report Builder を使用すると、Excel ワークシートに挿入された Adobe Analytics データからカスタマイズしたリクエストを作成できます。リクエストはセルから動的に参照できます。さらに、Report Builder によるデータの表示形式は更新やカスタマイズが可能です。 | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=ja) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### はじめに（エンドユーザー向け）

プロフェッショナルなアナリストでないエンドユーザーは、組織内のアナリストと協力してAdobe AnalyticsとAnalysis Workspaceの最大限の力を活用したり、Analysis Workspaceの基本を学んで顧客に関する実用的なインサイトを得たりできます。

#### アナリストとの連携

通常、様々なサイトにわたる顧客の行動に関する詳細を学びたいと考えている組織のユーザーは、専門的なアナリストではありません。

理想的には、これらのユーザーは [アナリスト](#analysts) 組織内で次の操作をおこないます。

1. 分析の要件を定義するには、顧客について学びたいことをアナリストに説明します。

1. 分析をレビューし、目標を満たしていることを確認します。

1. 分析から得られたデータについて話し合います。

1. 必要に応じて、解析を時間の経過と共に変更します。

#### Analysis Workspaceでの分析の作成

Adobe Analyticsから実用的なインサイトを得るために、データアナリストである必要はありません。

一部のユーザーは、データアナリストと協力して、 Analysis Workspaceでプロジェクトを設定し、データの解釈方法を説明すると便利です。詳しくは、 [アナリストとの連携](#work-with-analysts)を使用すると、他のユーザーも、プロジェクトの構築やデータ自体の解釈に慣れている場合があります。

Analysis Workspace では、分析をすばやく作成してインサイトを収集し、他のユーザーと共有できます。ドラッグ＆ドロップのブラウザーインターフェイスを使用して、分析の作成、データを活用するためのビジュアライゼーションの追加、データセットのキュレーション、選択した任意のユーザーとのプロジェクトの共有とスケジュールを行うことができます。

Analysis Workspaceで分析を作成する方法について詳しくは、 [Analysis Workspaceの概要](/help/analyze/analysis-workspace/home.md).

### 開発者向け入門ガイド

[Analytics API を使用すると、アドビのサーバーを直接呼び出し、ユーザーインターフェイスで実行できるほぼすべてのアクションを実行できます。](https://developer.adobe.com/analytics-apis/docs/2.0/)

レポートを作成して、データに関する重要な質問を調べたり、インサイトを得たり、回答したりすることができます。また、セグメントや計算指標の作成など、Adobe Analytics のコンポーネントを管理することもできます。

## ビデオの概要

Adobe Analyticsの基本を学ぶには、こちらをご覧ください *Adobe Analyticsの概要 — スキルビルダーウェビナー* ビデオ。 ビデオでは、データの取得方法、Adobe Analytics へのデータの送信方法、Adobe Analytics 内で使用できるビジュアライゼーション機能の基本について説明します。このビデオでは、データを作成、デプロイ、収集および解釈するための基礎を提供し、収集したデータに基づいて実用的なインサイトとレコメンデーションを提供します。

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

使用するツールに関する質問については、[使用する Adobe Analytics ツールの検討](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/which-analytics-tool.html?lang=ja)を参照してください。

## Customer Journey Analytics

Customer Journey Analytics は、Adobe Experience Platform からのデータと共に Analysis Workspace の機能を使用できるアドビの次世代 Analytics ソリューションです。数年分のデータを分類、フィルタリング、クエリ、視覚化でき、あらゆる種類のデータスキーマやデータの種類を保持できる Platform の機能と組み合わせることができます。

Adobe Analyticsと比較した場合のCustomer Journey Analyticsの利点の一部を次に示します。

* **変数とイベントは無制限**：eVar、prop、イベントの概念は存在しなくなりました。データは主にディメンションと指標に焦点を当てています。データセットには、無制限の数の一意のディメンションと指標を含めることができます。

* **無制限の一意の値**：Adobe Experience Platform では、一意制限を受けることはありません。

* **履歴データの変更**：Adobe Experience Platform を使用して、データを削除または修正できます。

* **クロスレポートスイートデータ**：複数のデータセットからの既存の実装を Platform で組み合わせることができます。

詳しくは、 [Customer Journey Analyticsの概要](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja).

