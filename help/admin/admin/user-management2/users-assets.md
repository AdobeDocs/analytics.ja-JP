---
description: Adobe Admin Consoleで Analytics ユーザーとそのアセットを管理します。
title: Analytics ユーザーとアセットの管理
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
source-git-commit: 869b44b826de5cb35d13000133092397cb16ccaa
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 4%

---

# 従来のユーザーアカウント、アセット、有効期限の管理

従来のユーザーアカウント、移行ステータス、有効期限データ、他のユーザーへのアセットの転送などを管理できます。 **[!UICONTROL Admin] > [!UICONTROL すべての管理者] >  [!UICONTROL Analytics ユーザーおよび管理者]**.

ユーザー画面には、現在のAdobe Analytics ユーザーのリストが次の列と共に表示されます。

| 列 | 説明 |
|---|---|
| [!UICONTROL ユーザー ID] | ユーザーがAdobe Analyticsへのログインに使用するユーザー ID。 |
| [!UICONTROL 名前] | ユーザーの名前。 |
| [!UICONTROL 移行ステータス] | 従来のユーザーアカウントからEnterprise IDまたはAdobe IDへの移行ステータス。  ステータスは、Not initiated、Queued、Migrated のいずれかです。 |
| [!UICONTROL 電子メール] | ユーザのメール。 |
| [!UICONTROL 従来のログイン] | 従来のログインのステータス。有効または無効にできます。 |
| [!UICONTROL 作成日] | Adobe Analyticsでユーザーアカウントが作成されたときのタイムスタンプ。 |
| [!UICONTROL 前回の Analytics アクセス] | Adobe Analyticsへのユーザーアカウントの最新アクセスのタイムスタンプ。 |
| [!UICONTROL 有効期限] | ユーザーアカウントの有効期限。ユーザーアカウントの有効期限が切れていない場合は、「なし」を選択します。 |

![ユーザー](assets/users.png)

- 特定のユーザーを検索するには、を使用します ![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *タイトルで検索* フィールド。
- 移行ステータスのリストをフィルタリングするには、以下を選択します ![山形](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL 移行ステータス]**.
- 従来のログインステータスに基づいてリストをフィルタリングするには、次を選択します。 ![山形](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL 従来のログイン]**.
- 列の表示を変更するには、 ![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) ポップアップから列を選択します。

リストから 1 人または複数のユーザーを選択する際に、様々なアクションを適用できます。

| アクション | 説明 |
|---|---|
| ![移行](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL 移行]** | 1 人以上のAdobeを Enterprise ID またはユーザー ID に移行できます。 |
| ![カレンダーがロックされました](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL 有効期限を設定]** | 選択したユーザーが従来のAdobe Analytics ログインを使用する場合の有効期限を設定できます。  カレンダーポップアップを使用して日付を指定するには、日付を選択します。 を選択 **[!UICONTROL 完了]** 有効期限を確認します。 |
| ![アセットを転送](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL アセットを転送]** | このアクションは、1 人のユーザーを選択した場合にのみ使用できます。 ユーザーが転送可能なアセットを持っている場合は、アカウント項目（ブックマーク、ダッシュボードなど）を選択できます。 を選択 **[!UICONTROL 転送]** 転送を完了します。<br/>![アセットを転送](assets/transfer-assets.png) |
| ![アカウントの削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL アカウントの削除]** | 選択したアカウントの削除を確認するダイアログが表示されます。 を選択 **[!UICONTROL OK]** をクリックしてアカウントを削除します。 を選択 **[!UICONTROL キャンセル]** をキャンセルします。 |
| ![CSV に書き出し](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL CSV に書き出し]** | このアクションを実行すると、選択したユーザーのコンマ区切りの値のリストと詳細（名前、移行ステータス、メールなど）を含むファイルが直ちにダウンロードされます。 |

