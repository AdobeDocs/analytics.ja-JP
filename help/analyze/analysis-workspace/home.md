---
description: Adobe Analyticsの使用を開始する方法を説明します。
keywords: Analysis Workspace
seo-description: Adobe Analyticsの使用を開始する方法を説明します。
seo-title: はじめに
solution: Analytics
title: はじめに
topic: Reports & Analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Analysis Workspace

Analysis Workspaceは、組織にとって実用的なデータベースの決定を行うためのアドビの主要ツールの1つです。 最も一般的なビジュアライゼーションであるフリーフォームテーブルを使用すると、ディメンション、指標、セグメントおよび日付範囲を使用して、カスタマイズしたレポートを簡単に作成できます。

## 前提条件

[Adobe Experience Platform Launchを使用してAdobe Analyticsにデータを送信します](/help/implement/implement-with-launch/validate-publish-prod.md)。Analysis Workspaceを使用するには、実装が正常に行われている必要があります。 ツールを使用する前に、組織がアドビにデータを送信していることを確認します。 DTMやレガシー手動実装など、他の実装も同様に機能します。

## Workspaceでの基本ランクレポートの取り込み

Analysis Workspaceを使用して基本ランクレポートを取り込みます。 ランクレポートには、各ディメンション値の集計された合計ビューが表示され、最も大きい値が最初に表示されます。 これらのタイプのレポートは、最もトラフィックが多いページや最も売れている製品など、サイトのどのコンポーネントが最も効果的かを知るのに役立ちます。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. 右上の 9 つの正方形のアイコン、色付きの Analytics ロゴの順にクリックします。
3. 上部ナビゲーションバーで、「ワークスペース」をクリックします。
4. [新しいプロジェクトの作成]ボタンをクリックします。
5. モーダルポップアップで「空白のプロジェクト」が選択されていることを確認し、「作成」をクリックします。
6. 左側に、ディメンション、指標、セグメントおよび日付範囲のリストが表示されます。 ページディメンション（色付きのオレンジ色）を見つけ、「ここにディメンションをドロップ」と表示されたカンバスにドラッグします。
7. レポートスイートにデータが含まれている場合は、今月のトップページを示すレポートが表示されます。 Analysis Workspaceは、回数指標を使用してレポートに自動的に [入力](/help/components/c-variables/c-metrics/metrics-occurrences.md) します。
8. 訪問回数指標（緑色）を見つけ、回数指標ヘッダーの上 **または****** （指標の上に配置しないで）の隣にドラッグします。 訪問回数指標を回数の上にドラッグすると、レポートでその指標が置き換えられます。 「回数」の横に訪問回数指標をドラッグすると、両方の指標が並べて表示されます。
9. プロジェクトを保存する場合は、左上のメニューで *[!UICONTROL Project]/[!UICONTROL Save]* （保存）をクリックします。

## Workspaceでの基本トレンドレポートの取得

Analysis Workspaceを使用して基本トレンドレポートを取得します。 トレンドレポートは、選択した日付範囲を使用した指標の時系列表示を示します。 これらのタイプのレポートは、経時的なトレンドの特定に役立ち、ビジネス上の意思決定の成功または失敗を測定するために使用できます。 例えば、経時的にトレンド表示されたページビュー数レポートを見て、サイトの再設計がトラフィックの増減に役立ったかどうかを確認できます。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. 右上の 9 つの正方形のアイコン、色付きの Analytics ロゴの順にクリックします。
3. 上部ナビゲーションバーで、「ワークスペース」をクリックします。
4. [新しいプロジェクトの作成]ボタンをクリックします。
5. モーダルポップアップで「空白のプロジェクト」が選択されていることを確認し、「作成」をクリックします。
6. 左側に、ディメンション、指標、セグメントおよび日付範囲のリストが表示されます。 ページビュー数ディメンションを見つけ、「ここに指標をドロップ」というラベルが付いたキャンバス上の小さなスペースにドラッグします。 ディメンション用に予約されたスペースにドロップしないでください（少なくともこの演習では）。
7. レポートスイートにデータが含まれている場合は、今月の基本ページビュー数レポートが表示されます。 Analysis Workspaceは自動的に「日」の日付範囲を取り込むので、現在の月のページビューのトレンドを確認できます。
8. 左側の日付範囲コンポーネントのリストで、週の日付範囲（紫色）を探します。 日付範囲のタイトルをクリックして、すべての日付範囲コンポーネントを展開し表示するか、検索バーを使用します。
9. カンバス上の日付範囲ヘッダーの上にある週の日付範囲をドラッグして置き換えます。
10. トレンドレポートは、日ではなく週別に集計されるようになりました。
11. プロジェクトを保存する場合は、左上のメニューで *[!UICONTROL Project]/[!UICONTROL Save]* （保存）をクリックします。

## ツールを使ってテストする

Analysis Workspaceはレポート作成ツールなので、データ収集には影響しません。 コンポーネントをプロジェクトに無差別にドラッグして、何が機能するかを確認する効果はありません。 様々なディメンションと指標の組み合わせをワークスペースプロジェクトにドラッグして、利用可能な項目を確認します。

無効なコンポーネントを誤ってワークスペースプロジェクトにドラッグしたり、ステップに戻したい場合は、Ctrl + zキー(Windows)またはCommand + zキー(Mac)を押して、最後に行った操作を元に戻します。 左上のメニューでプロジェクト *[!UICONTROL /新規をクリッ]クして* 、新しいスレートから始めることもできます。

## トラブルシューティング

**指標をドラッグすると、「無効なデータ」と表示されます。**

無効なデータは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。 例えば、2つの指標を同じように表示する方法がないので、2つの指標を重ね合わせてデータとして返すことはできません。 代わりに、指標を並べて配置します。

**指標をドラッグすると、実際のデータは表示されず、ゼロだけが表示されます。**

ワークスペースレポートを正常に作成したがデータがない場合は、次の点を確認できます。

* レポートスイートを再確認し、データが入力されていることを確認します。
* レポートでセグメントを使用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。 セグメントを削除するか、セグメント定義を調整してみてください。
* 右上の日付範囲を確認し、期待する値に設定されていることを確認します。
* Webサイトに移動し、デバッガーを使用してデータが収集されていることを検証します。

## その他のリソース

* [Analysis Workspaceリリースノート](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md):ツールに導入された最新の機能について説明します。
* [YouTube上の分析ワークスペース](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS):この広範なプレイリストを使用して、Analysis Workspaceのほとんどの機能を使用する方法を説明します。
* 製品内のヒント：1日のヒントと短いビデオは、Analysis Workspaceの右下隅に表示されることがあります。 これらのヒントを閉じると、ヘルプ/ヒ *[!UICONTROL ント](英語[!UICONTROL )を使用し]* ていつでも表示できます。
* [Analysis Workspaceコミュニティ](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace):他のユーザーとAnalysis Workspaceについて話し合い、ツールで表示したい機能に投票します。
* ブログ投稿：
   * [賢い分析による組織の強化](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [新しいAdobe Analytics機能により、強力なインサイトにアクセスしやすくなりました。](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [Analysis Workspaceで生産性を最大化する5つのヒント](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Analysis Workspaceによるインサイトの高速化](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Analysis Workspace を使用する理由](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 次の手順

Analysis Workspaceの理解を深めるためには、多くの方法があります。 アドビが推奨する基本事項を以下に示します。

### Analysis Workspaceの使用方法に関する知識を広げたいエンドユーザー向け

* [Workspace UIの詳細](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md):基本レポートを作成したら、残りのインターフェイスに慣れてください。
* [Workspaceのビジュアライゼーション](visualizations/freeform-analysis-visualizations.md):フリーフォームテーブルは、Analysis Workspaceのビジュアライゼーションの1つのタイプにすぎません。 折れ線グラフ、棒グラフ、地域マップなど、他のビジュアライゼーションの使用方法を説明します。
* [Workspaceのディメンション](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md):ディメンションとは何か、および単なるランクレポート以外でのディメンションの使用方法について詳しく説明します。
* [Workspaceの指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md):フリーフォームテーブルの他の部分での指標の概要と使用方法について説明します。
* [セグメントの概要](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md):セグメントとは何かを説明し、セグメントを使用して基本レポートを作成します。
* [Workspaceの日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md):相対日付と相対日付について説明し、Workspaceプロジェクトで使用します。
* Workspaceでのプロジェクトの共有：自分が作成したWorkspaceプロジェクトを同僚に表示します。
* [（詳細）Workspaceのパネル](c-panels/panels.md):アトリビューションやセグメント比較など、Workspaceの高度な機能を使用します。

### 組織のワークスペースの質の向上を検討しているアナリストおよび管理者向け

* [Analysis Workspace権限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html):Adobe Admin Consoleを使用して、Workspaceにユーザー権限を割り当てます。
* [ソリューションデザインドキュメントの作成](/help/implement/prepare/solution-design.md):組織がサイト固有の追加のディメンションや指標を収集する方法を計画し始めます。
* [Workspaceのテンプレート](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md):ニーズに合わせて調整されたプロジェクトスペースから、同僚が作業を開始できるように、テンプレートを作成します。
* [Workspaceキュレーション](curate-share/curate.md):使用可能なコンポーネントを制限するプロジェクトを作成し、ツールに慣れていないユーザーがワークスペースにアクセスしやすくする
