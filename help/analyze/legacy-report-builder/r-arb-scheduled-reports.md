---
description: スケジュールされたタスクマネージャーのフィールドの説明について説明します。
title: スケジュールされたタスクマネージャーについて
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 86%

---

# スケジュールされたタスクマネージャー

{{legacy-arb}}

[!UICONTROL スケジュールされたタスクマネージャー]では、受信者、スケジュールの詳細、ファイル形式と共に、既存の予定レポートのリストを表示できます。また、実行に失敗したスケジュール済みワークブックを再アクティブ化することもできます。

## 過去のスケジュールされたタスクの一時停止

2022年4月21日に、パフォーマンスと配信の最適化の一環として、Report Builder のスケジュールされたタスクに変更を加えました。これらの変更には、スケジュールされた配信の「x 回後に終了」機能の削除が含まれていました。代替案の検討や導入にさらなる時間の確保が必要であるとのお客様の要望に応えて、アドビでは、**2023年1月31日**&#x200B;まで限定的にこのオプションを復元することが決定されました。

引き続き、1 時間ごとのReport Builderタスクのスケジュールを設定し、最大 99 回発生した後にタスクを終了させることができます。 ロールバックは 1 時間ごとのタスクにのみ適用されることに注意してください。「x 回後に終了する」は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できません。

このオプションは、2023 年 1 月 31 日（PT）をもって廃止されることに注意してください。
その他の質問やサポートについては、Adobeカスタマーケアにお問い合わせください。

特に、この一時停止は、**2020年1月31日（PT）より前に作成されたすべてのタスク**&#x200B;に適用されます。タスク、ワークブックまたはデータは削除されません。2 年以上経過したタスクは一時停止され、スケジュールされたタスクはそれ以上送信されません。

送信を再開するタスクは、再アクティブ化できます。Report Builder にログインし、 [!UICONTROL スケジュールされたタスクマネージャー]を起動します。送信を再開するスケジュールされたタスクの「**[!UICONTROL 再アクティブ化]**」をクリックします。再アクティブ化されるタスクの有効期限は、有効期限が短い場合を除き、デフォルトで 18 か月になります。

また、作成日が 2 年未満で、現在の有効期限がない（または有効期限が 2 年を超える）タスクには、デフォルトで 18 か月の有効期限が適用されます。新しい有効期限は 2023年10月15日（PT）です。この有効期限は 18 か月未満に編集できますが、18 か月より長い期間には編集できません。有効期限が切れると、タスクは一時停止します。ただし、18 か月の新しい有効期限を指定してタスクを再アクティブ化することができます。タスク、ワークブックまたはデータは削除されません。

この一時停止の目的は、必要なタスクやワークブックに最適なパフォーマンスと配信を確保するために、スケジュールされたタスクデータベースを効果的に管理および維持することです。これは、今後の新しいガバナンスポリシーの役割を果たします。2023 年 1 月 31 日（PT）以降、すべてのタスクの有効期限は 18 か月になります。 18 か月後、期限切れのタスクは一時停止され、必要に応じて再アクティブ化できます。

## スケジュールされたタスクの設定

| フィールド | 説明 |
| --- | --- |
| **[!UICONTROL 「予定レポート」タブ]** | |
| [!UICONTROL レポート名] | スケジュールされたタスクの名前。 |
| [!UICONTROL メール / FTP] | 受信者のメールアドレスまたは FTP アドレス。**注意：**&#x200B;電子メールを選択すると、1 MB を超えるレポートは自動的に .zip ファイルとして電子メールに添付されます。この機能によって、添付ファイルのサイズを小さく保つことができます。この機能は無効にできません。 |
| [!UICONTROL 発行オプション] | [Power BI 発行オプション](https://experienceleague.adobe.com/docs/analytics/analyze/legacy-report-builder/publish-powerbi/power-bi.html?lang=ja)のいずれかが選択されている場合、この列には Power BI のリストが表示されます。 |
| [!UICONTROL スケジュール] | スケジュールされた配信のタイプ。 |
| [!UICONTROL ファイル形式] | Excel、PDF、HTML などのレポートの配信形式。 |
| [!UICONTROL 再アクティブ化] | スケジュールされているワークブックの実行が失敗した場合、Report Builder では 15 分ごとにさらに 2 度ワークブックの実行を試みます。3 回実行が失敗すると、Report Builder でスケジュールが無効になり、「再アクティブ化」ボタンが表示されます。ワークブックを再開すると、スケジュールされた配信が無効になった時刻から再開されます。<p>例えば、スケジュールされているワークブックが 14 日前に無効になっており、今日再開すると、実行されなかったすべての日に対して配信が実行されるため、14 回配信されることになります。配信が実行されなかった日に対してワークブックの配信を行わないようにするためには、スケジュールされたワークブックを削除してから、新しくスケジュールされたワークブックを作成します。<p>**メモ：**&#x200B;システム上でワークブックが無効になった理由がわからない場合は、ワークブックを再アクティブ化しないでください。トラブルシューティングを行うには、非アクティブ化されたワークブックをダウンロードし、クライアント側で更新します。エラーが表示されなければワークブックを再アクティブ化できると判断する、という方法が考えられます。 |
| [!UICONTROL 最後の送信] | レポートが最後に送信された日時。 |
| **「受信者」タブ** | |
| [!UICONTROL 受信者のメール] | レポート受信者のメールアドレス。 |
| [!UICONTROL レポート] | 各受信者に送信されたレポート。 |
| **「レポートの履歴」タブ** | |
| [!UICONTROL ファイル名] | スケジュールされたタスクの名前。 |
| [!UICONTROL 日付] | レポートが最後に送信された日時。 |
| [!UICONTROL ステータス] | レポートが送信されたかどうかを示すステータス。 |
| [!UICONTROL メール / FTP] | レポートの受信者のメールアドレスまたは FTP アドレス。 |
| [!UICONTROL ファイル形式] | Excel、PDF、HTML などのレポートの配信形式。 |
