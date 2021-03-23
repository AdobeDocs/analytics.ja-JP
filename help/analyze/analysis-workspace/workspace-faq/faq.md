---
description: Workspace に関する FAQ
title: よくある質問と Workspace のトラブルシューティング
translation-type: ht
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: ht
source-wordcount: '523'
ht-degree: 100%

---


# よくある質問

| 質問 | 回答 |
|--- |--- |
| Analysis Workspace を使用するための前提条件を教えてください。 | [Adobe Experience Platform Launch を使用して Adobe Analytics にデータを送信する](/help/implement/launch/validate-publish-prod.md)：Analysis Workspace を使用するには、動作する実装が必要です。ツールを使用する前に、組織がアドビにデータを送信していることを確認します。DTM やレガシーの手動による実装など、他の実装も同様に機能できます。 |
| Analysis Workspace の管理およびアクセスの要件を教えてください。 | [管理要件](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。 |
| Analysis Workspace を使用するとデータ収集に影響が出ますか。 | Analysis Workspace はレポート作成ツールなので、データ収集には影響しません。何が機能するかを確認するためにコンポーネントをプロジェクトに適当にドラッグしても、データに影響はありません。様々なディメンションと指標の組み合わせをワークスペースプロジェクトにドラッグして、利用可能な項目を確認してください。無効なコンポーネントを誤ってワークスペースプロジェクトにドラッグした場合や、手順を 1 つ戻したい場合は、Ctrl + Z キー（Windows）または Command + Z キー（Mac）を押して、最後におこなった操作を元に戻します。左上のメニューで&#x200B;*[!UICONTROL プロジェクト]／[!UICONTROL 新規]*&#x200B;をクリックして、新しいスレートから始めることもできます。 |
| Analysis Workspace プロジェクトには、レポートスイートはいくつ表示できますか。 | [複数のレポートスイート](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html)のデータを使用して、Analysis Workspace でプロジェクトを作成できるようになりました。 |
| Analysis Workspace はどのようにして実装しますか。 | 特別な実装は必要ありません。Analysis Workspace は、Analytics Standard または Premium を使用しているすべての企業で利用できます。ただし、コンテンツ（レポートスイートやプロジェクトコンポーネントなど）のほか、プロジェクトのキュレーションおよび共有には標準アクセス権限が適用されます。詳しくは、[管理およびアクセス要件](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。 |
| Analysis Workspace は Adobe Analytics の事前設定済みレポートを変更しますか。 | いいえ。環境が異なるので、Adobe Analytics の既存のレポートや事前設定されたレポートは変更されません。Analysis Workspace を使用する際も、標準の Reports &amp; Analytics および Report Builder のレポートを使用できます。 |
| Data Warehouse で Analysis Workspace を使用できますか。 | Analysis Workspace は、一括データエクスポートにはお勧めしません。これは、ダッシュボードのような分析プロジェクトを作成するビジュアライゼーションワークスペースです。 |
| Analysis Workspace のパフォーマンスを最適化するにはどうすればよいですか。 | 詳しくは、[パフォーマンスの最適化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md)を参照してください。 |

## トラブルシューティング

**指標をドラッグすると、「無効なデータ」と表示される。**

無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。代わりに、指標を並べて配置します。

**指標をドラッグすると、実際のデータは表示されず、ゼロのみが表示される。**

ワークスペースレポートを正常に作成したのにデータがないという場合は、次の点を確認してください。

* レポートスイートを再度チェックし、データが入力されていることを確認します。
* レポートにセグメントを適用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。セグメントを削除するか、セグメント定義を調整してみてください。
* 右上隅の日付範囲をチェックし、期待する値に設定されていることを確認します。
* Web サイトに移動し、[デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja-JP)を使用してデータが収集されていることを検証します。