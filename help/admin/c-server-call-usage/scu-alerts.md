---
description: サーバーのすべての使用状況アラートを追加または管理できます。アラートをセットアップすると、請求会社のすべてのログイン会社におけるすべてのレポートスイートに適用されます。
title: サーバーコールの使用状況アラート
uuid: 701fd542-5b24-42df-97a0-08e10929fa48
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# サーバーコールの使用状況アラート

アラートをセットアップすると、請求会社のすべてのログイン会社におけるすべてのレポートスイートに適用されます。

## 概要

A new alert category called **[!UICONTROL Server Calls Usage Alert]** is part of the existing [Alert Management](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html) user interface.

**1 つのデフォルトアラート**&#x200B;があらかじめ設定されており、サーバーコール使用状況の機能を利用できるあらゆるログイン会社内で表示されます。以下の条件のいずれかが満たされた場合、このアラートはログイン会社の管理者全員に宛てた通知をトリガーします。

* 該当するあらゆるサーバーコールタイプの「あらゆる」サーバーコール使用状況が 100 ％「以上」である。
* 該当するあらゆるサーバーコールタイプの「あらゆる」サーバーコール使用状況が 90 ％「以上」である。
* 該当するあらゆるサーバーコールタイプの「あらゆる」サーバーコール使用状況が 75 ％「以上」で、かつ、「経過した使用期間」が使用期間全体の 75 ％「以下」である。

![](assets/alerts.png)

サーバーコールの使用状況アラートには、以下の 2 とおりの方法でアクセスできます。

* Click **[!UICONTROL Manage Alerts]** in the upper right corner on the Current Usage tab or the Report Suite usage tab, or
* Adobe Analyticsで/ **[!UICONTROL Components]** に移 **[!UICONTROL Alerts]** 動します。

## サーバーコールの使用状況アラートの作成 {#section_2A2882C6D48D47C1944D52FB7C766BEC}

追加のアラートを作成するには、以下の手順に従います。

1. をクリック **[!UICONTROL + Add]** し、を選択しま **[!UICONTROL Server Call Usage Alert]**&#x200B;す。

   ![](assets/server_call_alert.png)

1. アラートを定義します。

   ![](assets/sc_alert.png)

   * **タイトル**：わかりやすい名前を指定します。名前を付けずにアラートを保存することはできません。
   * **時間制度**：アラートのチェック頻度を指定します。*現時点では、週 1 回の精度のみサポートしています。*&#x200B;つまり、アラートは週 1 回のペースでチェックされ、現在の使用期間のデータを振り返ります。
   * **受信者**：指定されたしきい値をアラートがトリガーしたときに電子メールを受け取る、組織の全員を指定します。
   * **有効期限**：デフォルトでは、有効期限はアラート作成日の 1 年後です。
   * **次の場合にアラートを送信**：

      * 次の指標のいずれかをトリガー：
サーバーコールのタイプを指標として追加し、修飾子と次のしきい値を選択してアラートのしきい値を指定します。
         * 以上
         * 以下
      * 次の場合：
経過した使用期間のしきい値と条件（以上または以下）を指定します。

1. クリック **[!UICONTROL Save]**.

## サーバーコールの使用状況アラートの管理 {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

アラートを管理するには、以下の手順に従います。

1. １ つ以上のアラートのチェックボックスを選択します。アラート管理のアクションが上部に表示されます。
1. 以下のアクションを 1 つ以上実行します。

   | アクション | 定義 |
   |--- |--- |
   | + 追加 | Access the [Alert Builder](/help/admin/c-server-call-usage/scu-alerts.md) by clicking  [!UICONTROL + Add]. |
   | タグ | アラートにタグを付けて、使いやすいように整理します。 |
   | 削除 | デフォルトアラートを除くすべてのアラートを削除できます。 |
   | 名前変更 | デフォルトアラートを除くすべてのアラートの名前を変更できます。 |
   | 承認 | アラートを承認して、「正式な」アラートにします。 |
   | 有効 / 無効 | デフォルトアラートを含め、すべてのアラートを有効または無効にすることができます。 |
   | 更新 | 1 つ以上のアラートを選択すると、それらを更新できます。This extends their expiration dates to be 1 year from the day [!UICONTROL Renew] was clicked, regardless of their original expiration date. |
   | CSV に書き出し | [使用状況レポートのダウンロード](/help/admin/c-server-call-usage/report-suite-usage.md)を参照してください。 |

