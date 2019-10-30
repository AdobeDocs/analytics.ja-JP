---
description: DFA と Adobe® コレクションサーバーが通信できるようになると、Reports & Analytics で DFA データを含むレポートを生成できます。
keywords: DFA
seo-description: DFA と Adobe® コレクションサーバーが通信できるようになると、Reports & Analytics で DFA データを含むレポートを生成できます。
seo-title: DFA データを使用した Analytics レポート
solution: Analytics
title: DFA データを使用した Analytics レポート
topic: Data Connectors
uuid: a4fe4a6c-f4a4-431d-bce9-9eedbcafedd6
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# DFA データを使用した Analytics レポート{#analytics-reports-using-dfa-data}

DFA と Adobe® コレクションサーバーが通信できるようになると、Reports &amp; Analytics で DFA データを含むレポートを生成できます。

パッケージ前の DFA レポートには、次が含まれます。

**チャネル**：有料検索と電子メールなど、バナー広告と他のインライン広告オプションを比較したデータを表示します。

**配信ツール**：DoubleClick for Advertisers と他のインライン広告サービスを比較したデータを表示します。

**サイト名**：DFA バナー広告が追加された Web サイトを比較したデータを表示します。

**ページ名**：DFA バナー広告が追加された個別の Web ページを比較したデータを表示します。

**広告名**：特定の DFA バナー広告を比較したデータを表示します。

**キャンペーン**：様々な DFA 広告キャンペーンを比較したデータを表示します。

DFA レポートを生成するには

1. Adobe Experience Cloud にログインします。
1. **[!UICONTROL Analytics]** / **[!UICONTROL Reports &amp; Analyticsに移動します]**。 インストールした DFA 統合のレポートスイートを選択していることを確認します。

1. 左側のナビゲーションで、DFA クリックスルーデータをキャプチャするコンバージョン変数を選択してから、目的の DFA レポートを選択します。
1. Click **[!UICONTROL Add Metrics]**. 指標セレクターダイアログボックスが開きます。
1. Check the Impressions and Clicks metrics in the **[!UICONTROL Available Metrics]** list and click **[!UICONTROL Apply]**.

   結果のレポートに、インプレッション数、クリック数および売上高データが表示され、DFA サービスからどれくらいの純売上高を得られるかを確認できます。例えば、DFA 広告名レポートは、現在の DFA 広告キャンペーンの特定のバナー広告に直接起因するインプレッション数、クリック数および売上高データを表示します。

   ![](assets/DFA_ad_name_report-sc15.png)

このレポートには、次の重要な機能があります。

* DFA_Ad Name レポートと表示されたレポートヘッダーには、レポート期間（2009 年 2 月）が表示され、横棒グラフ形式を使用したランクレポートであることが示されます。
* グラフ自体には、このレポートの各 DFA 広告に関する 3 つの指標（インプレッション数、クリック数および売上高）が表示されます。
* グラフは、各指標について、実際の数値を使用する代わりに指標合計の割合としてデータを表示します。これは、**[!UICONTROL レポートの設定]ダイアログボックスで変更できます。**
* グラフの下の DFA_Ad Name レポートのリストには、各 DFA 広告の詳細が表示され、広告パフォーマンスの数値と割合の両方のデータが表示されます。
* 特定の DFA 広告名を選択して、特定の DFA 広告に関する詳細情報を表示するためのオプションのメニューを開きます。
* 各指標列には、グラフ内で指標に割り当てられた色に対応するカラーキーが含まれます。
* レポートは、売上高指標を基準に並べられ、最も高い売上高の広告がトップに表示されます。別の列（指標）のラベルをクリックすることで、レポートの並び順を変更できます。
