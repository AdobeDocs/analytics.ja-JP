---
title: データフィードジョブの管理
description: データフィードで個々のジョブを管理する方法について説明します。 インターフェイスを移動し、フィルターと検索を使用して、列定義を検索します。
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
TQID: 'https://experienceleague.adobe.com/4ACex-y-w3ppGhC1tRX8qH4WeU1NT9ubcJBlhSh9sY0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
subfeature_v2: id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 545
ht-degree: 23%

---

# データフィードジョブの管理 {#manage-data-feed-jobs}

ジョブは、圧縮ファイルを出力する個々のタスクです。 ジョブはフィードによって作成および管理されます。

データフィードごとにジョブ履歴を表示したり、ジョブを再送信したり、ジョブを再処理したりできます。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_job_history"
>title="データフィードジョブ履歴"
>abstract="このページでは、特定のデータフィードのデータフィードジョブのリストを表示できます。 リクエスト ID またはリクエスト期間の開始日でジョブを検索します。 使用可能な列には、各ジョブに関する情報が表示されます。 同じデータでジョブを再送信したり、ジョブのソースデータを再送信前に再処理することもできます。"

<!-- markdownlint-enable MD034 -->

## データフィードのジョブ履歴の表示

特定のデータフィードのデータフィードのジョブのリストと、各ジョブに関する情報を表示できます。

データフィードのジョブ履歴を表示するには：

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。

1. 右上にある 9 つの正方形のアイコンを選択し、「[!UICONTROL **Analytics**]」を選択します。

1. 上部ナビゲーションバーで、[!UICONTROL **管理者**]／[!UICONTROL **データフィード**]&#x200B;に移動します。

   アクセス権のあるすべてのレポートスイートのデータフィードが表示されます。 または、フィードが設定されていない場合、ページに「**[!UICONTROL データフィードを作成]**」ボタンが表示されます。

   ![ データフィードマネージャー](assets/data-feed-manager.png)

1. 表示するジョブを含むデータフィードの横にあるチェックボックスをオンにし、[!UICONTROL **ジョブ履歴**]&#x200B;を選択します。

   データフィードのジョブ履歴が表示され、使用可能な列に各ジョブに関する情報が表示されます。

1. （オプション）テーブル内の表示列を調整するには、右上の列アイコン ![列アイコン ](assets/customize-columns-icon.png)を選択し、テーブルをカスタマイズ ダイアログで、表示する各列を選択し、非表示にする各列の選択を解除します。

   次の列を表示できます。

   * **[!UICONTROL リクエスト期間が開始]**

   * **[!UICONTROL リクエスト期間の終了]**

   * **[!UICONTROL スケジュール済み]**

   * **[!UICONTROL 開始]**

   * **[!UICONTROL 完了]**

   * **[!UICONTROL 実行#]**

   * **[!UICONTROL ステータス]**

   * **[!UICONTROL エラーコード]**

   * **[!UICONTROL エラーメッセージ]**

## データフィードのジョブの再送信

データフィードジョブを再送信すると、ファイルが最初に送信されたときと同じデータと処理でデータフィードファイルが再度送信されます。 または、[ データフィードジョブを再処理することもできます](#reprocess-data-feed-jobs)。

1つ以上のデータフィードのジョブを再送信するには：

1. Adobe Analytics で、[!UICONTROL **管理者**]／[!UICONTROL **データフィード**]&#x200B;を選択します。

1. 再送信するジョブを含むデータフィードの横にあるチェックボックスをオンにし、[!UICONTROL **ジョブ履歴**]&#x200B;を選択します。

1. （オプション）検索フィールドで、「リクエスト ID」または「リクエスト期間の開始日」で検索して、データフィードのジョブのリストを検索します。

1. 1つ以上のデータフィードジョブの横にあるチェックボックスを選択し、**[!UICONTROL 再送信]**&#x200B;を選択します。<!-- What does the status need to be? Error, ... -->

   ![ データフィードの再処理ジョブ ](assets/data-feed-job-resend.png)

## データフィードのジョブの再処理

データフィードジョブを再処理すると、データフィードジョブのソースデータが再処理され、再処理されたデータとともに再送信されます。 または、[ データフィードジョブを再送信することもできます](#resend-data-feed-jobs)。

1つ以上のデータフィードのジョブを再処理するには：

1. Adobe Analytics で、[!UICONTROL **管理者**]／[!UICONTROL **データフィード**]&#x200B;を選択します。

1. 再処理するジョブを含むデータフィードの横にあるチェックボックスをオンにし、[!UICONTROL **ジョブ履歴**]&#x200B;を選択します。

1. （オプション）検索フィールドで、「リクエスト ID」または「リクエスト期間の開始日」で検索して、データフィードのジョブのリストを検索します。

1. 1つ以上のデータフィードジョブの横にあるチェックボックスを選択し、**[!UICONTROL 再処理]**&#x200B;を選択します。<!-- What does the status need to be? Error, ... -->

   ![ データフィードの再処理ジョブ ](assets/data-feed-job-reprocess.png)
