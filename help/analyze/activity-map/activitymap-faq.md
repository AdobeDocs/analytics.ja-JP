---
description: Activity Map での設定や機能の使用に関するよくある質問（FAQ）です。
title: Activity Map の FAQ
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: fa9efcba40ae00c22e99f68f5be8f4d5bf32e44c

---


# Activity Map の FAQ

Activity Map での設定や機能の使用に関するよくある質問（FAQ）です。

## 実装と AppMeasurement

**質問：新規の Activity Map を有効にするための実装手順をおしえてください。**

回答：「[Activity Map の有効化](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)」を参照してください。

**質問：Analytics ユーザーは全員が管理ツールの Activity Map 実施可能ページにアクセスできますか。**

回答：Adobe SiteCatalyst ユーザーは Admin Console の Activity Map 実施可能ページにアクセスできません。Adobe Analytics Standard および Adobe Analytics Premium の契約を締結している企業のみが、この設定ページにアクセスできます。

**質問：新しい AppMeasurement コードは、Dynamic Tag Management（DTM）を使用して設定できますか。**

回答：はい。新しい AppMeasurement コードは[手動で実装](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html)できます。

**質問：AppMeasurement v1.6 ライブラリの大きな変更点は何ですか。**

回答：AppMeasurement v1.6 の唯一の変更点は、Activity Map リンクトラッキングプロセスの手法です。ページ名、リンク ID、地域 ID が必要です。

**質問：AppMeasurement は、特定のページ上ではなく、ドメインレベルでロールアウトされますか。**

回答：AppMeasurement は、レポートスイートレベルでロールアウトされます。レポートスイートレベルは、通常はドメインレベルと関連付けられますが、これは実装によって異なります。

**質問：DTM が、Activity Map が必要とするバージョン（1.5.1）よりも古いバージョン（1.3.4）の訪問者 API を自動的に読み込みます。これは問題ですか。**

回答：いいえ。Activity Map の機能は、訪問者 API には依存しません。

## Activity Map アプリケーション

**質問：Activity Mapでシングルページアプリ(SPA)をサポートする方法を教えてください。**

回答：

* 数秒ごとに、Activity MapはWebページをスキャンし、ページに対する変更を探します。 ActivityMapは、新しいページの読み込みを必要とせずに、ページ上で新しいコンテンツを検索しますが、この新しいコンテンツは、ページの読み込み時に見つかった最初のpageNameに常に関連付けられます。

* Activity Mapは、その情報に基づくリンクの表示が変更されたかどうかを確認します。 表示の変更が見つかった場合、そのリンクの [「ページ上のリンク](/help/analyze/activity-map/activitymap-links-report.md) 」テーブルの「現在」列が、またはで更新さ **[!UICONTROL Displayed]** れま **[!UICONTROL Hidden]**&#x200B;す。

* ユーザー操作によって新しいコンテンツが作成されると、AppMeasurementでリンクとして見つかった新しい要素がテーブルに追加さ **[!UICONTROL Links On Page]** れます。 Activity Mapは、これらの新しいリンクを含む新しいデータリクエストを送信します。 データリクエストがUIで処理され **[!UICONTROL Links On Page]** ると、新しいリンクが表に表示されます。

**質問：Activity Mapは「ビュー」に関するデータを提供しますか。**

A:いいえ。各ページの読み込み時に表示されるすべてのリンクを追跡するには、より多くのデータを収集する必要があります。 無料のアドオンとして、Activity Mapはこの機能を提供しません。

**質問：以前に Web サイトで訪問者 ClickMap を使用していなかった場合でも、Activity Map を使用できますか。**

回答：以前のバージョン（現在は単に ClickMap と呼びます）がインストールされていることは、新しいバージョンを実装するための前提条件ではありません。アドビでは、限られた期間内ではありますが、以前のバージョンを引き続きサポートします。

**質問：Activity Map ではどんなブラウザーおよびバージョンがサポートされていますか。**

A:4つのメインブラウザー(Chrome、Firefox、Safari、IE)の最新バージョンをサポートしています。

**質問：デフォルトのオーバーレイ設定は何ですか。**

回答：デフォルトで、Activity Map は、データを収集したすべてのリンクを表示します。

顧客 Web ページの上にポップアップパネルが表示されるとき、ポップアップパネルの下にあるリンクに所属するオーバーレイがポップアップパネルの上に表示される場合があります。

**質問：ランク付けした項目のオーバーレイが一部表示されないのはなぜですか。**

回答：ランク付けされたリンクの一部がページに表示されない場合があります（サブメニューリンクなど）。その結果、対応するリンクオーバーレイも表示されません。そのため、特定のランク値が欠けているオーバーレイランクが見られることが予測できます。ランクはページ内のすべてのリンク（現在表示されているもの + 非表示のもの）に関して計算されるからです。

**質問：すべてのリンクレポートで、リンクのランクはどのように決定されますか。**

* **グラデーション**&#x200B;と&#x200B;**バブルチャート**&#x200B;のモードの場合、ランクは指標列を基準として決定されます。指標の値が同じリンクに関しては、リンク ID のアルファベット順に基づいたランクとなります。
* **勝者と敗者**&#x200B;のモードの場合、ランクは主に % ゲイン列を基準として決定されます。ゲインが同じリンクに関しては、リンク ID のアルファベット順に基づいたランクとなります。

**質問：Activity Map を実行中にリンククリックデータが収集されないのはなぜですか。**

回答：Activity Map を使用中は、Analytics タグでリンククリックデータデータは収集されません。この動作は、ClickMapプラグインの動作に従います。

**質問：Activity Map のすべてのリンクレポートは、Reports &amp; Analytics の Activity Map レポートとどのように比較されますか。**

回答：Activity Map ですべてのリンクレポートを引き出すには、`<list of link&regions present in the page at rendering time>` の Activity Map のリンクと地域を基準として Activity Map ページ = &quot;visitedpage&quot; を分類する分類リクエストを作成します。

Reports &amp; Analytics で同等のレポートを得るには、まず Activity Map のページレポートに移動する必要があります。次に、Activity Map で訪問されたページ名をフィルターします。訪問されたページ名が、Activity Map のページの詳細下部パネルの左列に表示されます。ページが見つかったら、そのページから分類して、Activity Map のリンクと地域をセカンダリディメンションとして選択できます。

ただし、R&amp;A で得られたレポートには、そのページ用に収集されたすべてのリンクおよび地域のリストが表示されることに注意する必要があります。Activity Map では、Web ページに現在存在するリンクと地域のみが報告されます。そのため、新しいサイトがある場合は、その時点で存在するニュースのみが表示され、その日のもっと早い時間のニュースは表示されません。

**質問：複数のレポートスイートを表示する複数のタグを含むページと Activity Map はどのように連携しますか。**

回答：デフォルトで、Activity Map は、ページから最初に送信されたタグと関連付けられているレポートスイートを使用します。Activity Map 設定／「その他」タブで、別のタグ付きレポートスイートを選択できます。

**質問：Activity Map では、Analytics タグをスキャンするのにどのくらい時間がかかりますか。**

回答：ページ完了イベント後、最長 20 秒かけて Analytics タグをスキャンします。

**質問：Activity Map では、動的コンテンツをどのように処理しますか。**

回答：Activity Map では、2 秒ごとにチェックを行い、Web ページに次のような状態の変化が見つかったかどうかを確認します。

* HTML コンテンツの表示
* HTML コンテンツの非表示
* 新しく挿入された HTML コンテンツ

コンテンツの表示、非表示に変化があった場合、アプリケーションでは影響を受けるリンクの状態（およびオーバーレイ）が、非表示から表示、または表示から非表示に、自動的に変更されます。

新しいコンテンツが挿入された場合、アプリケーションでは関連するリンクを取得し、リンクの分析データを取り込んで、これらのリンクのオーバーレイを追加します。

**質問：ページフローレポートはどんな指標に基づいていますか。**

回答：表示されるデータはすべて、ページビューに基づいています。

**質問：様々なタイプのページでの Activity Map の動作を説明してください。**

*Analytics タグのない Web ページ*

タグが存在しないことを示す警告メッセージがツールバーの下に表示されます。

*互換性のない Analytics タグ（AppMeasurement v1.5 以前）を含む Web ページ*

ページコードをv1.6以上にアップグレードする必要があることを示す警告メッセージが表示されます。

*互換性のある Analytics タグ（AppMeasurement v1.6 以降）を含む Web ページ、ただし、管理ツールで Activity Map のレポートが有効になっていない場合*

\[Activity Map のレポートの有効化\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;)を管理者に依頼する必要があることを示す警告メッセージが表示されます。

**質問：[Analytics データフィード](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html)を使用して Activity Map データ（contextData）を書き出すことはできますか。**

回答：いいえ。

## Activity Map でのセグメント化

**質問：セグメントは個々のユーザーセグメントに関連付けられていますか。Are shared segments available in Activity Map?**

A:Activity Mapは、Analyticsからレポートセグメントを継承します。

**質問：セグメントはライブモードで動作しますか。**

回答：いいえ。セグメントはライブモードでは動作しません。機能は、Reports &amp; Analytics のリアルタイムレポートと同等です。

## 仮想レポートスイート

**質問：Activity Map は、仮想レポートスイートと互換性がありますか。**

回答：はい。ただし、仮想レポートスイートの制限により、Activity Map のライブモードは仮想レポートスイートと互換性がありません。
