---
description: '[!DNL Activity Map]での機能の設定、設定、使用に関するよくある質問です。'
seo-description: '[!DNL Activity Map]での機能の設定、設定、使用に関するよくある質問です。'
seo-title: '[!DNL Activity Map] FAQ'
solution: Analytics
title: '[!DNL Activity Map] FAQ'
topic: Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# [!DNL Activity Map] FAQ

Frequently asked questions for setting up, configuring, and employing features in [!DNL Activity Map].

## 導入と AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**質問：新しい[!DNL Activity Map]**

A:[!DNL Activity Map] [を有効にするを確認してください](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**質問：Analytics ユーザーは全員が管理ツールの Activity Map 実施可能ページにアクセスできますか。**

A: Adobe SiteCatalyst customers do not have access to the Admin Console's [!DNL Activity Map] Enablement page. Adobe Analytics Standard および Adobe Analytics Premium の契約を締結している企業のみが、この設定ページにアクセスできます。

**質問：新しい AppMeasurement コードは、Dynamic Tag Management（DTM）を使用して設定できますか。**

回答：はい。新しい AppMeasurement コードは[手動で実装](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html)できます。

**質問：AppMeasurement v1.6 ライブラリの大きな変更点は何ですか。**

A: The only change in AppMeasurement v1.6 is in the [!DNL Activity Map] link tracking process methodology that requires the collection of Page name, Link ID and RegionID.

**質問：AppMeasurement は、特定のページ上ではなく、ドメインレベルでロールアウトされますか。**

回答：AppMeasurement は、レポートスイートレベルでロールアウトされます。レポートスイートレベルは、通常はドメインレベルと関連付けられますが、これは実装によって異なります。

**[!DNL Activity Map]質問：DTM が、 が必要とするバージョン（1.5.1）よりも古いバージョン（1.3.4）の訪問者 API を自動的に読み込みます。これは問題ですか。**

回答：いいえ。[!DNL Activity Map] 機能はVisitorAPIに依存しません。

## [!DNL Activity Map] 申し込み {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**[!DNL Activity Map]質問：以前に Web サイトで訪問者 ClickMap を使用していなかった場合でも、 を使用できますか。**

回答：以前のバージョン（現在は単に ClickMap と呼びます）がインストールされていることは、新しいバージョンを実装するための前提条件ではありません。アドビでは、限られた期間内ではありますが、以前のバージョンを引き続きサポートします。

**質問：どのブラウザーとバージョンがサポートされていま[!DNL Activity Map]すか。**

回答：4 つの主要ブラウザー（Chrome、Firefox、Safari および IE）の最新バージョンのみをサポートしています。

**質問：デフォルトのオーバーレイ設定は何ですか。**

A: By default, [!DNL Activity Map] shows ALL links that have collected data.

顧客 Web ページの上にポップアップパネルが表示されるとき、ポップアップパネルの下にあるリンクに所属するオーバーレイがポップアップパネルの上に表示される場合があります。

**質問：ランク付けした項目のオーバーレイが一部表示されないのはなぜですか。**

回答：ランク付けされたリンクの一部がページに表示されない場合があります（サブメニューリンクなど）。その結果、対応するリンクオーバーレイも表示されません。そのため、特定のランク値が欠けているオーバーレイランクが見られることが予測できます。ランクはページ内のすべてのリンク（現在表示されているもの + 非表示のもの）に関して計算されるからです。

**質問：すべてのリンクレポートで、リンクのランクはどのように決定されますか。**

* **グラデーション**&#x200B;と&#x200B;**バブルチャート**&#x200B;のモードの場合、ランクは指標列を基準として決定されます。指標の値が同じリンクに関しては、リンク ID のアルファベット順に基づいたランクとなります。
* **勝者と敗者**&#x200B;のモードの場合、ランクは主に % ゲイン列を基準として決定されます。ゲインが同じリンクに関しては、リンク ID のアルファベット順に基づいたランクとなります。

**[!DNL Activity Map]質問： を実行中にリンククリックデータが収集されないのはなぜですか。**

A: While [!DNL Activity Map] is in use, link click data is not collected by the Analytics tag. この動作は、ClickMap プラグインの動作に従っています。

**質問：指標のドロップダウンに同じ指標が複数回表示されるのはなぜですか。**

A: [!DNL Activity Map] lists metrics for all report suites. その結果、[指標の統合処理](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html)をおこなっていない場合は、重複が発生する可能性があります。

指標ドロップダウンを使用すると、訪問したページのレポートスイートに割り当てられたものに計算指標のリストを制限できます。

**質問：すべてのリンク[!DNL Activity Map]レポートは、Reports &amp; Analyticsレポートとどのように比較され[!DNL Activity Map]ますか。**

A:すべてのリンクレポートを取り込むに [!DNL Activity Map]は、次の内訳リクエストを作成します。 [!DNL Activity Map] ページ= "visitedpage"。内の [!DNL Activity Map] Link&amp;Regionで分類されます `<list of link&regions present in the page at rendering time>`。

To get an equivalent report in Reports &amp; Analytics, you would need to first navigate to the [!DNL Activity Map] Page report. There, you would filter for the visited pagename in [!DNL Activity Map]. The visited Pagename is shown in the left column in the [!DNL Activity Map] Page Details Bottom Panel. Once the page has been found, you can break down from that page and choose [!DNL Activity Map] Links &amp; Regions as a secondary dimension.

ただし、R&amp;A で得られたレポートには、そのページ用に収集されたすべてのリンクおよび地域のリストが表示されることに注意する必要があります。But [!DNL Activity Map] only reports on Links&amp;Regions that are currently present in the webpage. そのため、新しいサイトがある場合は、その時点で存在するニュースのみが表示され、その日のもっと早い時間のニュースは表示されません。

**[!DNL Activity Map]質問：複数のレポートスイートを表示する複数のタグを含むページと はどのように連携しますか。**

A: By default, [!DNL Activity Map] uses the report suite that is associated with the first tag that is sent by the page.

別のタグ付きレポートを選択するには、[!DNL Activity Map] Settings／Others タブを使用します。

**[!DNL Activity Map]質問： では、Analytics タグをスキャンするのにどのくらい時間がかかりますか。**

回答：ページ完了イベント後、最長 20 秒かけて Analytics タグをスキャンします。

**質問：動的コンテンツ[!DNL Activity Map]の処理方法**

A: [!DNL Activity Map] checks every 2 seconds to see if it has found changes in the state of the web page such as:

* HTML コンテンツの表示
* HTML コンテンツの非表示
* 新しく挿入された HTML コンテンツ

コンテンツの表示、非表示に変化があった場合、アプリケーションでは影響を受けるリンクの状態（およびオーバーレイ）が、非表示から表示、または表示から非表示に、自動的に変更されます。

新しいコンテンツが挿入された場合、アプリケーションでは関連するリンクを取得し、リンクの分析データを取り込んで、これらのリンクのオーバーレイを追加します。

**質問：ページフローレポートはどんな指標に基づいていますか。**

回答：表示されるデータはすべて、ページビューに基づいています。

**[!DNL Activity Map]質問：様々なタイプのページでの の動作を説明してください。**

*Analytics タグのない Web ページ*

タグが存在しないことを示す警告メッセージがツールバーの下に表示されます。

*互換性のない Analytics タグ（AppMeasurement v1.5 以前）を含む Web ページ*

ページコードをv1.6にアップグレードする必要がある(/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)ことを示す警告メッセージが表示されます。

*[!DNL Activity Map]互換性のある Analytics タグ（AppMeasurement v1.6 以降）を含む Web ページ、ただし、管理ツールで のレポートが有効になっていない場合*

管理者に対して、\[Enable the report\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md")を依頼する必要があることを示す警 [!DNL Activity Map] 告メッセージが表示されます。

**質問：[!DNL Activity Map]Analyticsデータフィードを使用してデータ(contextData)をエクスポー[トできますか](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)。**

A：いいえ。

## セグメント [!DNL Activity Map] 化 {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**質問：セグメントは個々のユーザーセグメントに関連付けられていますか。Or are shared Admin-level segments available in[!DNL Activity Map]?**

A: [!DNL Activity Map] inherits your Admin-level segments (reporting segments) from Analytics.

**質問：セグメントはライブモードで動作しますか。**

回答：いいえ。セグメントはライブモードでは動作しません。機能は、Reports &amp; Analytics のリアルタイムレポートと同等です。

## 仮想レポートスイート{#section_BDB0CA9E732F478EAC349A79753A78DB}

**質問：仮想レポ[!DNL Activity Map]ートスイートと互換性があるか。**

回答：はい。However, due to virtual report suite limitations, [!DNL Activity Map]'s Live Mode is not compatible with virtual report suites.
