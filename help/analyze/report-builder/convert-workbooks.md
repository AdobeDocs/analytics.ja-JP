---
title: 従来のReport Builder ワークブックの変換
description: 従来のReport Builder ワークブックを新しいReport Builderに移行および変換する方法について説明します。 Adobe Analytics ベースのワークブックをシームレスに変換する方法については、この移行ガイドの手順に従ってください。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 9743d7ac2a6c7e63d7a6701e60d05683c5680d36
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 0%

---

# 従来のReport Builder ワークブックの変換

従来のReport Builderは、2026 年 6 月に提供終了となります。 ワークブックを従来のReport Builderから新しいReport Builderに移行する必要があります。 新しいReport Builderは、従来のReport Builderで作成されたワークブックをすばやく移行する便利な方法を提供します。

>[!IMPORTANT]
>
>従来のワークブックを変換する前に、各ワークブックを複製し、1 つのバージョンの名前を変更します。 これにより、必要に応じて、元の従来のワークブックのコピーを常に保持できます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[Convert workbooks](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/exporting/report-builder/upgrade-and-reschedule-workbooks){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


>[!NOTE]
>
>従来のワークブックを変換するには、まず [ 新しいReport Builderを設定する ](/help/analyze/report-builder/report-builder-setup.md) 必要があります。


## 従来のワークブックを開く

従来のワークブックを開くには、次の操作を実行します。

* **[!UICONTROL Report Builder ハブ]** の「[ スケジュール ](report-builder-hub.md)」タブから、スケジュールされた従来のワークブックを開きます。 このアクションは、スケジュールされたレガシーワークブックで推奨される方法です。 変換後の従来のワークブックをスケジュールする [ と、すぐに従来のワークブックに関連付けられたスケジュールを使用するオプションが ](#schedule-a-converted-legacy-workbook) きます。

   1. [!DNL Excel] を開き、![ のリボンバーから ](/help/assets/icons/AdobeLogoRedOnWhite.svg)AdobeLogoRedonWhite **** Report Builder[!DNL Excel] を選択します。

   1. **[!UICONTROL ログイン]** を選択し、Report Builderにログインします。

   1. **[!UICONTROL 2}Report Builderハブ]** で「[ スケジュール」を選択します。](report-builder-hub.md)
   1. 「**[!UICONTROL レガシー]** タブを選択します。 タブには、作成した従来のReport Builder ベースのスケジュール済みワークブックが一覧表示されます。

      ![ 従来のワークフロー ](assets/upgrade-legacy-schedule.png)

   1. リストから変換するスケジュール済みワークブックの「![SelectBox](/help/assets/icons/SelectBox.svg)」を選択し、「![ ダウンロード ](/help/assets/icons/Download.svg)」を選択します。 ワークブックがダウンロードされ、[!DNL Excel] の新しいウィンドウで開きます。 [ 従来のReport Builder ワークブックを変換 ](#convert-a--workbook) できるようになりました。


* 従来のワークブックをローカルコンピューターまたはネットワークから直接開きます。 この方法を使用する場合、従来のブックに関連付けられている可能性のあるスケジュールを使用することはできません。 <br/> 従来のワークブックを [!DNL Excel] で開いた場合：

   1. ![ のリボンバーから ](/help/assets/icons/AdobeLogoRedOnWhite.svg)AdobeLogoRedOnWhite **** Report Builder[!DNL Excel] を選択します。
   1. **[!UICONTROL ログイン]** を選択し、Report Builderにログインします。
   1. 次に [ 従来のワークブックを変換 ](#convert-a-workbook) します。


## 従来のワークブックの変換

従来のワークブックを変換するには：

1. 従来のワークブックを開くと、新しいReport Builderは、このワークブックに [ 従来のReport Builder](/help/analyze/legacy-report-builder/home.md) リクエストが含まれているかどうかを検出します。

   ![ 移行のアップグレードを示す [!DNL Excel] Report Builder アップグレードレポートのスクリーンショット ](assets/upgrade-workbook.png){zoomable="yes"}

1. 従来のリクエストが 1 つ以上見つかった場合は、「ワークブックをアップグレード **[!UICONTROL ダイアログで]** アップグレード **[!UICONTROL をクリックして、ワークブックをアップグレ]** ドします。

   >[!NOTE]
   >
   >各リクエストは個別にアップグレードする必要があります。 一括アップグレードはサポートされていません。


1. アップグレードすると、ブックの変更を知らせる **[!UICONTROL 警告]** ダイアログが表示されます。 また、続行する前に、従来のワークブックのバックアップを作成することも推奨されます。

   ![ 移行に関する警告を示す [!DNL Excel] Report Builder アップグレードレポートのスクリーンショット ](assets/upgrade-warning.png){zoomable="yes"}

1. **[!UICONTROL 続行]** をクリックして、アップグレードを続行します。

   アップグレードが正常に完了すると、「ワークブックのアップグレードが完了しました **[!UICONTROL 通知が表示され]** す。

   ![ 移行が完了したことを示す [!DNL Excel] Report Builder アップグレードレポートのスクリーンショット ](assets/upgrade-complete.png)

   * 「**[!UICONTROL 閉じる]**」を選択して通知を閉じ、新しいReport Builderの更新されたリクエストを含むワークブックで作業を続けます。

   * **[!UICONTROL アップグレードレポートをダウンロード]** を選択して、アップグレードの結果を示す新しい [!DNL Excel] ワークブックをダウンロードして開きます。 例については、以下を参照してください。

     ![ 移行レポートを示す [!DNL Excel] Report Builder アップグレードレポートのスクリーンショット ](assets/upgrade-report.png)

ワークブック内の [ データブロックを管理 ](/help/analyze/report-builder/manage-reportbuilder.md) できるようになりました。 これらのデータブロックは、アップグレードの結果であり、従来のReport Builder リクエストを置き換えます。


## 変換後の従来のワークブックのスケジュール

Report Builder ハブの「**[!UICONTROL スケジュール]**」タブからダウンロードして開いた従来のワークブックのスケジュールの詳細を使用することもできます。 このオプションは、ローカル コンピューターまたはネットワークから開いたスケジュールの詳細を含む従来のワークブックでは使用できません。

1. 変換後の従来のワークブックを従来のスケジュールでスケジュールするには、次の手順を実行します。

   * Report Builder ハブから **[!UICONTROL ワークブックを送信]** を選択する、または
   * Report Builderの **[!UICONTROL スケジュール]** タブにある **[!UICONTROL ワークブック]** タブから **[!UICONTROL スケジュールワークブック]** を選択します。

1. 従来のワークブックのスケジュールの詳細をデフォルトのスケジュール設定として使用するように勧められます。

   ![[!DNL Excel] Report Builderの従来のスケジュール設定オプションのスクリーンショット ](assets/upgrade-legacy-schedule-convert.png)

   * 従来のスケジュールの詳細を使用するには、「**[!UICONTROL 使用]**」を選択します。 スケジュールの詳細は、「ワークブックを送信 [ インターフェイスで事前入力され ](schedule-reportbuilder.md#schedule-a-workbook) す。
   * 従来のスケジュールの詳細を使用しない場合は、「**[!UICONTROL 使用しない]**」を選択します。
   * 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。

   今後、このワークブックに従来のスケジュールの詳細を使用しない場合は、「**[!UICONTROL 今後の使用から従来のメタデータを削除]**」を選択します。


## 従来のReport Builderからの移行

従来のReport Builderの一部の機能は、Report Builderでサポートされていない、部分的にサポートされている、別の方法で実装されていない、です。

* **リアルタイムリクエスト**。 リアルタイムリクエストはサポートされておらず、変換された従来のワークブックから削除されます。

* **パス/フォールアウトレポート**。 フォールアウト要求はサポートされておらず、変換された従来のワークブックから削除されます。

* 予定レポートの **[!DNL FTP]オプション**. [!DNL FTP] の場所に送信するレポートをスケジュールするオプションは使用できなくなりました。

* **予定レポート用の [!DNL Power BI] オプションにワークブックを公開する**。 [!DNL Power BI] にレポートをスケジュールするオプションは使用できなくなりました。

* **訪問者指標**。 レポート結果が完全には一致しない場合でも、変換後の従来のワークブックでは、指標 *、*、`visitorshourly`、`visitorsdaily`、`visitorsweekly` および `visitorsmonthly` が `visitorsquarterly` ユニーク訪問者 `visitorsyearly` に変換されます。 この変換は、`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` および `mobilevisitorsyearly` にも適用されます。

* **自動再認証**。 新しい [!DNL Excel] ファイルを開くときは、明示的に再認証する必要があります。 この再認証は、[!DNL Office Add-ins] 機能のセキュリティ機能です。

* **データブロックのグループを含むワークシートをコピーします**。 複数のデータ・ブロックを含むワークシートのコピーをサポートする手順は、次のとおりです：

   1. コピーする [!DNL Excel] ワークブックのワークシートタブを選択します。
   1. タブのコンテキストメニューから、「**[!UICONTROL 移動またはコピー…]**」を選択します。
   1. **[!UICONTROL 移動またはコピー]** ダイアログで、次の操作を行います。
      1. コピーするワークシートのコピー先を選択します。
      1. **[!UICONTROL コピーを作成]** を有効にします。
      1. **[!UICONTROL OK]** を選択します。
   1. ソース・ワークシートから、次の操作を行います。
      1. すべてのデータブロックを含むセル範囲を選択します。
      1. ![4](/help/assets/icons/Copy.svg)Report Builder ハブ **[!UICONTROL から「コピー」]** データブロックをコピー [ を選択します。](/help/analyze/report-builder/report-builder-hub.md)
   1. コピー先のワークシートで、次の操作を行います。
      1. コピーしたセル範囲を貼り付けるセルを選択します。
      1. ![4}Report Builder ハブ ](/help/assets/icons/Paste.svg) から「**[!UICONTROL 貼り付け]**」 [ データブロックの貼り付け } を選択します。](/help/analyze/report-builder/report-builder-hub.md)

* **日付範囲**。 Report Builderは、従来のReport Builderの日付範囲の行ラベルに適用された日付範囲フォーマットオプション **[!UICONTROL 開始期間と終了期間を次の形式で表示]** を移行しません。

* **平均**。 Report Builderでは、従来のReport Builderの指標に適用された選択した書式設定オプション **[!UICONTROL 平均オプション]** （**[!UICONTROL 日平均]** から **[!UICONTROL 年平均]** まで）が移行されません。 計算指標を使用して、選択したオプションを置き換えます。

* **テキストの先頭または末尾に付加**。 Report Builderは、従来のReport Builderの指標に適用された **[!UICONTROL 前付け/後付け]** テキスト）を移行しません。

* **小計**. Report Builderが、従来のReport Builderの指標に適用されたフォーマットオプション **[!UICONTROL 小計（このリクエスト）]** を移行しません。 従来のワークブックリクエストで **[!UICONTROL SubTotal （このリクエスト）]** を使用すると、機能は **[!UICONTROL Total]** に変換されます。 例：上位 5 つのページ名を持つレガシーデータブロックで **[!UICONTROL SubTotal （Page Views）]** を使用して上位 5 つのページ名のページビューの合計を返した場合。 移行後、上位 5 つのページ名を持つ同じデータブロックが、*すべて* のページ名のページビューの合計を返します。 計算指標の機能を使用すると、従来の **[!UICONTROL 小計]** 機能を置き換えることができます。
