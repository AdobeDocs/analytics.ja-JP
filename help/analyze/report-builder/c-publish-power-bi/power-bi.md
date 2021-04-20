---
description: Microsoft Power BI で Report Builder を使用します。
title: Power BI への発行 - 概要
uuid: ad688817-6e3c-45da-983d-48c123465309
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 99%

---


# Power BI への発行 - 概要

Microsoft Power BI は、データを分析してインサイトを共有するビジネス分析ダッシュボードのスイートです。Adobe Analytics と Power BI を統合すると、Microsoft Power BI 内で Report Builder Analytics データを視覚化し、組織全体で簡単に共有できます。

これまで、アナリストは Report Builder ワークブックを電子メール（または ftp）で配信するようスケジュールを設定していました。それが、関係するビジネスユーザーが様々なプラットフォームやデバイスからアクセス可能な Web ベース環境で正確かつ最新のデータに（Power BI アカウント内から）アクセスできるようになりました。

Report Builder のレポート生成機能を Power BI の視覚化機能と組み合わせることで、組織の全員が情報にアクセスできるようになります。Power BI を使用すると、Adobe Analytics を他のデータソース（POS、CRM など）と統合して、独自の顧客インサイト、関連事項および機会を発見することもできます。

![](assets/aaplusbi.png)

## 必要システム構成 {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 が[インストールされている](/help/analyze/report-builder/setup/t-install-arb.md)
* Power BI にログインできるアクティブな Microsoft アカウント

## ワークブックを Power BI に発行する {#section_21CA66229EC240D49594A9A7D3FBA687}

スケジュールされたワークブックは、Adobe Analytics のデータが取り込まれた、フォーマット済みの Excel スプレッドシートです。スケジュールに従って定期的に送信されます。

**Report Builder でのワークブックの発行**

1. Report Builder で、ワークブックを生成して保存します。
1. Report Builder ツールバーで、**[!UICONTROL スケジュール]**／**[!UICONTROL 新規作成]**&#x200B;をクリックします。

1. 基本のスケジュールウィザードで、「**[!UICONTROL ワークブックを Microsoft Power BI に発行]**」の横にあるチェックボックスをオンにします。

   ![](assets/simple-schedule-wizard.png)

1. 電子メールを指定してすぐに送信するか、スケジュールの頻度（毎時、毎日など）を指定します。
1. 「**[!UICONTROL OK]**」をクリックして発行します。
1. Microsoft アカウントにログインするよう求められます。資格情報を入力します。
1. Report Builder ワークブックがスケジュールされて Power BI に発行されます。

   スケジュールされた各インスタンスでは、Report Builder のスケジュールプロセスによってワークブックが更新済みの Analytics データで更新された後、Microsoft Power BI に発行されます。

**Power BI での Report Builder のワークブックデータの表示**

1. Power BI で、[!UICONTROL ワークブック]メニューの下に表示されるワークブックをダブルクリックします。

   ![](assets/workbooks-power-bi.png)

1. これで、ワークブックのダッシュボードデータを表示できるようになります。           ![](assets/view-data-pbi.png)

1. このワークブックの領域をピン留めして任意の Power BI ダッシュボードに追加することができます。

## ワークブック内のすべてのフォーマット済みテーブルを Power BI データセットテーブルとして発行する {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
> ワークブックにマクロが含まれている場合、「すべてのフォーマット済みテーブルを Power BI データセットテーブルとして発行」は無効になります。

ワークブック全体をインポートする代わりに、ワークブック内のすべてのフォーマット済みテーブルの内容のみをインポートすることができます。

**使用例：**&#x200B;複数の Report Builder リクエストからデータを取り込み、多数の数式を含むサマリテーブルを作成する Excel ワークブックがあるとします。サマリテーブルのみを Power BI にインポートして、そのビジュアライゼーションを作成できます。

**Report Builder でのフォーマット済みテーブルの発行**

1. Report Builder で、ヘッダー行とそれに続くデータ行を含むデータテーブルを生成します。
1. テーブルを選択し、[!UICONTROL ホーム]メニューから&#x200B;**[!UICONTROL テーブルとしてフォーマット]**&#x200B;を選択します。テーブルにはデフォルトで名前（テーブル 1、テーブル 2 など）が付けられますが、[!UICONTROL デザイン]メニューで名前を変更できます。

1. Report Builder ツールバーで、**[!UICONTROL スケジュール]**／**[!UICONTROL 新規作成]**&#x200B;をクリックします。

1. 基本のスケジュールウィザードで、**[!UICONTROL アドバンススケジュールオプション]**&#x200B;をクリックします。
1. [!UICONTROL スケジュールウィザード - アドバンス]の「**[!UICONTROL 発行オプション]**」タブで「**[!UICONTROL すべてのフォーマット済みテーブルを Power BI データセットテーブルとして発行]**」の横にあるチェックボックスをオンにします。

   ![](assets/advanced-schedule-wizard2.png)

1. （オプション）発行されたアセットの名前を Power BI でカスタマイズできます。これは、ワークブック名の一部としてバージョン番号を使用しており（myworkbook_v1.1.xlsx など）、発行された Power BI アセットの名前にバージョン番号を表示したくない場合に便利です。バージョン番号が変更されても、発行されたアセットは変更されないという利点もあります（こちらの[仕様](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md)を参照してください）。

**Power BI でのテーブルデータの表示**

1. Power BI で、**[!UICONTROL ワークスペース]**／**[!UICONTROL データセット]**&#x200B;メニューに移動します。

   ![](assets/datasets-menu.png)

1. 発行したデータセットを選択し、その横にある[!UICONTROL レポートの作成]アイコンをクリックします。テーブルはフィールドとして表示されることに注意してください。

   ![](assets/formatted-tables.png)

1. テーブルとその関連列を選択します。

   ![](assets/view-table-dataset.png)

1. [!UICONTROL 視覚化]メニューから、Power BI でテーブルを視覚化する方法を選択できます。例えば、データを折れ線グラフとして表示することができます。

   ![](assets/bi-line-graph.png)

1. ここから、このデータセットテーブルのビジュアライゼーションを作成できます。

## すべての Report Builder リクエストを Power BI データセットテーブルとして発行する {#section_0C26057C7DBB4068A643FDD688F6E463}

すべてのリクエストをデータセットテーブルに変換し、その上にビジュアライゼーションを作成することができます。

>[!IMPORTANT]
>
>ワークブックに 100 を超えるリクエストが含まれている場合、Power BI に発行されるのは最初の 100 件のリクエストのみです。さらに、Power BI に発行された各リクエストでは、最初の 10,000 行のデータのみが発行されます。そのため、こうしたリクエストはスケジュールによって正常に配信されますが、Power BI への発行範囲は制限されます。

1. Report Builder で、Report Builder リクエストを含むワークブックを開くか作成します。
1. Report Builder ツールバーで、**[!UICONTROL スケジュール]**／**[!UICONTROL 新規作成]**&#x200B;をクリックします。

1. 基本のスケジュールウィザードで、**[!UICONTROL アドバンススケジュールオプション]**&#x200B;をクリックします。
1. [!UICONTROL スケジュールウィザード - アドバンス]の「**[!UICONTROL 発行オプション]**」タブで「**[!UICONTROL すべての Report Builder リクエストを Power BI データセットテーブルとして発行]**」の横にあるチェックボックスをオンにします。![](assets/advanced-schedule-wizard2.png)

1. 「**[!UICONTROL OK]**」をクリックします。

**Power BI でのリクエストデータの表示**

スケジュールされた各 Report Builder リクエストは、データセット内のテーブルとして発行されます。各リクエストテーブルには、リクエストのプライマリディメンションに基づいた名前が付けられ、[!UICONTROL レポートスイート]列と[!UICONTROL セグメント]列があります。

1. Power BI で、**[!UICONTROL ワークスペース]**／**[!UICONTROL データセット]**&#x200B;メニューに移動します。

1. 発行したリクエストを選択し、その横にある[!UICONTROL レポートの作成]アイコンをクリックします。

   リクエストは、[!UICONTROL フィールド]メニューにテーブルとして表示されることに注意してください。

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >ワークシートで Report Builder リクエストのレイアウトをどのように設定しても（ピボットレイアウト、カスタムレイアウト、一部の列を非表示）、リクエストは同じ 2 次元の単一ヘッダー行形式（日付、ディメンション、指標、レポートスイート、セグメント）で常に発行されます。

1. **[!UICONTROL 凡例]**&#x200B;という追加のテーブルがあることにも注意してください。Report Builder 以外でリクエストを利用する場合に、各リクエストが何を表しているのかわからなくなることがあります。凡例テーブルの目的は、例えば、テーブル ID の下に各リクエストの名前を表示することです。他の凡例列を追加して、リクエストの全体像を把握することもできます。

   ![](assets/legend-table.png)

