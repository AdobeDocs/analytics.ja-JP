---
description: Adobe Analyticsの使用を開始する方法。
keywords: Analysis Workspace
seo-description: Adobe Analyticsの使用を開始する方法。
seo-title: はじめにガイド
solution: Analytics
title: はじめにガイド
topic: Reports and Analytics
uuid: 851feedb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: a0158b98089c044091f61796d782604865aa4eba

---


# Analysis Workspace

Analysis Workspaceは、組織に対して実行可能なデータベースの決定を行うための、アドビのflagshipツールの1つです。最も一般的なビジュアライゼーションであるフリーフォームテーブルでは、ディメンション、指標、セグメント、日付範囲を使用してカスタマイズしたレポートを簡単に作成できます。

## 前提条件

[Adobe Experience Platform Launchを使用してAdobe Analyticsにデータを送信](../../implement/implement-with-launch/validate-publish-prod.md)します。Analysis Workspaceを使用するには、作業の実装が必要です。ツールを使用する前に、組織がアドビにデータを送信していることを確認してください。DTMやレガシーの手動実装などのその他の実装も同様に機能します。

## ワークスペースでの基本ランクレポートの取り込み

Analysis Workspaceを使用して基本的なランクレポートを取り込みます。ランクレポートには、各ディメンション値の集計合計表示が表示され、最初に最も大きな値が表示されます。これらのタイプのレポートは、最もトラフィックの多いページや最も売れている商品など、サイトのどのコンポーネントが最も効果的かを知るのに役立ちます。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. 右上の9正方形アイコンをクリックし、色付きのAnalyticsロゴをクリックします。
3. 上部ナビゲーションバーで、「ワークスペース」をクリックします。
4. 「新規プロジェクトを作成」ボタンをクリックします。
5. モーダルポップアップで、「空白のプロジェクト」が選択されていることを確認し、「作成」をクリックします。
6. 左側には、ディメンション、指標、セグメント、日付範囲のリストが表示されます。ページディメンション（オレンジ色のオレンジ色）を見つけて、「ここにディメンションをドロップ」と表示されるキャンバスまでドラッグします。
7. レポートスイートにデータがある場合、今月のトップページを表示するレポートが表示されることがあります。Analysis Workspace automatically populated the report with the [Occurrences](../../components/c-variables/c-metrics/metrics-occurrences.md) metric.
8. Locate the Visits metric (colored green), and drag it either **over** or **next to** the Occurrences metric header (avoid placing it above the metric). 回数の上部に訪問回数指標をドラッグすると、レポートで指標が置換されます。「回数」の横にある訪問回数指標をドラッグすると、両方の指標が並べて表示されます。
9. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## ワークスペースでの基本トレンドレポートの取り込み

Analysis Workspaceを使用して基本トレンドレポートを取り込みます。トレンドレポートは、選択した日付範囲を使用した指標の時系列ビューを表示します。これらのタイプのレポートは、経時的な傾向を特定するのに役立ち、ビジネス決定の成功または失敗を測定するために使用できます。例えば、ページビュー数レポートを経時的に調べて、サイトの再設計によってトラフィックの増減がサポートされるかどうかを確認できます。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. 右上の9正方形アイコンをクリックし、色付きのAnalyticsロゴをクリックします。
3. 上部ナビゲーションバーで、「ワークスペース」をクリックします。
4. 「新規プロジェクトを作成」ボタンをクリックします。
5. モーダルポップアップで、「空白のプロジェクト」が選択されていることを確認し、「作成」をクリックします。
6. 左側には、ディメンション、指標、セグメント、日付範囲のリストが表示されます。ページビューディメンションを見つけ、「ここに指標をドロップ」というラベルの付いたキャンバスの小さいスペースにドラッグします。ディメンション用に予約されているスペースにドロップすることは避けてください（この演習では少なくとも使用できます）。
7. レポートスイートにデータがある場合は、現在の月の間に基本的なページビューレポートが表示されることに注意してください。Analysis Workspaceは「日」日付範囲に自動的に取り込まれるので、現在の月のページビューのトレンドを確認できます。
8. 左側の日付範囲コンポーネントのリストで、週の日付範囲（色付きの紫色）を探します。日付範囲のタイトルをクリックして、すべての日付範囲コンポーネントを展開したり表示したり、検索バーを使用したりします。
9. キャンバス上の日付範囲ヘッダーの上部にある週の日付範囲をドラッグして、置き換えます。
10. トレンドレポートは、曜日ではなく週ごとに集計されるようになりました。
11. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## ツールでテストする

Analysis Workspaceはレポートツールなので、データ収集には影響しません。意図的にコンポーネントをプロジェクトにドラッグしても、何が動作するかを確認することはありません。ディメンションと指標の様々な組み合わせをワークスペースプロジェクトにドラッグして、利用可能なものを確認します。

誤って無効なコンポーネントをワークスペースプロジェクトにドラッグした場合、またはステップに戻る場合は、Ctrl+ Zキー（Windows）またはCommand+ Zキー（Mac）を押して最後のアクションを取り消します。You can also start with a clean slate by clicking *[!UICONTROL Project]&gt;[!UICONTROL New]* in the upper left menu.

## トラブルシューティング

**指標をドラッグすると、「無効なデータ」と表示されます。**

無効なデータは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返すことができないことを意味します。例えば、2つの指標を表示する方法がないため、2つの指標を相互に積み重ねてデータとして積み重ねることはできません。代わりに、指標を並べて配置します。

**指標をドラッグすると、実際のデータが表示されません。**

ワークスペースレポートを作成したが、データがない場合は、次のことを確認できます。

* レポートスイートをダブルチェックして、データが入力されたことを確認します。
* レポートでセグメントを使用している場合、セグメント条件がどのデータにも一致しないことがあります。セグメントを削除するか、セグメント定義を調整してみてください。
* 右上の日付範囲をチェックし、期待する値に設定してください。
* Webサイトに移動し、デバッガーを使用してデータが収集されていることを確認します。

## その他のリソース

* [Analysis Workspaceリリースノート](../../analyze/analysis-workspace/new-features-in-analysis-workspace.md):ツールに導入された最新の機能をお読みください。
* [YouTube上のAnalysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS):この広範なプレイリストを介して、Analysis Workspaceのほとんどの機能を使用する方法について説明します。
* 製品内ヒント:短いビデオと共に、今日のヒントは、分析ワークスペースの右下隅に表示されることがあります。If these tips are dismissed, they can be reached through *[!UICONTROL Help]&gt;[!UICONTROL Tips]* at any time.
* [Analysis Workspaceコミュニティ](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace):Analysis Workspaceについて、ユーザーと話し合って、ツールに表示する機能に投票します。
* ブログ投稿:
   * [賢い分析による組織の強化](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [強力なインサイトをより一層アクセスできる新しいAdobe Analytics機能](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [Analysis Workspaceで生産性を最大化するための5つのヒント](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [分析ワークスペースによるインサイトの迅速化](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Analysis Workspace を使用する理由](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 次の手順

Analysis Workspaceの理解を深めるには、多くの指示があります。アドビに推奨される基本事項を以下に示します。

### 分析ワークスペースの使用方法に関する知識を深めるエンドユーザー向け

* [Workspace UIの詳細](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md):基本レポートを作成した後、残りのインターフェイスについて理解しやすくなりました。
* [Workspaceのビジュアライゼーション](visualizations/freeform-analysis-visualizations.md):フリーフォームテーブルは、Analysis Workspaceのビジュアライゼーションのタイプの1つだけです。折れ線グラフ、棒グラフ、地理マップなど、他のビジュアライゼーションを使用する方法について説明します。
* [Workspaceのディメンション](../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md):ランクレポート以外のディメンションの詳細と使用方法について説明します。
* [Workspaceの指標](../../analyze/analysis-workspace/components/apply-create-metrics.md):どの指標と、それらの指標をフリーフォームテーブルの他の部分で使用するかについて詳しく説明します。
* [セグメントの概要](../../analyze/analysis-workspace/components/t-freeform-project-segment.md):セグメントを使用して、セグメントを使用して基本レポートを作成する方法について説明します。
* [Workspaceの日付範囲](../../analyze/analysis-workspace/components/calendar-date-ranges/calendar.md):相対日付と相対日付について説明し、ワークスペースプロジェクトで使用します。
* Workspaceでのプロジェクトの共有:作成した素晴らしいワークスペースプロジェクトに同僚を表示します。
* [（詳細）ワークスペースのパネル](c-panels/panels.md):アトリビューションやセグメント比較など、Workspaceの高度な機能を使用します。

### 組織内のワークスペースの品質を改善するためのアナリストおよび管理者向け

* [Analysis Workspaceの権限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html):Adobe Admin Consoleを使用して、Workspaceにユーザー権限を割り当てます。
* [ソリューションデザインドキュメント](../../implement/prepare/solution-design.md)の作成:貴社のサイトに固有のディメンションや指標を組織がどのように収集するかを計画します。
* [ワークスペースのテンプレート](../../analyze/analysis-workspace/build-workspace-project/starter-projects.md):テンプレートを作成して、同僚がニーズに合わせてプロジェクト空間を作成できるようにします。
* [Workspaceキュレーション](curate-share/curate.md):利用可能なコンポーネントを制限するプロジェクトを作成し、ツールに精通していないユーザーからワークスペースにアクセスできるようにする