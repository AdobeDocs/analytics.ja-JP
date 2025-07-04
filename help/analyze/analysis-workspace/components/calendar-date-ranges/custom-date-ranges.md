---
description: Analysis Workspace でカスタム日付範囲を作成し、時間コンポーネントとして保存します。
keywords: Analysis Workspace
title: Analysis Workspace でカスタム日付範囲を作成
feature: Date Ranges
role: User, Admin
exl-id: 586bb120-3f20-452c-9867-0b93d2e794bc
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: ht
source-wordcount: '438'
ht-degree: 100%

---

# カスタム日付範囲を作成

Analysis Workspace でカスタム日付範囲を作成し、時間コンポーネントとして保存できます。

プロジェクトへの既存の日付範囲の追加について詳しくは、[カレンダーと日付範囲の概要](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)を参照してください。

カスタム日付範囲を作成するには：

1. Adobe Analytics で、**[!UICONTROL コンポーネント]**／**[!UICONTROL 日付範囲]**&#x200B;を選択します。

   ![日付範囲ページ](assets/date-ranges.png)

1. 「[!UICONTROL **新しい日付範囲を作成**]」を選択します。

1. 日付範囲ビルダーで、次の情報を指定します。

   | オプション | 説明 |
   |---------|----------|
   | [!UICONTROL **タイトル**] | ユーザーが Analysis Workspace で日付範囲を選択した際に表示される日付範囲のタイトル。 |
   | [!UICONTROL **説明**] | 日付範囲に関する説明。 |
   | [!UICONTROL **タグ**] | 日付範囲に適用するタグ。 |
   | [!UICONTROL **日付範囲**] | カスタム日付範囲を選択できます。デフォルトでは、過去 30 日間が選択されます。 |
   | [!UICONTROL **プリセット**] | [!UICONTROL **昨日**]、[!UICONTROL **過去 7 日間**]、[!UICONTROL **過去 30 日間**]&#x200B;など、プリセット日付範囲のリストから選択します。 |
   | [!UICONTROL **開始時間**] | 日付範囲が開始する時刻。 |
   | [!UICONTROL **終了時間**] | 日付範囲が終了する時刻。 |
   | [!UICONTROL **日周期を使用**] | 日周期を使用すると、レポートを実行したタイミングに基づいて、一定期間、将来や過去を確認する動的レポートを生成できます。例えば、（「作成日」フィールドに基づく）「先月」に発行されたすべての注文をレポートしたい場合、12 月にレポートを実行すると、11 月に発行された注文が表示されます。同じレポートを 1 月に実行すると、12 月に発行された注文が表示されます。<ul><li>**[!UICONTROL 日付のプレビュー]**：周期的なカレンダーに含まれる期間を示します。</li><li>**[!UICONTROL 開始]**：本日、今週、今月、今四半期、本年から選択できます。</li><li>**[!UICONTROL 終了]**：本日、今週、今月、今四半期、本年から選択できます。</li></ul><br>デフォルトで選択されています。 |

1. 「[!UICONTROL **保存**]」を選択します。

## 例：「2 か月前」の日付範囲 {#section_C4109C57CB444BB2A79CC8082BD67294}

次のカスタム日付範囲は、方向の変化を示す変更概要ビジュアライゼーションで、「2 ヶ月前」の日付範囲を示します。

![](assets/date-range-two-months-ago.png)

カスタム日付範囲は、プロジェクトの[!UICONTROL 日付範囲]コンポーネントパネルの最上部に表示されます。

![](assets/date-range-panel-two-months-ago.png)

比較用に、このカスタム日付範囲を、先月プリセットを使用した、カスタムの、月周期の日付範囲の横の列にドラッグできます。変更概要ビジュアライゼーションを追加して、各列から合計を選択し、方向の変化を示します。

![](assets/date-range-two-months-table.png)

## 例：7 日周期の日付範囲の使用 {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

1 週間前に終了する 7 日周期の時間枠を指定する、日付範囲を作成できます。

![](assets/create_date_range.png)

*`rolling daily`*.を使用します。

* 「開始」設定は、*`current day minus 6 days`* になります。

* 「終了」設定は、*`current day minus 7 days`* になります。

この日付範囲は、コンポーネントとして任意のフリーフォームテーブルにドラッグできます。
