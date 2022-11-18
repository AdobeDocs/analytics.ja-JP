---
description: Workspace に関する FAQ
title: よくある質問と Workspace のトラブルシューティング
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
source-git-commit: 5bad2982cc8883701be3c63a6ca179933fb59d2a
workflow-type: ht
source-wordcount: '554'
ht-degree: 100%

---

# よくある質問

+++Analysis Workspace を使用するための前提条件は何ですか？
[Adobe Analytics 拡張機能を使用して Adobe Analytics にデータを送信](/help/implement/launch/validate-publish-prod.md)：Analysis Workspace を使用するには、有効な実装が必要です。このツールを使用する前に、組織がアドビにデータを送信することを確認します。従来の手動実装など、他の実装も機能します。
+++

+++Analysis Workspace の管理とアクセスの要件は何ですか？
[管理要件](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。
+++

+++Analysis Workspace を使用すると、データ収集に影響が出ますか？
Analysis Workspace はレポート作成ツールなので、データ収集には影響しません。何が機能するかを確認するためにコンポーネントをプロジェクトに適当にドラッグしても、データに影響はありません。様々なディメンションと指標の組み合わせを Workspace プロジェクトにドラッグして、利用可能な項目を確認してください。無効なコンポーネントを誤って Workspace プロジェクトにドラッグした場合や、手順を 1 つ戻したい場合は、Ctrl + Z キー（Windows）または Command + Z キー（Mac）を押して、最後におこなった操作を元に戻します。左上のメニューで**[!UICONTROL プロジェクト]**／**[!UICONTROL 新規]**をクリックして、新しいスレートから始めることもできます。
+++

+++Analysis Workspace プロジェクトに表示できるレポートスイートはいくつですか？
[複数のレポートスイート](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=ja)のデータを使用して、Analysis Workspace でプロジェクトを作成できるようになりました。
+++

+++Analysis Workspace を実装するにはどうすればよいですか？
特別な実装は必要ありません。Analysis Workspace は、Analytics Standard または Premium を使用しているすべての企業で利用できます。ただし、コンテンツ（レポートスイートやプロジェクトコンポーネントなど）のほか、プロジェクトのキュレーションおよび共有には標準アクセス権限が適用されます。詳しくは、 [管理およびアクセス要件](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md) を参照してください。
+++

+++Analysis Workspace は Adobe Analytics の事前設定済みレポートを変更しますか？
いいえ。環境が異なるので、Adobe Analytics の既存のレポートや事前設定されたレポートは変更されません。Analysis Workspace を使用する際も、標準の Reports &amp; Analytics および Report Builder のレポートを使用できます。
+++

+++Data Warehouse に Analysis Workspace を使用できますか？
Analysis Workspace は、一括データエクスポートにはお勧めしません。これは、ダッシュボードのような分析プロジェクトを作成するビジュアライゼーションワークスペースです。
+++

+++Analysis Workspace のパフォーマンスを最適化するにはどうすればよいですか？
[パフォーマンスの最適化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md) を参照してください。
+++

+++データは Analysis Workspace プロジェクトにどのように取り込まれますか？
次のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/31072/?quality=12)

+++

+++ Workspace の使用状況を追跡するにはどうすればよいですか？

Analysis Workspace の使用ログのトラッキングに関する次のビデオをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/29768/?quality=12)

+++

+++指標をドラッグすると、「無効なデータ」と表示されます。この問題を解決するにはどうすればよいですか？
無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。代わりに、指標を並べて配置します。
+++

+++指標をドラッグすると、実際のデータが表示されず、ゼロのみが表示されます。この問題をトラブルシューティングするにはどうすればよいですか？
ワークスペースレポートを正常に作成したのにデータがないという場合は、次の点を確認してください。

* レポートスイートを再度チェックし、データが入力されていることを確認します。
* レポートにセグメントを適用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。セグメントを削除するか、セグメント定義を調整してみてください。
* 右上隅の日付範囲をチェックし、期待する値に設定されていることを確認します。
* Web サイトに移動し、[デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用してデータが収集されていることを検証します。
+++
