---
description: Adobe Admin Consoleで Analytics ユーザーとそのアセットを管理します。
title: Analytics ユーザーとアセットの管理
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 6%

---

# 従来のユーザーアカウント、アセット、有効期限の管理

**[!UICONTROL 管理者 ]/[!UICONTROL  すべての管理者 ]/[!UICONTROL Analytics ユーザーと管理者]** を使用して、従来のユーザーアカウント、移行ステータス、有効期限データ、他のユーザーへのアセットの転送などを管理できます。

ユーザー画面には、現在のAdobe Analytics ユーザーのリストが次の列と共に表示されます。

| 列 | 説明 |
|---|---|
| [!UICONTROL ユーザー ID] | ユーザーがAdobe Analyticsへのログインに使用するユーザー ID。 |
| [!UICONTROL 名前] | ユーザーの名前。 |
| [!UICONTROL  移行ステータス ] | 従来のユーザーアカウントからEnterprise IDまたはAdobe IDへの移行ステータス。  ステータスは、Not initiated、Queued、Migrated のいずれかです。 |
| [!UICONTROL 電子メール] | ユーザのメール。 |
| [!UICONTROL  従来のログイン ] | 従来のログインのステータス。有効または無効にできます。 |
| [!UICONTROL 作成日] | Adobe Analyticsでユーザーアカウントが作成されたときのタイムスタンプ。 |
| [!UICONTROL  前回の Analytics アクセス ] | Adobe Analyticsへのユーザーアカウントの最新アクセスのタイムスタンプ。 |
| [!UICONTROL 有効期限] | ユーザーアカウントの有効期限。ユーザーアカウントの有効期限が切れていない場合は、「なし」を選択します。 |

![ユーザー](assets/users.png)

- 特定のユーザーを検索するには、「![ 検索 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)*タイトルで検索*」フィールドを使用します。
- 移行ステータスのリストをフィルタリングするには、「![ 山形記号 ](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg)**[!UICONTROL 移行ステータス]**」を選択します。
- 従来のログインステータスに基づいてリストをフィルタリングするには、「![ 山形記号 ](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL 従来のログイン]**」を選択します。
- 列の表示を変更するには、「![ 列設定 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」を選択し、ポップアップから列を選択します。

リストから 1 人または複数のユーザーを選択する際に、様々なアクションを適用できます。

| アクション | 説明 |
|---|---|
| ![ 移行 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) 移行 **** | 1 人以上のユーザーを Enterprise ID またはAdobe ID に移行できます。 |
| ![ カレンダーをロック ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg)**[!UICONTROL 有効期限を設定]** | 選択したユーザーが従来のAdobe Analytics ログインを使用する場合の有効期限を設定できます。  カレンダーポップアップを使用して日付を指定するには、日付を選択します。 「**[!UICONTROL 完了]**」を選択して、有効期限を確定します。 |
| ![ 資産の譲渡 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg)**[!UICONTROL 資産の譲渡]** | このアクションは、1 人のユーザーを選択した場合にのみ使用できます。 ユーザーが転送可能なアセットを持っている場合は、アカウント項目（ブックマーク、ダッシュボードなど）を選択できます。 「**[!UICONTROL 転送]**」を選択して、転送を完了します。<br/>![ 資産の譲渡 ](assets/transfer-assets.png) |
| ![ アカウントの削除 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)**[!UICONTROL アカウントの削除]** | 選択したアカウントの削除を確認するダイアログが表示されます。 「**[!UICONTROL OK]**」を選択して、アカウントを削除します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。 |
| ![CSV への書き出し ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg)**[!UICONTROL CSV への書き出し]** | このアクションを実行すると、選択したユーザーのコンマ区切りの値のリストと詳細（名前、移行ステータス、メールなど）を含むファイルが直ちにダウンロードされます。 |

