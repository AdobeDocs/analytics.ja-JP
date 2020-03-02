---
description: ダッシュボードマネージャーを使用して、ダッシュボードのコピー、共有、アーカイブ、および配信スケジュールの設定を行います。
subtopic: Dashboards
title: ダッシュボードマネージャー
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: 92eaaeafdd587febcfe7fe60f696baca0691b4bc

---


# ダッシュボードマネージャー

ダッシュボードマネージャーを使用して、ダッシュボードのコピー、共有、アーカイブ、および配信スケジュールの設定を行います。

>[!IMPORTANT]
>
>ダッシュボードマネージャを使用する場合は、1人のユーザーに対して300個以下のダッシュボードを使用することをお勧めします。 また、マネージャーがすべての共有ダッシュボードを下に読み込むので、ダッシュボードの共有は慎重に行ってください。

## ダッシュボードマネージャー

ダッシュボードマネージャーを使用して、ダッシュボードのコピー、共有、アーカイブ、および配信スケジュールの設定を行います。

Click **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| 要素 | 説明 |
|--- |--- |
| 共有 | ダッシュボードが共有されているかどうかを示します。 |
| 日時指定 | ダッシュボードの配信スケジュールを設定できます。 |
| 保存レポートを閲覧 | この機能は使用できなくなりました。 |
| 閲覧ユーザーを選択 | ダッシュボードを共有できます。 |
| 管理 | ダッシュボードを編集、コピー、削除できます。 |

## 共有ダッシュボードの管理

共有ダッシュボードの管理オプションの使い方を説明します。

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], locate the shared dashboard (or legacy dashboard) you want to manage and choose one or more of the following options:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> オプション </th> 
  <th class="chdeschd"> 説明 </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>保存レポートを閲覧</strong></td> 
  <td class="chdesc stentry"> この機能は使用できなくなりました。 </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>ダッシュボードプレイヤー</strong></td> 
  <td class="chdesc stentry"> <p>SiteCatalyst 14 サーバーは、ダッシュボードプレイヤーのデータリクエストに応答しなくなります。ダッシュボードプレイヤーに現在表示されているダッシュボードには、標準的な Reports &amp; Analytics インターフェイスからアクセスできます。また、これらのダッシュボードをリアルタイムダッシュボードとして再作成することもできます。リアルタイムダッシュボードは、連続表示に対応するよう特別に設計されています。リアルタイムダッシュボードにはフルスクリーンモードがあり、TV や他の大型スクリーン搭載デバイスに表示できます。 </p> <p>必要なユーザーアクション：ダッシュボードプレイヤーの使用を止める必要があります。 </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>コピー</strong></td> 
  <td class="chdesc stentry"> ダッシュボードのリストに、元の名前と同じ名前を使用してコピーを追加します。ただし、そのダッシュボードの所有者が加えた更新や変更は表示できません。レガシーダッシュボードをコピーすると、空白のダッシュボードが開かれ、ここにレガシーコンテンツを追加できます。 <p>重要：ダッシュボードへの変更がそのダッシュボードを共有されているユーザーに表示されない場合は、そのユーザーが「<span class="uicontrol">コピー</span>」オプションを選択しているかどうかをダッシュボードマネージャーで確認してください。選択している場合、そのユーザーには更新／変更が表示されません。すべての変更／更新を表示するには、ダッシュボードマネージャーの「<span class="uicontrol">メニュー</span>」オプションを選択する必要があります。 </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>メニュー</strong></td> 
  <td class="chdesc stentry"> ダッシュボードの所有者が加えた変更や更新を表示できるようにします。 </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>共有しない</strong></td> 
  <td class="chdesc stentry"> 共有ダッシュボードのリストからダッシュボードを削除します。 </td> 
 </tr> 
</table>

## レガシーダッシュボードからの移行

既存のレガシーダッシュボードを引き続き実行し、編集、ダウンロードおよびスケジュールを行うこともできますが、レガシーダッシュボードを新規作成することはできません。必要なユーザーアクション：既存のレガシーダッシュボードを新しいダッシュボードフォーマットにアップグレードすることを強くお勧めします。

> [!NOTE] 今後は、 [Analysis Workspaceプロジェクトの使用と](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) 、ダウンロードおよびスケジュール機能の使用を検討します。

レガシーダッシュボードをコピーすると、編集用のレガシーダッシュボードが表示され、レガシーコンテンツまたは新しいコンテンツを追加できます。レガシーダッシュボードをコピーしても、元のレガシーダッシュボードはレガシーダッシュボードのリストに保持されます。

> [!NOTE] レガシーコンテンツをダッシュボードに追加すると、最新のダッシュボード機能に基づいてダッシュボードが作成されます。 ただし、レガシーレポートレットには以前のデータプラットフォームに基づくデータが含まれている可能性があります。

**バージョン 14.x のレガシーダッシュボードを移行するには**

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. 列の下 [!UICONTROL Manage] のをクリック [!UICONTROL Legacy Dashboards]します **[!UICONTROL Copy to New Dashboard]**。

   コピーされたダッシュボードがダッシュボードレイアウトエディターで開かれます。

   詳しくは、 [ダッシュボードとレポートレットのデータの編集](/help/analyze/reports-analytics/dashboard.md).

## ダッシュボードの共有

管理者がダッシュボードを複数のユーザーと共有（またはプッシュ）する手順を説明します。When you push dashboards to users, the dashboards become available in user&#39;s [!UICONTROL Shared Dashboards] menu.

1. で、ダッシ [!UICONTROL Dashboard Manager]ュボードを見つけて有効にしま **[!UICONTROL Shared]**&#x200B;す。
1. クリック **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. ページで、タ [!UICONTROL Push Dashboard] ーゲットユーザーを選択するか、をクリックしま **[!UICONTROL Check All]**&#x200B;す。
1. クリック **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. 選択している場合、そのユーザーには更新／変更が表示されません。To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## ダッシュボードの配信スケジュールの設定

In the [!UICONTROL Dashboard Manager], you can see whether a dashboard is scheduled for delivery, and edit the schedule. ダッシュボードの配信オプションは、レポート配信オプションと同じです。

1. ダッシュボードを開きます。
1. クリック **[!UICONTROL More]** > **[!UICONTROL Send]**.

   See [Schedule and Distribution](/help/analyze/reports-analytics/scheduling.md) for more information.

## ダッシュボードのアーカイブ

> [!NOTE] この機能は、2020年1月にはご利用いただけなくなります。

送信したダッシュボードを PDF ファイルとしてアーカイブする手順を説明します。アーカイブされたファイルは 2 年間または最大 4 GB に達するまで（いずれか短い期間）保存されます。

1. ダッシュボードを開きます。
1. クリック **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. グループ内で、 [!UICONTROL Email Report] を有効にしま **[!UICONTROL Archive]**&#x200B;す。
1. Specify delivery options, then click **[!UICONTROL Send]**.

   ダッシュボードマネージャーでアーカイブされたダッシュボードを表示できます。または、ダッシュボードを開いて、/をクリ **[!UICONTROL More]** ックしま **[!UICONTROL View Archive]**&#x200B;す。
