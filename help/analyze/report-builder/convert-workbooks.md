---
title: 従来のReport Builder ワークブックをデータブロックに変換する方法
description: レガシーリクエストをデータブロックに変換する方法を説明します
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 22%

---

# 従来のReport Builder ワークブックのデータブロックへの変換

新しいReport Builder テクノロジーへの移行の一環として、現在の従来のワークブックを Javascript ベースのワークブックにすばやく変換できます。

>[!IMPORTANT]
>
>各ワークブックを複製し、1 つのバージョンの名前を変更してから変換します。 その場合でも、元のワークブックのコピーは必要に応じて保持されます。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Convert workbooks](https://video.tv.adobe.com/v/3446183?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]



1. [&#x200B; 次の手順に従って &#x200B;](/help/analyze/report-builder/report-builder-setup.md)、新しいReport Builderを設定します。

1. Excel を開き、右上の「Adobe Report Builder」アイコンをクリックします。

1. **[!UICONTROL ログイン]** をクリックし、Report Builderにログインします。

1. Report Builder アドインは、このワークブックに [&#x200B; 従来のReport Builder](/help/analyze/legacy-report-builder/home.md) リクエストが含まれているかどうかを検出します。

   ![&#x200B; ワークブックのアップグレードを促すメッセージ &#x200B;](assets/upgrade_workbook.png)

1. レガシーリクエストが 1 つ以上見つかった場合は、「**[!UICONTROL アップグレード]**」をクリックして、ワークブックをアップグレードします。

   >[!NOTE]
   >
   >各リクエストは個別にアップグレードする必要があります。 一括アップグレードはサポートされていません。


1. アップグレードすると、ブックが変更されたことを知らせる警告が表示されます。 また、続行する前に、従来のワークブックのバックアップを作成することも推奨されます。

   ![&#x200B; アップグレードの警告 &#x200B;](assets/upgrade_warning.png)

1. **[!UICONTROL 続行]** をクリックして、アップグレードを続行します。

   アップグレードが正常に完了すると、次の完了通知が表示されます。

   ![&#x200B; アップグレード完了 &#x200B;](assets/upgrade_complete.png)

1. （任意）「**[!UICONTROL アップグレードレポートをダウンロード]**」をクリックします。 このレポートには、アップグレードされた各データブロックのステータスが含まれています。

これで [&#x200B; データブロックを管理 &#x200B;](/help/analyze/report-builder/manage-reportbuilder.md) できます。


## 新しい Report Builder でサポートされていないレガシー Report Builder 機能 {#unsupported}

レガシー Report Builder の機能と新しい Report Builder アドインの機能を比較すると、一部のレガシー機能は使用できなくなっています。

- リアルタイムリクエスト

- パス／フォールアウトレポート

- 予定レポートの FTP オプション

- 訪問者指標。レポート結果が完全に一致しない場合でも、`visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly` および `visitorsyearly` の指標はすべて「ユニーク訪問者」に変換されます。これは、`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` および `mobilevisitorsyearly` にも適用されます。

## 変換後のワークブックのスケジュール {#schedule}

スケジュールに関する記事の [&#x200B; 変換後のワークブックをスケジュール設定する &#x200B;](/help/analyze/report-builder/schedule-reportbuilder.md) を参照してください。