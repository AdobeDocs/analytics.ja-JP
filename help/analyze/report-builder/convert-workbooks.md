---
title: 従来のReport Builderワークブックをデータブロックに変換する方法
description: レガシーリクエストをデータブロックに変換する方法を説明します
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# 従来のReport Builderワークブックのデータブロックへの変換

新しいReport Builderテクノロジーへの移行の一環として、現在の従来のワークブックを Javascript ベースのワークブックにすばやく変換できます。

>[!IMPORTANT]
>
>各ワークブックを複製し、1 つのバージョンの名前を変更してから変換します。 その場合でも、元のワークブックのコピーは必要に応じて保持されます。

>[!VIDEO](https://video.tv.adobe.com/v/3434957/?quality=12&learn=on)

1. [ 次の手順に従って ](/help/analyze/report-builder/report-builder-setup.md)、新しいReport Builderを設定します。

1. Excel を開き、右上の「Adobe Report Builder」アイコンをクリックします。

1. **[!UICONTROL ログイン]** をクリックし、Report Builderにログインします。

1. Report Builder アドインは、このブックに [ 従来のReport Builder](/help/analyze/legacy-report-builder/home.md) 要求が含まれているかどうかを検出します。

   ![ ワークブックのアップグレードを促すメッセージ ](assets/upgrade_workbook.png)

1. レガシーリクエストが 1 つ以上見つかった場合は、「**[!UICONTROL アップグレード]**」をクリックして、ワークブックをアップグレードします。

   >[!NOTE]
   >
   >各リクエストは個別にアップグレードする必要があります。 一括アップグレードはサポートされていません。


1. アップグレードすると、ブックが変更されたことを知らせる警告が表示されます。 また、続行する前に、従来のワークブックのバックアップを作成することも推奨されます。

   ![ アップグレードの警告 ](assets/upgrade_warning.png)

1. **[!UICONTROL 続行]** をクリックして、アップグレードを続行します。

   アップグレードが正常に完了すると、次の完了通知が表示されます。

   ![ アップグレード完了 ](assets/upgrade_complete.png)

1. （任意）「**[!UICONTROL アップグレードレポートをダウンロード]**」をクリックします。 このレポートには、アップグレードされた各データブロックのステータスが含まれています。

これで [ データブロックを管理 ](/help/analyze/report-builder/manage-reportbuilder.md) できます。


## 新しいReport Builderではサポートされていない従来のReport Builder機能

従来のReport Builderの機能と新しいReport Builderアドインの機能を比較すると、一部の従来の機能は使用できなくなります。

- リアルタイムリクエスト

- パス/フォールアウトレポート

- 予定レポートの FTP オプション

- 訪問者指標。 レポート結果が完全には一致しない場合でも、`visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly` および `visitorsyearly` の指標はすべて「ユニーク訪問者」に変換されます。 これは、`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly` および `mobilevisitorsyearly` にも適用されます。