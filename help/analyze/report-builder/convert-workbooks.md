---
title: 従来のReport Builder ワークブックの変換
description: 従来のReport Builder ベースのワークブックを新しいReport Builderを使用するように変換する方法を説明します。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: d7832dc56eb680f57a6875cf32e29fd5a8858098
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 1%

---

# 従来のReport Builder ワークブックの変換

新しいReport Builder機能への移行の一環として、現在の従来のReport Builder ベースのワークブック（従来のワークブック）を、新しいReport Builder[ データブロック ](create-a-data-block.md) 機能を使用するようにすばやく変換できます。

>[!IMPORTANT]
>
>従来のワークブックを変換する前に、各ワークブックを複製し、1 つのバージョンの名前を変更します。 これにより、必要に応じて、元の従来のワークブックのコピーを常に保持できます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[Convert workbooks](https://video.tv.adobe.com/v/3434957?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


>[!NOTE]
>
>従来のワークブックを変換するには、まず [ 新しいReport Builderを設定する ](/help/analyze/report-builder/report-builder-setup.md) 必要があります。


## 従来のワークブックを開く

従来のワークブックを開くには、次の操作を実行します。

* 従来のワークブックをローカルコンピューターまたはネットワークから直接開きます。 従来のワークブックを Excel で開いた場合：

   1. Excel のリボンバーから ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** を選択します。
   1. **[!UICONTROL ログイン]** を選択し、Report Builderにログインします。
   1. 次に [ 従来のワークブックを変換 ](#convert-a-workbook) します。

* **[!UICONTROL Report Builder ハブ]** の「[ スケジュール ](report-builder-hub.md)」タブから、スケジュールされた従来のワークブックを開きます。 それには、次の手順を実行します。

   1. Excel を開き、Excel のリボンバーから ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** を選択します。

   1. **[!UICONTROL ログイン]** を選択し、Report Builderにログインします。

   1. **[!UICONTROL 2}Report Builderハブ]** で「[ スケジュール」を選択します。](report-builder-hub.md)
   1. 「**[!UICONTROL レガシー]** タブを選択します。 このタブには、従来のReport Builderでスケジュールされたワークブックが表示されます。

      ![ 従来のワークフロー ](assets/upgrade-legacy-schedule.png)

   1. リストから変換するスケジュール済みワークブックの「![SelectBox](/help/assets/icons/SelectBox.svg)」を選択し、「![ ダウンロード ](/help/assets/icons/Download.svg)」を選択します。 ワークブックがダウンロードされ、Excel の新しいウィンドウで開きます。 [ 従来のReport Builder ワークブックを変換 ](#convert-a--workbook) できるようになりました。


## 従来のワークブックの変換

従来のワークブックを変換するには：

1. 従来のワークブックを開くと、新しいReport Builderは、このワークブックに [ 従来のReport Builder](/help/analyze/legacy-report-builder/home.md) リクエストが含まれているかどうかを検出します。

   ![ ワークブックのアップグレードを促すメッセージ ](assets/upgrade-workbook.png){zoomable="yes"}

1. 従来のリクエストが 1 つ以上見つかった場合は、「ワークブックをアップグレード **[!UICONTROL ダイアログで]** アップグレード **[!UICONTROL をクリックして、ワークブックをアップグレ]** ドします。

   >[!NOTE]
   >
   >各リクエストは個別にアップグレードする必要があります。 一括アップグレードはサポートされていません。


1. アップグレードすると、ブックの変更を知らせる **[!UICONTROL 警告]** ダイアログが表示されます。 また、続行する前に、従来のワークブックのバックアップを作成することも推奨されます。

   ![ アップグレードの警告 ](assets/upgrade-warning.png){zoomable="yes"}

1. **[!UICONTROL 続行]** をクリックして、アップグレードを続行します。

   アップグレードが正常に完了すると、「ワークブックのアップグレードが完了しました **[!UICONTROL 通知が表示され]** す。

   ![ アップグレード完了 ](assets/upgrade-complete.png)

   * 「**[!UICONTROL 閉じる]**」を選択して通知を閉じ、新しいReport Builderの更新されたリクエストを含むワークブックで作業を続けます。

   * **[!UICONTROL アップグレードレポートをダウンロード]** を選択して、アップグレードの結果を示す新しい Excel ワークブックをダウンロードして開きます。 例については、以下を参照してください。

     ![Excel Report Builder アップグレード レポート ブック ](assets/upgrade-report.png)

これで [ データブロックを管理 ](/help/analyze/report-builder/manage-reportbuilder.md) できます。


## 変換後の従来のワークブックのスケジュール

Report Builder ハブの「**[!UICONTROL スケジュール]**」タブからダウンロードして開いた従来のワークブックのスケジュールの詳細を使用することもできます。 このオプションは、ローカル コンピューターまたはネットワークから開いたスケジュールの詳細を含む従来のワークブックでは使用できません。

1. ワークブックのスケジュールを設定します。 変換後の従来のワークブックを従来のスケジュールでスケジュールするには、次の手順を実行します。

   * Report Builder ハブから **[!UICONTROL ワークブックを送信]** を選択する、または
   * Report Builderの **[!UICONTROL スケジュール]** タブにある **[!UICONTROL ワークブック]** タブから **[!UICONTROL スケジュールワークブック]** を選択します。

1. 従来のワークブックのスケジュールの詳細をデフォルトのスケジュール設定として使用するように勧められます。

   ![ 従来のワークブックスケジュールを移行 ](assets/upgrade-legacy-schedule-convert.png)

   * 従来のスケジュールの詳細を使用するには、「**[!UICONTROL 使用]**」を選択します。 スケジュールの詳細は、「ワークブックを送信 [ インターフェイスで事前入力され ](schedule-reportbuilder.md#schedule-a-workbook) す。
   * 従来のスケジュールの詳細を使用しない場合は、「**[!UICONTROL 使用しない]**」を選択します。
   * 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。

   今後、このワークブックに従来のスケジュールの詳細を使用しない場合は、「**[!UICONTROL 今後の使用から従来のメタデータを削除]**」を選択します。


## 従来のReport Builder機能はサポートされていません {#unsupported}

一部の従来のReport Builder機能は、新しいReport Builderでは使用できなくなりました

* リアルタイムリクエスト。

* パス/フォールアウトレポート。

* 予定レポートの FTP オプション。

* 訪問者指標。レポート結果が完全には一致しない場合でも、指標 *、*、`visitorshourly`、`visitorsdaily`、`visitorsweekly` および `visitorsmonthly` は、`visitorsquarterly` ユニーク訪問者 `visitorsyearly` に変換されます。 この変換は、`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` および `mobilevisitorsyearly` にも適用されます。
