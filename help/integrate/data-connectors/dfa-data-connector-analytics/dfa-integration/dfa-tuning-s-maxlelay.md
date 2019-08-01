---
description: DFA を正しく導入することが、特定のサイトの s.maxDelay の最適化に影響します。
keywords: DFA
seo-description: DFA を正しく導入することが、特定のサイトの s.maxDelay の最適化に影響します。
seo-title: s.maxDelay の調整
solution: Analytics
title: s.maxDelay の調整
topic: Data Connectors
uuid: 7640af26-6ac6-427e-9cfc-932c86cpf5ab
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# s.maxDelay の調整{#tuning-s-maxdelay}

DFA を正しく導入することが、特定のサイトの s.maxDelay の最適化に影響します。

In general, the decision to raise or lower *`s.maxDelay`* involves a tradeoff between obtaining more DFA visitor data and endangering collecting Adobe visitor data. Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. s.maxDelay を減らすと、Adobe 訪問者データのコレクションは守られますが、DFA 訪問者データを失う可能性があります。

*`s.maxDelay`* は、単なる DFA に接続するためのネットワーク通信の時間以上のものをカプセル化します。また、これらの通信が基にする JavaScript を実行および評価するためのブラウザー遅延を表します。This is because the Integrate module begins the *`s.maxDelay`* timer after it has inserted the HTML element in to the DOM which pulls the data from the DFA Floodlight server. この新しい HTML エレメントに基づいてブラウザーが実際に HTTP リクエストを開始するまでにかかる時間は、同時に読み込まれる他のイメージまたは JavaScript ファイル、訪問者のコンピューターの速度、特定のブラウザー実装に基づいて変化します。さらに、JSON データが DFA Floodlight サーバーから取得される際に、JavaScript はブラウザーによって評価される必要があります。これもまた、ブラウザーによって完全に制御され、同時に実行する大量の JavaScript コードがある場合や多くの非同期 JavaScript リクエストがある場合は、遅延する可能性があります。

このことを考慮して、*`s.maxDelay`* は、ランディングページの複雑さに加えて、DFA のネットワーク遅延の量に応じて設定する必要があります。一部のサイトで複雑さを軽減する 1 つの方法は、ページ読み込みの早い段階で Adobe コレクションコードを実行することです。これにより、Floodlight サーバーがリクエストされるときのブラウザーでの負荷が軽減されます。

タイムアウト変数は、s.maxDelay タイムアウトに達するたびに増えるので、*`s.maxDelay`*&#x200B;に設定されます。When deciding whether to increase or decrease *`s.maxDelay`* we recommend following this process:

1. Collect several days of data with *`s.maxDelay`* set to a particular value.
1. Run a [!DNL Daily Unique Visitors Report] for the time range.
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. タイムアウトは、訪問者ごとに 1 回のみ収集されることに注意してください。

数字を入手したら、次を計算します。

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

タイムアウトの割合では、実際はサイトへのすべての訪問者が考慮されます。一部の訪問者は、DFA にまったく結び付けられず、タイムアウトは誤った結果になる可能性があります。To improve this computation, another analysis could consider only unique visitors to pages with the `clickThroughParam` set (for example, `?CID=1`). これは、より正確に表示します。

タイムアウトの割合が非常に低い場合、*`s.maxDelay`* と呼ばれる iFrame を読み込みます。If it is very high, increase *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

タイムアウトは、統合のバー-ジョン 2.0 に移行すると、302 リダイレクトが排除されるので、減少することが予想されます。ベータクライアントでの初期のテストでは、タイムアウトに一貫した減少が見られました。従って、より多くの DFA データが収集されます。
