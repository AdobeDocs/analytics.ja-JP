---
description: Analysis Workspace プロジェクトを直接またはスケジュールに従ってメール配信で送信する方法について説明します。
keywords: Analysis Workspace
title: プロジェクトの送信とスケジュール
feature: Curate and Share
role: User, Admin
exl-id: 2d6854f7-8954-4d55-b2be-25981cfb348b
source-git-commit: 61fcafa0e2e6cb71d9b594984e9a0c71a76c13e4
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 25%

---

# プロジェクトの送信とスケジュール

Adobe Analytics プロジェクトをファイルとして、選択したユーザーにメールで送信できます。 アドホックでファイルを送信することも、スケジュールに従って送信するようにファイルを設定することもできます。

ファイルを送信する際は、次の点を考慮してください。

* ファイルは CSV 形式または PDF 形式で送信できます。

* プロジェクトに適用されたタグは、書き出しに自動的に適用されます。

[&#x200B; 書き出しの概要 &#x200B;](/help/export/home.md) に示すように、Adobe Analytics データを書き出すその他の方法も使用できます。

![ファイルを送信](assets/send-file.png)

## ファイルを送信

メールで受信者にアドホック形式のファイルを送信するには：

1. **[!UICONTROL 共有 &#x200B;]/[!UICONTROL &#x200B; ファイルを送信]** を選択します。
1. 次のいずれかのファイルタイプを指定します。
   * [!UICONTROL **CSV**]：プレーンテキストデータが必要な場合は、このオプションを選択します。
   * [!UICONTROL **PDF**]：ダウンロードしたファイルに、プロジェクト内に表示されているすべてのテーブルとビジュアライゼーションを含める場合は、このオプションを選択します。
1. （任意） **[!UICONTROL 説明]** を使用して、メールに含める説明を追加します。
1. 受信者またはグループを追加します。メールアドレスを入力することもできます。
1. （任意） **[!UICONTROL スケジュールオプションを表示]** を選択して [&#x200B; ファイルの書き出しをスケジュール &#x200B;](#schedule-file-export) します。
1. **[!UICONTROL 今すぐ送信]** をクリックします。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。


## ファイルの書き出しをスケジュール {#schedule}

メールで受信者にスケジュールに従ってファイルを送信するには：

1. **[!UICONTROL 共有 &#x200B;]/[!UICONTROL &#x200B; ファイル書き出しをスケジュール]** を選択します。
1. 次のいずれかのファイルタイプを指定します。
   * [!UICONTROL **CSV**]：プレーンテキストデータが必要な場合は、このオプションを選択します。
   * [!UICONTROL **PDF**]：ダウンロードしたファイルに、プロジェクト内に表示されているすべてのテーブルとビジュアライゼーションを含める場合は、このオプションを選択します。
1. （任意） **[!UICONTROL 説明]** を使用して、メールに含める説明を追加します。
1. 受信者またはグループを追加します。メールアドレスを入力することもできます。
1. （Healthcare Shield のお客様のみ）パスワードを入力して [&#x200B; 予定レポートをパスワードで保護 &#x200B;](#password-protect-a-new-scheduled-project) ます。
1. **[!UICONTROL スケジュールオプションを表示]** が選択されていることを確認します。
1. **[!UICONTROL 頻度]** を選択します。 次のいずれかを選択できます。

   | 頻度 | オプション |
   |---|---|
   | **[!UICONTROL 1 時間ごとに送信]** | **[!UICONTROL 時間数ごとに送信]** の値を入力します。 |
   | **[!UICONTROL 毎日送信]** | **[!UICONTROL 1 日の頻度]**:**[!UICONTROL 毎日送信]**、**[!UICONTROL 平日ごとに送信]**、または **[!UICONTROL カスタム頻度]** を選択します。<br/> 「カスタム頻度 **[!UICONTROL を選択した場合は、]** 日数ごとに送信 **[!UICONTROL の値を入力し]** す。 |
   | **[!UICONTROL 毎週送信]** | **[!UICONTROL 週数ごとに送信]** の値を入力します。 **[!UICONTROL 曜日]** を選択します。 |
   | **[!UICONTROL 毎月曜日に送信]** | **[!UICONTROL 曜日]** と **[!UICONTROL 週]** を選択します。 |
   | **[!UICONTROL 毎月日ごとに送信]** | **[!UICONTROL その月のこの日に送信]** から値を選択します。 |
   | **[!UICONTROL 毎年、その月の日ごとに送信]** | 「**[!UICONTROL 曜日]**」を選択し、「**[!UICONTROL 週]**」を選択して、「**[!UICONTROL 月]**」を選択します。 |
   | **[!UICONTROL 特定の日付で毎年送信]** | **[!UICONTROL 月]** を選択し、**[!UICONTROL その月のこの日に送信]** から値を選択します。 |

1. 開始日を **[!UICONTROL 開始日]** に入力します。 または、「![&#x200B; カレンダー &#x200B;](/help/assets/icons/Calendar.svg)」を選択して、カレンダーから開始日を選択します。

1. 終了日を **[!UICONTROL 終了日]** に入力します。 または、「![&#x200B; カレンダー &#x200B;](/help/assets/icons/Calendar.svg)」を選択して、カレンダーから終了日を選択します。
1. 「**[!UICONTROL スケジュールに従って送信]**」を選択します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。


## スケジュール済みプロジェクトマネージャー {#manager}

スケジュールされたAnalysis Workspace プロジェクトは、**[!UICONTROL コンポーネント]**/**[!UICONTROL スケジュールされたプロジェクト]** を使用して、メインインターフェイスから管理できます。 詳しくは、[スケジュール済みプロジェクト](/help/components/scheduled-projects-manager.md)を参照してください。

<!--
# Schedule projects

From the Workspace **Share menu**, you can send Analysis Workspace projects using email to selected recipients. Files can be sent in CSV or PDF format. After you share scheduled projects, you can edit the schedule settings to modify the frequency, receipient list, or file type using the Scheduled Projects manager.

## Send file now

To send a file immediately to recipients via email:

1. Click **[!UICONTROL Share] > [!UICONTROL Export file]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Add a description to include in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. Click **[!UICONTROL Send Now]**.
1. (Optional) Click **[!UICONTROL Show scheduling options]** to specify a delivery schedule.

![Send file now](assets/send-file-now.png)

## Send file on schedule

To send a file on a recurring schedule to recipients via email:

1. Click **[!UICONTROL Share] > [!UICONTROL Schedule file export]**.
1. Specify the file type (CSV or PDF).
1. (Optional) Add a description that will be included in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. Specify the range the schedule should be delivered over by modifying Starting on and Ending on inputs. The end date must be within a year from the day the schedule is created or modified.
1. Specify the delivery frequency. Each frequency allows for different customizations. 
1. Click **[!UICONTROL Send on schedule]**.

![](assets/send-on-schedule.png)

## Manage scheduled projects

When you manage scheduled projects, you can edit and delete recurring project schedules:

*  Change the file type (.csv or PDF)
*  Update the project description
*  Add or remove recipients
*  Change the frequency


Scheduled Analysis Workspace projects can be managed under **Analytics > Components > Scheduled Projects**.

For more information, see [Scheduled projects](/help/components/scheduled-projects-manager.md)
-->
