---
description: Adobe Admin ConsoleでAnalytics ユーザーとそのアセットを管理します。
title: Analytics ユーザーとアセットの管理
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
TQID: 'https://experienceleague.adobe.com/d8CK9Vf-eaEU6P9386J1eO-JpD5u4l3VoqRcMwvXcW0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 9%

---

# レガシーユーザーアカウント、アセット、有効期限の管理

**[!UICONTROL 管理者] > [!UICONTROL すべての管理者] > [!UICONTROL Analytics ユーザーと管理者]**&#x200B;を使用して、レガシーユーザーアカウント、移行ステータス、有効期限データ、他のユーザーへのアセットの転送などを管理できます。

「ユーザー」画面には、現在のAdobe Analytics ユーザーのリストが表示され、次の列が表示されます。

| 列 | 説明 |
|---|---|
| [!UICONTROL ユーザー ID] | Adobe Analyticsへのログインに使用するユーザーID。 |
| [!UICONTROL 名前] | ユーザーの名前。 |
| [!UICONTROL 移行ステータス &#x200B;] | レガシーユーザーアカウントからEnterprise IDまたはAdobe IDへの移行のステータス。  ステータスは、「未開始」、「キュー」または「移行」にできます。 |
| [!UICONTROL 電子メール] | ユーザのメール。 |
| [!UICONTROL 従来のログイン &#x200B;] | 有効または無効にできるレガシーログインのステータス。 |
| [!UICONTROL 作成日] | Adobe Analyticsでユーザーアカウントが作成された時点。 |
| [!UICONTROL 最後のAnalytics アクセス &#x200B;] | Adobe Analyticsへのユーザーアカウントの最新アクセスのタイムスタンプ， |
| [!UICONTROL 有効期限] | ユーザーアカウントの有効期限、またはユーザーアカウントが期限切れでない場合は「なし」の日付。 |

![ユーザー](assets/users.png)

- 特定のユーザーを検索するには、「![検索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *タイトルで検索*」フィールドを使用します。
- 移行ステータスのリストをフィルタリングするには、![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL 移行ステータス]**&#x200B;を選択します。
- レガシーログインのステータスに関するリストをフィルタリングするには、![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL レガシーログイン]**&#x200B;を選択します。
- 列の表示を変更するには、![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)を選択し、ポップアップから列を選択します。

リストから1人以上のユーザーを選択する際に、様々なアクションを適用できます。

| アクション | 説明 |
|---|---|
| ![移行](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL 移行]** | 1人以上のユーザーをEnterprise IDまたはAdobe IDに移行できます。 |
| ![&#x200B; カレンダーがロックされています](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL 有効期限を設定]** | 選択したユーザーに従来のAdobe Analytics ログインを使用するための有効期限を設定できます。  カレンダーのポップアップを使用して日付を指定する日付を選択します。 **[!UICONTROL 完了]**&#x200B;を選択して、有効期限を確認します。 |
| ![&#x200B; アセットの転送](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL アセットの転送]** | このアクションは、1人のユーザーを選択する場合にのみ使用できます。 転送可能なアセットがユーザーにある場合は、アカウント項目（ブックマーク、ダッシュボードなど）を選択できます。 「**[!UICONTROL 転送]**」を選択して、転送を完了します。<br/>![&#x200B; アセットの転送](assets/transfer-assets.png) |
| ![&#x200B; アカウントの削除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL アカウントの削除]** | 選択したアカウントの削除を確認するダイアログが表示されます。 アカウントを削除するには、**[!UICONTROL OK]**&#x200B;を選択します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。 |
| ![CSVに書き出し](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL CSVに書き出し]** | このアクションは、選択したユーザーのコンマ区切りの値リストとその詳細（名前、移行ステータス、電子メールなど）を含むファイルを即座にダウンロードします。 |

