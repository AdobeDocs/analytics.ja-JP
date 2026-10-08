---
description: Analysis Workspace のエラーとトラブルシューティングについて説明します。
title: エラーとトラブルシューティング
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
TQID: 'https://experienceleague.adobe.com/Kr34CyT7YxRqKRdwpaLN-DZwHhLbaT663Gj-pc5Wd8s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 94%
---
# エラーとトラブルシューティング

Analysis Workspace の操作中に、その機能やパフォーマンスに影響を与えるエラーが発生することがあります。 以下に、最も一般的なエラータイプ、エラーの発生理由および実行可能な最適化を示します。

## エラーメッセージ

Analysis Workspace の使用時に表示される可能性のある一般的なエラーメッセージを次に示します。

| エラーメッセージ | エラーが発生する理由 | 最適化 |
| --- | --- | --- |
| [!UICONTROL レポートスイートで非常に大量のレポートが発生しています。 後で再試行してください。] | 組織が特定のレポートスイートに対して同時に実行するリクエストが多すぎます。 このエラーの原因となっているのは、API リクエスト、スケジュール済みプロジェクト、スケジュール済みレポート、スケジュール済みアラート、およびレポートリクエストをおこなう同時ユーザーです。 | レポートスイートのリクエストやスケジュールを、1 日を通じて均等に配分します。<p>管理者は、[レポートアクティビティマネージャーを使用して、レポート処理能力を消費しているリクエストを特定しキャンセル](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md)できます。</p> |
| [!UICONTROL  このレポートは複雑すぎます。 Analysis Workspace レポート作成のベストプラクティスを確認してください。] | レポートリクエストが大きすぎるので、実行できません。 このエラーの原因は、リクエストの複雑さによるタイムアウトです。 | リクエストを簡略化します。 例えば、日付範囲を短縮したり、セグメント条件を簡略化したり、テーブルの一部の列や行を削除したりします。 テーブルを別々のリクエストに分割することも検討してください。 |
| [!UICONTROL レポートスイートは現在、レポート処理能力を超えています。 リクエストを簡略化するか、後でもう一度試してください。] | 組織が特定のレポートスイートに対して同時に実行するリクエストが多すぎます。 このエラーの原因となっているのは、API リクエスト、スケジュール済みプロジェクト、およびレポートリクエストを行う同時ユーザーです。 | レポートスイートのリクエストやスケジュールを、1 日を通じて均等に配分します。 |
| [!UICONTROL システムエラーが発生しました。 **[!UICONTROL ヘルプ／サポートチケットを送信]**&#x200B;でカスタマーケアのリクエストとエラーコードをログに記録します。] | アドビ側で解決が必要な問題が発生しています。 | エラーコードをカスタマーケアに送信してください。 |
| [!UICONTROL エラー500：ページの読み込みに失敗しました] | 会社の[ファイアウォール設定](/help/technotes/ip-addresses.md)など、ローカルネットワークに関する問題が、このエラーの原因の 1 つです。 さらに、解決が必要な問題がアドビで発生している可能性があります。 | 数分後にもう一度ログインしてみてください。 問題が解決しない場合は、EIM インスタンス ID コードをカスタマーケアに送信してください。 |
| [!UICONTROL 列が多すぎるか事前設定された行が原因で、要求に失敗しました。] | テーブルに含まれるフリーフォームセル（行 x 列）が多すぎます。 | テーブルの列または行を削除するか、テーブルを個別のリクエストに分割することを検討します。 |


## トラブルシューティング

Analysis Workspaceを使用する場合は、以下の情報を使用して、一般的な問題のトラブルシューティングを行うことができます。

| 問題 | トラブルシューティング方法 |
|---|---|
| 指標をドラッグすると、*無効なデータ*&#x200B;と表示されます。 | 無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。 例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。 代わりに、指標を並べて配置します。 |
| 指標をドラッグすると、実際のデータが表示されず、ゼロのみが表示されます。 | Workspace レポートを正常に作成したのにデータがないという場合は、次の点を確認してください。<ul><li>レポートにセグメントを適用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。 セグメントを削除するか、セグメント定義を調整してみてください。</li><li>右上隅の日付範囲をチェックし、期待する値に設定されていることを確認します。</li><li>Web サイトに移動し、[Adobe Experience Platform Debugger](https://experienceleague.adobe.com/ja/docs/experience-platform/debugger/home)を使用して、データが収集されていることを検証します。</li></ul> |
