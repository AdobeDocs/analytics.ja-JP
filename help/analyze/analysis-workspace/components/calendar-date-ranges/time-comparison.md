---
description: Analysis Workspace での日付の比較では、日付範囲を含む任意の列を使用して、前年比、前四半期比、前月比などの一般的な日付比較を作成できます。
title: 日付の比較
uuid: ef18f9d9-b6ad-4859-b7c9-9750ca0df519
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 日付の比較

Analysis Workspace での日付の比較では、日付範囲を含む任意の列を使用して、前年比、前四半期比、前月比などの一般的な日付比較を作成できます。

## 期間を比較 {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

分析にはコンテキストが必要ですが、多くの場合、そのコンテキストは前の期間から得られます。例えば、「前年の同じ時期に比べてどのくらい良くなっているか悪くなっているか」という質問は、ビジネスを把握するうえで基本的な問いです。日付の比較では自動的に「差異」列が含まれ、指定した期間と比較した変更の割合が示されます。

1. ある期間について比較する任意のディメンションと指標を含むフリーフォームテーブルを作成します。
1. テーブル行を右クリックし、を選択しま **[!UICONTROL Compare Time Periods]**&#x200B;す。

   ![](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >この右クリックオプションは、指標行、日付範囲行、時間ディメンション行では無効化されます。

1. テーブルの日付範囲をどのように設定したかに応じて、次のオプションを比較に使用できます。

   | オプション | 説明 |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | この日付範囲の直前の週、月などと比較します。 |
   | **[!UICONTROL This week/month/quarter/year last year]** | 1 年前の同じ日付範囲と比較します。 |
   | **[!UICONTROL Select range]** | カスタム日付範囲を選択できます。 |

   >[!NOTE]
   >
   >カスタムの日数を選択すると、例えば10月7日～ 10月20日（14日の範囲）の場合、次の2つのオプションしか表示されません。、 **[!UICONTROL Prior 14 days before this date range]**&#x200B;および **[!UICONTROL Select range]**。

1. 結果として次のような比較が表示されます。

   ![](assets/compare-time-result.png)

   「変更の割合」列は、マイナスの値の場合は赤、プラスの値の場合は緑で表示されます。

1. （オプション）他の Workspace プロジェクトの場合と同様に、これらの期間比較に基づいてビジュアライゼーションを作成できます。以下は横向き棒グラフの例です。

   ![](assets/compare-time-barchart.png)

   Note that in order to show the percentage change in the bar chart, you have to have the [!UICONTROL Percentages] setting checked in the [!UICONTROL Visualization Settings].

## 比較のために期間の列を追加 {#section_93CC2B4F48504125BEC104046A32EB93}

テーブルの各列に期間を追加できるようになりました。これにより、カレンダーの設定先とは異なる期間を追加できます。この方法でも日付を比較することができます。

1. テーブルの列を右クリックし、「 **[!UICONTROL Add Time Period Column]**![](assets/add-time-period-column.png)

1. テーブルの日付範囲をどのように設定したかに応じて、次のオプションを比較に使用できます。

   | オプション | 説明 |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | この日付範囲の直前の週、月などの列を追加します。 |
   | **[!UICONTROL This week/month/quarter/year last year]** | 1 年前の同じ日付範囲を追加します。 |
   | **[!UICONTROL Select range]** | カスタム日付範囲を選択できます。 |

   >[!NOTE]
   >
   >カスタムの日数を選択すると、例えば10月7日～ 10月20日（14日の範囲）の場合、次の2つのオプションしか表示されません。、 **[!UICONTROL Prior 14 days before this date range]**&#x200B;および **[!UICONTROL Select range]**。

1. 選択した列の前に、期間が挿入されます。

   ![](assets/add-time-period-column2.png)

1. 期間の列はいくつでも追加でき、異なる日付範囲を組み合わせることもできます。

   ![](assets/add-time-period-column4.png)

1. また、各列で並べ替えて、並べ替えに使用した列に基づいて日付の順序を変更することもできます。

## 列の日付が同じ行で始まるように整列 {#section_5085E200082048CB899C3F355062A733}

すべてのテーブルに対して新しい設定を使用できま **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**&#x200B;す。 「テーブル全体に適用」とは、例えば、テーブルで分類をおこない、分類に対してこの設定を変更すると、テーブル全体で設定が変更されることを意味します。

![](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>この設定は、すべての既存のプロジェクトでは&#x200B;**無効**（オフ）、すべての新規プロジェクトでは&#x200B;**有効**（オン）になっています。

例：日付を整列させると、2016 年 10 月を 9 月と比較する前月比の場合、左側の列は 10 月 1 日、右側の列は 9 月 1 日から始まります。

![](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->

