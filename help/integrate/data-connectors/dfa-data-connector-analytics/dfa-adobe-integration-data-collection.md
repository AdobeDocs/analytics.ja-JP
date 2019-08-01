---
description: データ収集のしくみを図で示します。
keywords: DFA
seo-description: データ収集のしくみを図で示します。
seo-title: Adobe統合リアルタイムデータ収集
solution: Analytics
title: Adobe統合リアルタイムデータ収集
topic: Data Connectors
uuid: 5dce319c-7d4b-4475-8e6d- dc5c972a82e9
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Adobe 統合：リアルタイムデータ収集{#adobe-integration-real-time-data-collection}

データ収集のしくみを図で示します。

![](assets/DFA_data_collection.png)

Adobe 統合では、データ収集は、訪問者がランディングページに到達すると開始されます（1）。ランディングページで実行されている Adobe データコレクションコードは、訪問者が提示された広告で得た履歴の情報を持ちません。Google DFA チームは、DFA Floodlight サーバーで実行しているサービスを調整して、現在サイトにいる訪問者に関する広告情報を Adobe コードでクエリできるようにします（2）。このデータを取得するには、Adobe イメージビーコンを一時的に遅らせて、Floodlight サーバーからデータをリクエストします。

データが到達した場合、または時間がかかりすぎる場合、Adobe トラッキングサーバーに対してヒットを実行します（3）。

Integrate モジュールは、Adobe イメージビーコンを遅らせて、一定時間（ *`s.maxDelay`*). *`s.maxDelay`* は、イメージタグが訪問者のブラウザーで実行されるまで、Integrate モジュールが DFA Floodlight サーバーからのデータを待機する時間を定義します。この動作は、DFA Floodlight サーバーがダウンしたり負荷が高い場合でも基本的な訪問者データが収集されるので、重要です。Floodlight データが *`s.maxDelay`* の有効期限前に到達する場合、Adobe トラッキングデータは即座に実行され、追加の DFA データが含められます。

タイムアウトが発生した場合、ページコードは、タイムアウトイベントとして使用される Adobe Reports &amp; Analytics イベントを指定できます。このイベントは、統合で診断の問題が発生した場合、または *`s.maxDelay`* と呼ばれる iFrame を読み込みます。In cases where there are excessive timeouts, increase *`s.maxDelay`*. *`s.maxDelay`* は設定できますが、訪問者が *`s.maxDelay`* 期限切れになる前にサイトを離れる可能性がある可能性があります。For more discussion on this topic, see [Tuning s.maxDelay](../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d).

Floodlight サーバーは、訪問者に関するエラーを返すことがあります。これは、通常、訪問者が広告を見ていないか、DFA 訪問者 cookie を持っていないために、Floodlight サーバーが訪問者に関する情報を持たない場合に発生します。ページコードは、これらのエラーを収集し、実装の問題のトラブルシューティングを支援したり、Google トランザクションの問題を指摘できる、カスタムコンバージョン変数（eVar）を指定できます。最も一般的なエラーは、次の表に示す、履歴なし、Cookie なし、クエリエラーおよびオプトアウトです。

| エラー | 名前 | 説明 |
|---|---|---|
| nh | 履歴なし（No History） | 訪問者は広告を表示していないか、クリックしていません。 |
| nc | Cookie なし（No Cookie） | 訪問者は、DFA 訪問者 cookie を持っていません。 |
| qe | クエリエラー（Query Error） | Floodlight サーバーへのデータのクエリ中にエラーが発生しました。 |
| oo | オプトアウト（Opted Out） | 訪問者は、Google インプレッション／クリックトラッキングをオプトアウトしました。 |

