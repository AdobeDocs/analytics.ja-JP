---
description: 組織全体の予定レポートを表示および管理します。
title: スケジュール済みプロジェクトマネージャー
feature: Admin Tools
source-git-commit: 8d0cf795b0366b2797fa0574ae9faaffb76b005e
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 74%

---

# スケジュールされたプロジェクト

スケジュールされた Analysis Workspace プロジェクトは、 **Analytics／コンポーネント／スケジュールされたプロジェクト** で管理できます。

スケジュールされたプロジェクトを管理する場合、定期的なプロジェクトスケジュールを編集および削除できます。 検索バーまたは左側のパネルのフィルターオプションを使用して、スケジュールを検索します。次の条件でフィルターできます。 [!UICONTROL タグ], [!UICONTROL 所有者], [!UICONTROL お気に入力]など。

![](assets/scheduled-project-manager2.png)

## 使用可能な列

| フィールド | 説明 |
| --- | --- |
| [!UICONTROL お気に入り] | 星アイコンを選択すると、このスケジュールがお気に入りになります。 |
| [!UICONTROL スケジュール ID] | この ID は、主にデバッグ目的で使用されます。 |
| [!UICONTROL タイトルと説明] | このプロジェクトのタイトルと説明です。 |
| [!UICONTROL 所有者] | プロジェクトを作成し所有しているユーザー。 |
| [!UICONTROL タグ] | （任意）タグ付けは、プロジェクトを整理するのに適した方法です。すべてのユーザーがタグを作成し、1 つ以上のタグをプロジェクトに適用できます。ただし、タグを表示できるのは、自分が所有しているプロジェクトか、自分と共有されているプロジェクトに限られます。 |
| [!UICONTROL 配信先] | このスケジュールされたプロジェクトの受信者。 |
| [!UICONTROL 有効期限] | スケジュールされた任意のプロジェクト頻度に対して、1 年以内の有効期限を設定できます。 |
| [!UICONTROL 頻度] | このスケジュールされたプロジェクトを受信者に送信する頻度。 |
| [!UICONTROL 実行時間] | このスケジュールされたプロジェクトが送信される時刻。 |
| [!UICONTROL クエリ数] | このプロジェクトに対するクエリの数。 |

## 一般的なアクション

スケジュール済みプロジェクトマネージャーでの一般的な操作は次のとおりです。

| アクション | 説明 |
|---|---|
| **[!UICONTROL 編集]** | 配信設定を更新するスケジュールのタイトルを選択します。 |
| **[!UICONTROL 削除]** | リストでスケジュール済みのプロジェクトを選択し、メニューから「削除」をクリックします。これにより、プロジェクトで選択したスケジュールが削除されます。プロジェクト自体は削除されません。 |
| **[!UICONTROL タグ]** | リストでスケジュール済みのプロジェクトを選択し、「タグ」または「承認」を選択してスケジュールを整理し、検索しやすくします。 |
| **[!UICONTROL 失敗スケジュールを表示]** | 左側のパネル／その他のフィルター／失敗に移動して、失敗したスケジュールを表示します。 |
| **[!UICONTROL 期限切れスケジュールを表示]** | 左側のパネル／その他のフィルター／期限切れに移動して、期限切れのスケジュールを表示します。新しい配信スケジュールを設定するには、スケジュールのタイトルをクリックします。 |
| **[!UICONTROL スケジュール ID を表示]** | 右上の列のオプションに移動し、表にスケジュール ID 列を追加します。スケジュール ID は、多くの場合デバッグに役立ちます。 |

スケジュール済みプロジェクトマネージャーには、特定のユーザーが作成した項目が表示されます。 ユーザーアカウントがアプリケーションで無効になっている場合、予定されたすべての配信が停止されます。スケジュールされたプロジェクトの所有権は、以下の新しいユーザーに転送できます。 **管理者** > **Analytics ユーザーおよびアセット** > **アセットを転送**.