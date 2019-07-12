---
title: Adobe Analyticsのオーディエンスレポート
description: Analysis Workspaceを使用してオーディエンスベースのレポートを作成する方法について説明します。
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# オーディエンスレポート

オーディエンスレポートには、サイトの訪問者のタイプに関する情報が表示されます。

このページでは、Analysis Workspaceの使用に関する基本的な知識があると想定しています。See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## アクティブなユーザー

アクティブなユーザーは、1、7、14または28日前のサイトへのユーザーの累積数を表示します。Adobeでは、Google Analyticsでの正確な計算が行われていませんが、指標個別訪問者数を使用して、選択した日付範囲に基づいて、サイトに対して重複しないユーザー数を表示できます。

個別訪問者の折れ線グラフを取得するには:

1. 左側のビジュアライゼーションアイコンをクリックし、空白のフリーフォームテーブルの上にあるワークスペースに線ビジュアライゼーションをドラッグします。
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the smaller space labeled &#39;Drop a Metric here&#39;.
3. If different granularity is desired, drag the desired date range (e.g. **Day**, **Week**, **Month**, etc.) をクリックします。

See [Unique Visitors](../../../components/c-variables/c-metrics/metrics-unique-visitors.md) in the Components user guide for details on how Adobe calculates unique visitors.

## ライフタイム値

ライフタイム値は、両方のプラットフォームで特別な特別実装を必要とする機能です。アドビでは、このデータを取得するために導入コンサルタントと協力することを推奨しています。

## コホート分析

コホート分析は、同じユーザーがサイトに戻る頻度を示します。

コホートテーブルを作成するには:

1. 左側のビジュアライゼーションアイコンをクリックし、コホートテーブルビジュアライゼーションをワークスペースにドラッグします。
2. Click the Components icon on the left, then drag the **Visits** metric onto both the Inclusion Criteria and Return Criteria.
3. 「作成」をクリックします。

See [Cohort Analysis](../../../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) in the Analysis Workspace user guide for details on additional customizations to the cohort visualization.

## オーディエンス

Google Analyticsのオーディエンスレポートには、オーディエンスの設定が必要です。オーディエンスには、Adobe Audience Managerを使用したアドビの設定も必要です。詳しくは、&quot;Adobe Audience Managerユーザーガイド」を参照してください。

## User Explorer

ユーザーエクスプローラーレポートを使用すると、アナリストは匿名識別子を使用して個々の訪問を表示できます。アドビでは、データフィードの外部でバックエンド識別子を処理しません。これはデータのヒットレベルのRAWエクスポートです。

* このデータがAnalysis Workspaceで必要な場合は、導入コンサルタントと協力して、匿名化された一意の識別子cookieの値をeVarに渡すことができます。これは、1か月あたり100万人未満の個別訪問者数で構成される小規模な実装でのみ機能します。
* If this data is desired within data feeds, the concatenated columns `visid_high` and `visid_low` are the most common way to identify unique visitors. Learn more about [Data Feeds](../../../export/analytics-data-feed/c-getstarted/data-feed-overview.md) in the Export user guide.

## 人口統計レポートと目標レポート

人口統計と関心データは、サイトユーザーの年齢、性別、興味に関する情報を提供します。このデータは、クロスサイトトラッキング機能を通してGoogleによって収集されます。

人口統計と興味のデータは、アドビによって自動的に収集されることはありません。ただし、組織がこのデータを取得した場合は、Adobe Experience Cloudプラットフォーム内の機能である顧客属性を使用できます。属性によってデータ編成を完全に制御できるので、人口統計や興味に限りません。

詳しくは、顧客属性ヘルプを参照してください。

## 地域-言語

地域言語レポートは、訪問者のブラウザーの言語設定によってサイトトラフィックを表示します。

言語レポートを作成するには:

1. In the Components menu, locate the **Language** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Language](../../../components/c-variables/dimensionslist/reports-languages.md) dimension in the Components user guide for more information.

## 地域-場所

地域レポートでは、世界規模の地図表示、データの分類が国ごとに行われます。

地域レポートを作成するには:

1. 左側のビジュアライゼーションアイコンをクリックし、マップビジュアライゼーションを空のフリーフォームテーブルの上にあるワークスペースにドラッグします。
2. Click the Components icon on the left, then drag the **Unique Visitors** metric into the space labeled &#39;Add Metric&#39;.
3. 「作成」をクリックします。

マップに加えてテーブルが必要な場合:

1. In the Components menu, locate the **Countries** dimension and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See [Geosegmentation](../../../components/c-variables/dimensionslist/reports-geosegmentation.md) dimensions in the Components user guide for more information.

## 行動-新規とリターン

新規レポートとリターンレポートでは、最初のセッション（新規訪問）と後続セッション（再来訪）を簡単に表示できます。

新規訪問回数レポートと再来訪レポートを作成するには:

1. In the components menu, locate the **First Time Visits** segment and drag it onto the large freeform table area labeled &#39;Drop a Dimension here&#39;. **初回訪問回数** はセグメントですが、Workspaceでは通常、行を表すディメンションが使用されます。
2. **再来訪** セグメントを見つけて、セグメント行ヘッダーの上部にドラッグします。これにより、セグメントが初回訪問件数以下のディメンションとして追加され、容易に比較できるようになります。
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

折れ線グラフも必要な場合:

1. 左側のビジュアライゼーションアイコンをクリックし、フリーフォームテーブルの上のワークスペースに線ビジュアライゼーションをドラッグします
2. フリーフォームテーブルの各行にあるCtrlキー（Windows）またはCommandキー（Mac OS）を押しながら、各行をハイライト表示します。これにより、両方のトレンドが行のビジュアライゼーションに表示されます。
3. 線のビジュアライゼーションの左上隅にある小さい丸い丸の点をクリックし、チェックボックスの「選択項目をロック」をクリックします。

## 行動-頻度と最新性

The frequency &amp; recency report is approximately equal to the **Visit Number** dimension in Analysis Workspace.

1. In the components menu, locate the **Visit Number** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Visit Number](../../../components/c-variables/dimensionslist/reports-visitor-number.md) dimension in the Components user guide for more information.

## 行動-アクション

The engagement report is approximately equal to the **Time Spent per Visit - Bucketed** dimension.

1. In the components menu, locate the **Time Spent per Visit - Bucketed** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Time Spent per Visit](../../../components/c-variables/dimensionslist/reports-time-spent-per-visit.md) dimension in the Components user guide for more information.

## 技術-ブラウザーとOS

ブラウザーおよびOSレポートには、複数の主要ディメンションがあります。

* **ブラウザー** のプライマリディメンションは、Analysis Workspaceでディメンションとしても使用できます。
* **オペレーティングシステム** のプライマリディメンションは、Analysis Workspaceでディメンションとしても使用できます。
* **画面解像度** のプライマリディメンションは、Analysis Workspaceで **モニター解像** 度ディメンションとして使用できます。
* **画面色** のプライマリディメンションは、Analysis Workspaceで **色深度** ディメンションとして使用できます。
* **Flashバージョン** のプライマリディメンションはAdobe Analyticsでは使用できませんが、必要に応じてeVarによってこのデータを収集できます。

1. コンポーネントメニューで、前述の目的のディメンションを見つけて、「ここにディメンションをドロップ」というラベルの大きなフリーフォームテーブル領域にドラッグします。
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

それぞれのディメンションについて詳しくは、「コンポーネントユーザーガイド」の次のページを参照してください。

* [ブラウザー](../../../components/c-variables/dimensionslist/reports-browsers.md)
* [オペレーティングシステム](../../../components/c-variables/dimensionslist/reports-operating-system.md)
* [画面の解像度](../../../components/c-variables/dimensionslist/reports-technology.md)
* [画面の色](../../../components/c-variables/dimensionslist/reports-color-depth.md)

## 技術-ネットワーク

The network report is approximately equal to the **Domain** dimension.

1. In the components menu, locate the **Domain** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Domain](../../../components/c-variables/dimensionslist/reports-domains.md) dimension in the Components user guide for more information.

## モバイル-概要

The mobile overview report is approximately equal to the **Mobile Device Type** dimension. 「その他」の値はデスクトップトラフィックと同じです。

1. In the components menu, locate the **Mobile Device Type** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device Type](../../../components/c-variables/dimensionslist/reports-device-types.md) dimension in the Components user guide for more information.

## モバイル-デバイス

The mobile devices report is approximately equal to the **Mobile Device** dimension.

1. In the components menu, locate the **Mobile Device** dimension and drag it onto the large freeform table area labeled &#39;Drop a dimension here&#39;.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Mobile Device](../../../components/c-variables/dimensionslist/reports-devices.md) dimension in the Components user guide for more information.

## カスタム

カスタムレポートは、実装ごとに定義されます。これらのレポートを解釈するには、組織のAnalytics管理者または導入コンサルタントに相談してください。Typically an organization maintains a [Solution Design Document](../../../implement/prepare/solution-design.md) to keep track of custom variable values and how they are populated.

## ベンチマーク

ベンチマークレポートを使用すると、データのファセットを業界平均とどのように比較するかを確認できます。現時点では、アドビは顧客間でのデータのベンチマークを共有していません。

## ユーザーフロー

フローレポートは両方のプラットフォームで利用できます。フローレポートを作成するには:

1. 左側のビジュアライゼーションアイコンをクリックし、フロービジュアライゼーションをフリーフォームテーブルの上のワークスペースにドラッグします
2. **ページ** ディメンションを見つけて、矢印アイコンをクリックしてページ値を表示します。ディメンション値は黄色で表示されます。
3. 開始するページ値を探し、「ディメンションまたは項目」という名前のスペースにドラッグします
4. このフローレポートはインタラクティブです。任意の値をクリックして、後続のページまたは前のページにフローを展開します。右クリックメニューを使用して、列を展開または折りたたみます。同じフローレポート内でも異なるディメンションを使用できます。
