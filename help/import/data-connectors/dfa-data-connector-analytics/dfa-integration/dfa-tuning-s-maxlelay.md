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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# s.maxDelay の調整{#tuning-s-maxdelay}

DFA を正しく導入することが、特定のサイトの s.maxDelay の最適化に影響します。

一般的に、上昇または下降 *`s.maxDelay`* への意思決定は、より多くのDFA訪問者データを取得し、Adobe訪問者データの収集を危険にさらすことに関与します。Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. s.maxDelay を減らすと、Adobe 訪問者データのコレクションは守られますが、DFA 訪問者データを失う可能性があります。

*`s.maxDelay`* は、単なる DFA に接続するためのネットワーク通信の時間以上のものをカプセル化します。また、これらの通信が基にする JavaScript を実行および評価するためのブラウザー遅延を表します。これは、IntegrateモジュールがDFA Floodlightサーバーからデータを取り込むDOMにHTML要素を挿入した後に *`s.maxDelay`* 、Integrateモジュールがタイマーを開始するからです。この新しい HTML エレメントに基づいてブラウザーが実際に HTTP リクエストを開始するまでにかかる時間は、同時に読み込まれる他のイメージまたは JavaScript ファイル、訪問者のコンピューターの速度、特定のブラウザー実装に基づいて変化します。さらに、JSON データが DFA Floodlight サーバーから取得される際に、JavaScript はブラウザーによって評価される必要があります。これもまた、ブラウザーによって完全に制御され、同時に実行する大量の JavaScript コードがある場合や多くの非同期 JavaScript リクエストがある場合は、遅延する可能性があります。

このことを考慮して、*`s.maxDelay`* は、ランディングページの複雑さに加えて、DFA のネットワーク遅延の量に応じて設定する必要があります。一部のサイトで複雑さを軽減する 1 つの方法は、ページ読み込みの早い段階で Adobe コレクションコードを実行することです。これにより、Floodlight サーバーがリクエストされるときのブラウザーでの負荷が軽減されます。

タイムアウト変数は、s.maxDelay タイムアウトに達するたびに増えるので、*`s.maxDelay`*&#x200B;に設定されます。このプロセスを増やすか減らす *`s.maxDelay`* かを決定する際は、次の手順に従うことをお勧めします。

1. 特定の値に *`s.maxDelay`* 設定された数日間のデータを収集します。
1. 時間範囲 [!DNL Daily Unique Visitors Report] 用にを実行します。
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. タイムアウトは、訪問者ごとに 1 回のみ収集されることに注意してください。

数字を入手したら、次を計算します。

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

タイムアウトの割合では、実際はサイトへのすべての訪問者が考慮されます。一部の訪問者は、DFA にまったく結び付けられず、タイムアウトは誤った結果になる可能性があります。To improve this computation, another analysis could consider only unique visitors to pages with the `clickThroughParam` set (for example, `?CID=1`). これは、より正確に表示します。

タイムアウトの割合が非常に低い場合、*`s.maxDelay`* と呼ばれる iFrame を読み込みます。If it is very high, increase *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

タイムアウトは、統合のバー-ジョン 2.0 に移行すると、302 リダイレクトが排除されるので、減少することが予想されます。ベータクライアントでの初期のテストでは、タイムアウトに一貫した減少が見られました。従って、より多くの DFA データが収集されます。
