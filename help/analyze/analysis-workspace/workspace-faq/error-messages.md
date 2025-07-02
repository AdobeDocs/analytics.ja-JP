---
description: Analysis Workspaceのエラーとトラブルシューティングについて説明します。
title: Analysis Workspaceのトラブルシューティングでエラーが発生する
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: 0146d0798571d8589a74fb6d3fbbd574af224631
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 97%

---

# エラーとトラブルシューティング

Analysis Workspace の操作中に、その機能やパフォーマンスに影響を与えるエラーが発生することがあります。以下に、最も一般的なエラータイプ、エラーの発生理由および実行可能な最適化を示します。

## エラーメッセージ

Analysis Workspace の使用時に表示される可能性のある一般的なエラーメッセージを次に示します。

| エラーメッセージ | エラーが発生する理由 | 最適化 |
| --- | --- | --- |
| [!UICONTROL データビューで非常に大量のレポートが発生しています。後で再試行してください。] | 組織が特定のデータビューに対して同時に実行するリクエストが多すぎます。このエラーの原因となっているのは、API リクエスト、スケジュール済みプロジェクト、スケジュール済みレポート、スケジュール済みアラート、およびレポートリクエストを行う同時ユーザーです。 | データビューのリクエストやスケジュールを、1 日を通じて均等に配分します。<p>管理者は、[レポートアクティビティマネージャーを使用して、レポート処理能力を消費しているリクエストを特定しキャンセル](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)できます。</p> |
| [!UICONTROL  このレポートは複雑すぎます。Analysis Workspace レポート作成のベストプラクティスを確認してください。] | レポートリクエストが大きすぎるので、実行できません。このエラーの原因は、リクエストの複雑さによるタイムアウトです。 | リクエストを簡略化します。例えば、日付範囲を短縮したり、セグメント条件を簡略化したり、テーブルの一部の列や行を削除したりします。テーブルを別々のリクエストに分割することも検討してください。 |
| [!UICONTROL データビューは現在、レポート処理能力を超えています。リクエストを簡素化するか、後でもう一度試してください。] | 組織が特定のデータビューに対して同時に実行するリクエストが多すぎます。このエラーの原因となっているのは、API リクエスト、スケジュール済みプロジェクト、およびレポートリクエストを行う同時ユーザーです。 | データビューのリクエストやスケジュールを、1 日を通じて均等に配分します。 |
| [!UICONTROL システムエラーが発生しました。**[!UICONTROL ヘルプ／サポートチケットを送信]**&#x200B;でカスタマーケアのリクエストとエラーコードをログに記録します。] | アドビで問題が発生しています。この問題は解決する必要があります。 | エラーコードをカスタマーケアに送信してください。 |
| [!UICONTROL エラー500：ページの読み込みに失敗しました] | 会社の[ファイアウォール設定](/help/technotes/ip-addresses.md)など、ローカルネットワークに関する問題が、このエラーの原因の 1 つです。さらに、解決が必要な問題がアドビで発生している可能性があります。 | 数分後にもう一度ログインしてみてください。問題が解決しない場合は、EIM インスタンス ID コードをカスタマーケアに送信します。 |
| [!UICONTROL 列が多すぎるか事前設定された行が原因で、要求に失敗しました。] | テーブルに含まれるフリーフォームセル（行 x 列）が多すぎます。 | テーブルの列または行を削除するか、テーブルを個別のリクエストに分割することを検討します。 |


## トラブルシューティング

Analysis Workspace を使用している場合、以下の情報を使用して、いくつかの一般的な問題のトラブルシューティングを行うことができます。

| 問題 | トラブルシューティング方法 |
|---|---|
| 指標をドラッグすると、*無効なデータ*&#x200B;と表示されます。 | 無効なデータとは、レポートで使用されるディメンションと指標の組み合わせを使用してデータを返せないことを意味します。例えば、2 つの指標を重ね合わせて表示する方法がない場合、その方法ではデータとして返すことはできません。代わりに、指標を並べて配置します。 |
| 指標をドラッグすると、実際のデータが表示されず、ゼロのみが表示されます。 | Workspace レポートを正常に作成したのにデータがないという場合は、次の点を確認してください。<ul><li>レポートにセグメントを適用している場合、そのセグメント条件がどのデータとも一致しない可能性があります。セグメントを削除するか、セグメント定義を調整してみてください。</li><li>右上隅の日付範囲をチェックし、期待する値に設定されていることを確認します。</li><li>Web サイトに移動し、[デバッガー](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用してデータが収集されていることを検証します。</li></ul> |



<!--
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. <p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension that you are using. | Replace the dimension in your table with one that is compatible with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
-->