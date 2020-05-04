---
description: Workspace FAQ
title: よくある質問とWorkspaceのトラブルシューティング
translation-type: tm+mt
source-git-commit: 7fbeac0488fbe9b3d10d7c1242f31250f1c7dc16

---


# よくある質問

| 質問 | 回答 |
|--- |--- |
| 分析ワークスペースを使用するための前提条件は何ですか？ | [Adobe Experience Platform Launch を使用して Adobe Analytics にデータを送信する](/help/implement/launch/validate-publish-prod.md)：Analysis Workspace を使用するには、動作する実装が必要です。ツールを使用する前に、組織がアドビにデータを送信していることを確認します。DTM やレガシーの手動による実装など、他の実装も同様に機能できます。 |
| Analysis Workspace の管理およびアクセスの要件を教えてください。 | 詳しくは、[管理要件](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。 |
| 分析ワークスペースを使用すると、データ収集に影響を与えますか。 | Analysis Workspace はレポート作成ツールなので、データ収集には影響しません。何が機能するかを確認するためにコンポーネントをプロジェクトに適当にドラッグしても、データに影響はありません。様々なディメンションと指標の組み合わせをワークスペースプロジェクトにドラッグして、利用可能な項目を確認してください。無効なコンポーネントを誤ってワークスペースプロジェクトにドラッグした場合や、手順を 1 つ戻したい場合は、Ctrl + Z キー（Windows）または Command + Z キー（Mac）を押して、最後におこなった操作を元に戻します。You can also start with a clean slate by clicking *[!UICONTROL Project]>[!UICONTROL New]*in the upper left menu. |
| Analysis Workspace プロジェクトには、レポートスイートはいくつ表示できますか。 | You can now create projects in Analysis Workspace with data from more [multiple report suites](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html). |
| Analysis Workspace はどのようにして実装しますか。 | 特別な実装は必要ありません。Analysis Workspace は、Analytics Standard または Premium を使用しているすべての企業で利用できます。ただし、コンテンツ（レポートスイートやプロジェクトコンポーネントなど）のほか、プロジェクトのキュレーションおよび共有には標準アクセス権限が適用されます。詳しくは、[管理およびアクセス要件](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。 |
| Analysis Workspace は Adobe Analytics の事前設定済みレポートを変更しますか。 | いいえ。環境が異なるので、Adobe Analytics の既存のレポートや事前設定されたレポートは変更されません。Analysis Workspace を使用する際も、標準の Reports &amp; Analytics および Report Builder のレポートを使用できます。 |
| Data Warehouse で Analysis Workspace を使用できますか。 | Analysis Workspace は、一括データエクスポートにはお勧めしません。これは、ダッシュボードのような分析プロジェクトを作成するビジュアライゼーションワークスペースです。 |
| Analysis Workspace のパフォーマンスを最適化するにはどうすればよいですか。 | 詳しくは、[パフォーマンスの最適化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)を参照してください。 |
| Analysis Workspace と Ad Hoc Analysis の機能の違いを教えてください。 | 詳しくは、[ Analysis Workspace と Ad Hoc Analysis の比較](/help/analyze/analysis-workspace/workspace-faq/adhocanalysis-vs-analysisworkspace.md). |

## トラブルシューティング

**指標をドラッグすると、「無効なデータ」と表示される。**

無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。代わりに、指標を並べて配置します。

**指標をドラッグすると、実際のデータは表示されず、ゼロのみが表示される。**

ワークスペースレポートの作成に成功したがデータがない場合は、次の項目を確認できます。

* 重複がレポートスイートをチェックし、データが入力されていることを確認します。
* レポートでセグメントを適用した場合、そのセグメント条件がどのデータとも一致しない可能性があります。 セグメントを削除するか、セグメント定義を調整してみてください。
* 右上隅の日付範囲を確認し、期待値に設定されていることを確認します。
* Navigate to your website and use the [Debugger](https://docs.adobe.com/content/help/ja-JP/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.