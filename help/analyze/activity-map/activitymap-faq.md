---
description: Activity Mapの設定、設定および機能の使用に関するよくある質問です。
title: Activity Map の FAQ
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 5a8ff1c81644c12f7d00ef147db197f54c48f60c

---


# Activity Map の FAQ

Activity Mapの設定、設定および機能の使用に関するよくある質問です。

## 実装と AppMeasurement

**質問：新しいActivity Mapを有効にするための導入手順を教えてください。**

A:Activity Mapの有効化を [確認してください](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**質問：Analytics ユーザーは全員が管理ツールの Activity Map 実施可能ページにアクセスできますか。**

回答：Adobe SiteCatalyst ユーザーは Admin Console の Activity Map 実施可能ページにアクセスできません。この設定ページにアクセスできるのは、Adobe Analytics StandardおよびAdobe Analytics Premiumの契約を締結している会社のみです。

**質問：新しいAppMeasurementコードは、Dynamic Tag Management(DTM)を使用して設定できますか。**

A:はい、新しいAppMeasurementコードを [手動で](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) 実装できます。

**質問：AppMeasurement v1.6ライブラリの大きな変更点は何ですか。**

回答：AppMeasurement v1.6 の唯一の変更点は、Activity Map リンクトラッキングプロセスの手法です。ページ名、リンク ID、地域 ID が必要です。

**質問：AppMeasurementは、特定のページではなく、ドメインレベルでロールアウトされますか。**

A:AppMeasurementは、レポートスイートレベルでロールアウトされます。 レポートスイートレベルは、通常ドメインレベルに関連付けられますが、実装ごとに異なります。

**質問：DTMは、Activity Mapが必要とする(1.5.1)よりも古いバージョン(1.3.4)の訪問者APIを自動的に読み込みます。 問題なの？**

回答：いいえ。Activity Mapの機能は、VisitorAPIに依存しません。

## Activity Map アプリケーション

<!--**Q: How does Activity Map support Single-Page Applications (SPA)?**

A: 

* Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the [Links On Page](/help/analyze/activity-map/activitymap-links-report.md) table's Present column for that link updates with **[!UICONTROL Displayed]** or **[!UICONTROL Hidden]**.

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the **[!UICONTROL Links On Page]** table. Activity Map sends a new data request that includes these new links. The new links should appear in the **[!UICONTROL Links On Page]** table when the data request is handled by the UI.-->

**質問：Activity Mapは「ビュー」に関するデータを提供しますか。**

A:いいえ。表示されたリンクは追跡されません。

**質問：以前にWebサイトでVisitor ClickMapを使用していない場合、Activity Mapを使用できますか。**

A:従来のバージョン（現在は単にClickMapと呼ばれています）がインストールされていることは、新しいバージョンを実装するための前提条件ではありません。 アドビは、限られた期間、引き続きレガシーバージョンをサポートします。

**質問：Activity Mapでサポートされているブラウザーとバージョンを教えてください。**

A:4つのメインブラウザー(Chrome、Firefox、Safari、IE)の最新バージョンをサポートしています。

**質問：デフォルトのオーバーレイ設定は何ですか？**

A:デフォルトでは、Activity Mapには、データを収集したすべてのリンクが表示されます。

顧客のWebページの上にポップアップパネルが表示される場合、ポップアップパネルの下にあるリンクに属するオーバーレイがポップアップパネルの上に表示される場合があります。

**質問：ランク付けされた項目のオーバーレイが一部表示されないのはなぜですか。**

A:ランク付けされたリンクの一部がページに表示されない場合があります（サブメニューリンクなど）。 その結果、対応するリンクオーバーレイは表示されません。 このため、特定のランク値が欠けているオーバーレイランクを見ることができます。ランクは、ページ内のすべてのリンク（現在のリンクと非表示のリンク）に対して計算されるからです。

**質問：すべてのリンクレポートで、リンクのランクはどのように決定されますか。**

* グラデー **ション** とバ **ブル** モード：ランキングは指標列で決まります。 同じ指標値を持つリンクの場合、リンクIDのアルファベット順に基づいてランクが更に決定されます。
* 勝者と **敗者のモードで** 、ランクは主に%ゲイン列で決まります。 同じゲインのリンクの場合、リンクIDのアルファベット順に基づいてランクがさらに決定されます。

**質問：Activity Mapの実行時にリンククリックデータが収集されないのはなぜですか。**

A:Activity Mapが使用中の場合、Analyticsタグでリンククリックデータは収集されません。 この動作は、ClickMapプラグインの動作に従います。

**質問：Activity Map のすべてのリンクレポートは、Reports &amp; Analytics の Activity Map レポートとどのように比較されますか。**

回答：Activity Map ですべてのリンクレポートを引き出すには、`<list of link&regions present in the page at rendering time>` の Activity Map のリンクと地域を基準として Activity Map ページ = &quot;visitedpage&quot; を分類する分類リクエストを作成します。

Reports &amp; Analyticsで同等のレポートを取得するには、まずActivity Mapのページレポートに移動する必要があります。 ここで、Activity Mapで訪問されたページ名をフィルタリングします。 訪問されたページ名は、Activity Mapのページの詳細下部パネルの左の列に表示されます。 ページが見つかったら、そのページから分類し、Activity Mapのリンクと地域をセカンダリディメンションとして選択できます。

ただし、R&amp;Aで取得したレポートには、そのページに対して収集されたすべてのリンクと地域が一覧表示されることに注意してください。 ただし、Activity Mapは、現在Webページに存在するリンクと地域のみをレポートします。 そのため、ニュースサイトがある場合は、その時点で存在するニュースストーリーのデータのみが表示され、その日の早い時点で存在していたニュースストーリーは表示されません。

**質問：複数のレポートスイートを一覧表示する複数のタグを含むページで、Activity Mapはどのように機能しますか。**

A:デフォルトでは、Activity Mapは、ページから送信された最初のタグに関連付けられたレポートスイートを使用します。 Activity Map 設定／「その他」タブで、別のタグ付きレポートスイートを選択できます。

**質問：Activity Mapは、Analyticsタグをどの程度の期間スキャンしますか。**

A:ページ完了イベントの後、Analyticsタグを最大20秒間スキャンします。

**質問：Activity Mapは動的コンテンツをどのように処理しますか。**

A:Activity Mapは2秒ごとにチェックを行い、次のようなWebページの状態に変化が見つかったかどうかを確認します。

* 表示されるHTMLコンテンツ
* 非表示のHTMLコンテンツ
* 挿入された新しいHTMLコンテンツ

コンテンツが非表示または表示されると、影響を受けるリンクの状態（およびオーバーレイ）が、非表示から表示、または表示から非表示に自動的に変更されます。

新しいコンテンツが挿入されると、アプリケーションは関連するリンクを取得し、それらのリンクの分析データを取り込み、これらのリンクのオーバーレイを追加します。

**質問：ページフローレポートの基礎となる指標は何ですか。**

A:表示されるデータはすべてページビュー数に基づいています。

**質問：様々なタイプのページでのActivity Mapの動作を説明できますか。**

*AnalyticsタグのないWebページ*

タグが存在しないことを示す警告メッセージがツールバーの下に表示されます。

*互換性のないAnalyticsタグ（AppMeasurement v1.5以前）を含むWebページ*

ページコードをv1.6以上にアップグレードする必要があることを示す警告メッセージが表示されます。

*互換性のある Analytics タグ（AppMeasurement v1.6 以降）を含む Web ページ、ただし、管理ツールで Activity Map のレポートが有効になっていない場合*

\[Activity Map のレポートの有効化\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;)を管理者に依頼する必要があることを示す警告メッセージが表示されます。

**質問：[Analytics データフィード](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)を使用して Activity Map データ（contextData）を書き出すことはできますか。**

回答：いいえ。

## Activity Map でのセグメント化

**質問：セグメントは個々のユーザーセグメントに結び付けられているか。 共有セグメントはActivity Mapで使用できますか。**

A:Activity Mapは、Analyticsからレポートセグメントを継承します。

**質問：セグメントはライブモードで機能しますか。**

A:いいえ。セグメントはライブモードでは機能しません。 この機能は、Reports &amp; Analyticsのリアルタイムレポートと同じです。

## 仮想レポートスイート

**質問：Activity Mapは仮想レポートスイートと互換性がありますか。**

回答：はい。ただし、仮想レポートスイートの制限により、Activity Mapのライブモードは仮想レポートスイートと互換性がありません。
