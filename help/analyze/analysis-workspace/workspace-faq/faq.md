---
description: Analysis Workspace に関するよくある質問への回答を入手します。
title: よくある質問
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
TQID: https://experienceleague.adobe.com/Cp7KvN1Y7Mxr4iGWNF08TYBzJWqhVWVSHApX0989lZ4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c069c44e-5426-4c1a-accc-8028662f2fdeid: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 598
ht-degree: 83%

---

# よくある質問

+++Analysis Workspace を使用する前提条件を教えてください。
[Adobe Analytics 拡張機能を使用して Adobe Analytics にデータを送信](/help/implement/launch/validate-publish-prod.md)：Analysis Workspace を使用するには、有効な実装が必要です。 このツールを使用する前に、組織がアドビにデータを送信することを確認します。 従来の手動実装など、他の実装も機能します。
+++

+++Analysis Workspace の管理およびアクセスの要件を教えてください。
[管理要件](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)を参照してください。
+++

+++Analysis Workspace を使用するとデータ収集に影響が出ますか。
Analysis Workspace はレポート作成ツールなので、データ収集には影響しません。 何が機能するかを確認するためにコンポーネントをプロジェクトに適当にドラッグしても、データに影響はありません。 様々なディメンションと指標の組み合わせを Workspace プロジェクトにドラッグして、利用可能な項目を確認してください。 無効なコンポーネントを誤って Workspace プロジェクトにドラッグした場合や、手順を 1 つ戻したい場合は、Ctrl + Z キー（Windows）または Command + Z キー（Mac）を押して、最後におこなった操作を元に戻します。 左上のメニューで&#x200B;**[!UICONTROL プロジェクト]**／**[!UICONTROL 新規]**&#x200B;をクリックして、新しいスレートから始めることもできます。
+++

+++Analysis Workspace プロジェクトには、レポートスイートはいくつ表示できますか。
[複数のレポートスイート](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md)のデータを使用して、Analysis Workspace でプロジェクトを作成できるようになりました。
+++

+++Analysis Workspaceを導入する方法？
特別な実装は必要ありません。 Analysis Workspaceは、Analytics StandardまたはPremiumを使用しているすべての企業で利用できます。 ただし、コンテンツに対する標準的な権限（レポートスイートやプロジェクトコンポーネントなど）が適用され、プロジェクトのキュレーションと共有に使用されます。 詳しくは、 [管理およびアクセス要件](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md) を参照してください。
+++

+++Data WarehouseではAnalysis Workspaceを使用できますか？
Analysis Workspaceの一括データ書き出しはお勧めしません。 ダッシュボードのような分析プロジェクトを作成するビジュアライゼーションワークスペースです。
+++

+++Analysis Workspace のパフォーマンスを最適化するにはどうすればよいですか。

詳しくは、 [パフォーマンスの最適化](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md) を参照してください。

+++

+++データは Analysis Workspace プロジェクトにどのように取り込まれますか？

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace へのデータ](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/understanding-how-data-gets-into-your-analysis-workspace-project){target="_blank"}を参照してください。

+++

+++Workspace の使用状況を追跡するにはどうすればよいですか？

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ログトラッキング](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/logs/usage-log-tracking-for-analysis-workspace){target="_blank"}を参照してください。

+++

+++指標をドラッグすると、「無効なデータ」と表示されます。 この問題を解決するにはどうすればよいですか？

無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。 例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。 代わりに、指標を並べて配置します。

+++

+++指標をドラッグすると、実際のデータが表示されず、ゼロのみが表示されます。 この問題をトラブルシューティングするにはどうすればよいですか？

ワークスペースレポートを正常に作成したのにデータがないという場合は、次の点を確認してください。

* レポートスイートを再度チェックし、データが入力されていることを確認します。
* レポートにセグメントを適用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。 セグメントを削除するか、セグメント定義を調整してみてください。
* 右上隅の日付範囲をチェックし、期待する値に設定されていることを確認します。
* Web サイトに移動し、[デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用してデータが収集されていることを検証します。


+++

+++読み取り専用ユーザーとして、Analysis Workspace でどのようなアクションを実行できますか？
プロジェクトを読み取り専用として共有する際、すべての編集機能が完全に無効になり、受信者はドロップダウンメニューを変更して、定義済みの方法でパネルにフィルターを適用することしかできません。
+++
