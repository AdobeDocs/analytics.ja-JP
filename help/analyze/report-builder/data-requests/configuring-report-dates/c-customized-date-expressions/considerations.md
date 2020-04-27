---
description: '「式をカスタマイズ」を使用して日付範囲を設定する際には、次の 2 点に注意してください。 '
title: 日付のカスタマイズに関する考慮事項
topic: Report builder
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 日付のカスタマイズに関する考慮事項

「式をカスタマイズ」を使用して日付範囲を設定する際には、次の 2 点に注意してください。

* レポートが実行される日付、またはリクエストが更新される（基準の）日付によって、使用できるデータが決まります。
* レポートの開始日と終了日が相対的に変化すると、レポートが対象とする日付範囲に影響が出ます。

データが使用できるかどうかは、レポートの対象期間とリクエストの更新日によるので、必要な情報を抽出する場合は適切な日にレポートを実行してください。以下の例で、これらの両方の注意点について説明します。

Assume you make a request for [!UICONTROL Page Views] using Aggregated granularity. アメリカでは、週は日曜日から開始します。日曜日から土曜日までの期間（例えば、2008 年 11 月 23 日から 11 月 29 日）について更新されたレポートを取得するためには、日曜日（11 月 30 日）にその前週（11 月 23 日から 11 月 29 日）のレポートを実行（リクエストを更新）します。

この場合は、次のカスタマイズされた式を使用します。

*開始日：* cw-1w *終了日：* cw-1d

An analysis of the customize expression when the inclusive [!UICONTROL End Date] for the request is 11/30:

*開始日：* cw-1w

11 月 30 日（日）に開始する現在の週の開始日から 7 日間を引いた日付 = 11 月 23 日（日）

*終了日：* cw-1d

11 月 30 日（日）に開始する現在の週の開始日から 1 日間を引いた日付 = 11 月 29 日（土）

After the customized expression is mapped to the spreadsheet, refresh the request using Sunday, November 30, 2008 as the inclusive [!UICONTROL End Date] for the floating request. データには、直前 1 週間の期間が反映されます。

If instead you refresh the expression and specify Saturday, November 29 as the [!UICONTROL End Date] for the floating request, the data will reflect the week 11/16 to 11/22. この理由は、リクエスト更新のための基準日が 1 日早くなるからです。

Here are the differences when the inclusive [!UICONTROL End Date] for the request is 11/29:

*開始日：* cw-1w

11 月 23 日（日）に開始する現在の週の開始日から 7 日間を引いた日付 = 11 月 16 日（日）

*終了日：* cw-1d

11 月 23 日（日）に開始する現在の週の開始日から 1 日間を引いた日付 = 11 月 22 日（土）

ヨーロッパや他の一部の国々では、週は日曜日ではなく月曜日に開始します。この場合、カレンダーをカスタマイズして開始日を変更することができます。（[カスタムカレンダー](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)を参照）
