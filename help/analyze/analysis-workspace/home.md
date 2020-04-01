---
description: Adobe Analytics の使用開始方法を説明します。
keywords: Analysis Workspace
title: 入門ガイド
translation-type: tm+mt
source-git-commit: 825dc13b0294e5a96b30b95f14524175d44c621d

---


# Analysis Workspace

Analysis Workspace は、組織にとって実用的なデータベースの決定をおこなう、アドビの主要ツールの 1 つです。最も一般的なビジュアライゼーションであるフリーフォームテーブルを使用すれば、ディメンション、指標、セグメントおよび日付範囲を使用し、カスタマイズしたレポートを簡単に作成できます。

## 前提条件

[Adobe Experience Platform Launch を使用して Adobe Analytics にデータを送信する](/help/implement/launch/validate-publish-prod.md)：Analysis Workspace を使用するには、動作する実装が必要です。ツールを使用する前に、組織がアドビにデータを送信していることを確認します。DTM やレガシーの手動による実装など、他の実装も同様に機能できます。

## Workspace での基本ランクレポートの取り込み

Analysis Workspace を使用して基本ランクレポートを取り込みます。ランクレポートには、各ディメンション値の集計された合計ビューが表示され、最も大きい値が最初に表示されます。これらのタイプのレポートは、最もトラフィックが多いページや最も売れている製品など、サイトのどのコンポーネントが最も効果的かを知るのに役立ちます。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. 右上の 9 つの正方形のアイコン、色付きの Analytics ロゴの順にクリックします。
3. 上部ナビゲーションバーで、「Workspace」をクリックします。
4. 「新規プロジェクトを作成」ボタンをクリックします。
5. モーダルポップアップで「空白のプロジェクト」が選択されていることを確認し、「作成」をクリックします。
6. 左側に、ディメンション、指標、セグメントおよび日付範囲のリストが表示されます。ページディメンション（色付きのオレンジ色）を見つけ、「ここにディメンションをドロップ」と表示されたキャンバスにドラッグします。
7. レポートスイートにデータが含まれている場合は、今月のトップページを示すレポートが表示されます。Analysis Workspace は、[回数](/help/components/c-variables/c-metrics/metrics-occurrences.md)指標を使用してレポートに自動的に入力します。
8. 訪問回数指標（緑色）を見つけ、回数指標ヘッダーの&#x200B;**上**&#x200B;または&#x200B;**隣**&#x200B;にドラッグします（指標の上に配置しないでください）。訪問回数指標を「回数」の上にドラッグすると、レポート内のその指標が置き換えられます。「回数」の横に訪問回数指標をドラッグすると、両方の指標が並べて表示されます。
9. If you&#39;d like to save your project, click *[!UICONTROL Project]>[!UICONTROL Save]*in the upper left menu.

## Workspace での基本トレンドレポートの取り込み

Analysis Workspace を使用して基本トレンドレポートを取り込みます。トレンドレポートは、選択した日付範囲を使用して、指標の時系列表示を示します。これらのタイプのレポートは、経時的なトレンドの特定に役立ち、ビジネス上の意思決定の成功または失敗を測定するために使用できます。例えば、経時的にトレンド表示されたページビュー数レポートを見て、サイトを作り直したことがトラフィックの増減に役立ったかどうかを確認できます。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. 右上の 9 つの正方形のアイコン、色付きの Analytics ロゴの順にクリックします。
3. 上部ナビゲーションバーで、「Workspace」をクリックします。
4. 「新規プロジェクトを作成」ボタンをクリックします。
5. モーダルポップアップで「空白のプロジェクト」が選択されていることを確認し、「作成」をクリックします。
6. 左側に、ディメンション、指標、セグメントおよび日付範囲のリストが表示されます。ページビュー数ディメンションを見つけ、「ここに指標をドロップ」というラベルが付いたキャンバス上の小さなスペースにドラッグします。ディメンション用に予約されたスペースにドロップしないでください（少なくともこの演習では）。
7. レポートスイートにデータが含まれている場合は、今月の基本ページビュー数レポートが表示されます。Analysis Workspace は自動的に「日」の日付範囲を取り込むので、現在の月のページビューのトレンドを確認できます。
8. 左側の日付範囲コンポーネントのリストで、週の日付範囲（紫色）を探します。日付範囲のタイトルをクリックして、すべての日付範囲コンポーネントを展開して表示するか、検索バーを使用します。
9. キャンバス上の日付範囲ヘッダーの上にある週の日付範囲をドラッグして置き換えます。
10. トレンドレポートは、日ではなく週別に集計されるようになりました。
11. If you&#39;d like to save your project, click *[!UICONTROL Project]>[!UICONTROL Save]*in the upper left menu.

## ツールを使って実験する

Analysis Workspace はレポート作成ツールなので、データ収集には影響しません。何が機能するかを確認するためにコンポーネントをプロジェクトに適当にドラッグしても、データに影響はありません。様々なディメンションと指標の組み合わせをワークスペースプロジェクトにドラッグして、利用可能な項目を確認してください。

無効なコンポーネントを誤ってワークスペースプロジェクトにドラッグした場合や、手順を 1 つ戻したい場合は、Ctrl + Z キー（Windows）または Command + Z キー（Mac）を押して、最後におこなった操作を元に戻します。You can also start with a clean slate by clicking *[!UICONTROL Project]>[!UICONTROL New]*in the upper left menu.

## トラブルシューティング

**指標をドラッグすると、「無効なデータ」と表示される。**

無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。代わりに、指標を横に並べて配置します。

**指標をドラッグすると、実際のデータは表示されず、ゼロのみが表示される。**

ワークスペースレポートを正常に作成したのにデータがないという場合は、次の点を確認してください。

* レポートスイートを再度チェックし、データが入力されていることを確認します。
* レポートでセグメントを使用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。セグメントを削除するか、セグメント定義を調整してみてください。
* 右上の日付範囲をチェックし、期待する値に設定されていることを確認します。
* Web サイトに移動し、デバッガーを使用してデータが収集されていることを検証します。

## その他のリソース

* [Analysis Workspace リリースノート](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)：ツールに導入された最新の機能について説明します。
* [Analysis Workspace（YouTube）](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)：この広範なプレイリストを使用して、Analysis Workspace のほとんどの機能を使用する方法を説明します。
* 製品内ヒント：Analysis Workspace の右下隅には時折、その日のヒントと短いビデオが表示されることがあります。If these tips are dismissed, they can be reached through *[!UICONTROL Help]>[!UICONTROL Tips]*at any time.
* [Analysis Workspace コミュニティ](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace)：他のユーザーと Analysis Workspace について話し合い、ツールに望む機能に投票します。
* ブログ投稿：
   * [よりスマートな分析による組織の強化](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [強力なインサイトがより一層得られる新しい Adobe Analytics の機能](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [Analysis Workspace で生産性を最大化するための 5 つのヒント](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Analysis Workspace でインサイトを簡単に](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Analysis Workspace を使用する理由](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## 次の手順

Analysis Workspace の理解を深めるためには、様々なアプローチがあります。アドビが推奨する基本事項を以下に示します。

### Analysis Workspace の使用方法に関する知識を広げたいエンドユーザー向け

* [Workspace UI の詳細](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)：基本レポートを作成したら、残りのインターフェイスに慣れてください。
* [Workspace のビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)：フリーフォームテーブルは、Analysis Workspace のビジュアライゼーションのタイプの 1 つにすぎません。折れ線グラフ、棒グラフ、地域マップなど、他のビジュアライゼーションの使用方法を説明します。
* [Workspace のディメンション](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md)：ディメンションの概要と、単なるランクレポート以外でのディメンションの使用方法について詳しく説明します。
* [Workspace の指標](/help/analyze/analysis-workspace/components/apply-create-metrics.md)：指標の概要と、フリーフォームテーブルの他の部分での指標の使用方法について説明します。
* [セグメントの概要](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md)：セグメントとは何かを説明し、セグメントを使用して基本レポートを作成します。
* [Workspace の日付範囲](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)：相対日付と日周期について説明し、Workspace プロジェクトで使用します。
* Workspace でのプロジェクトの共有：自分が作成した Workspace プロジェクトを同僚に表示します。
* [Workspace のパネル](/help/analyze/analysis-workspace/c-panels/panels.md)：アトリビューションやセグメント比較など、Workspace の高度な機能を使用します。

### 組織のWorkspaceの質の向上を求めているアナリストおよび管理者向け

* [Analysis Workspace 権限](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)：Adobe Admin Console を使用して、Workspace にユーザー権限を割り当てます。
* [Workspace のテンプレート](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)：テンプレートを作成し、同僚のニーズに合わせて調整されたプロジェクトスペースでの作業を同僚が開始できるようにします。
* [Workspace のキュレーション](/help/analyze/analysis-workspace/curate-share/curate.md)：使用可能なコンポーネントを制限するプロジェクトを作成し、ツールに慣れていないユーザーがワークスペースにアクセスしやすいようにします。
