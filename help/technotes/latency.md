---
description: The following information can help troubleshoot report suite latency issues in Analytics data.
keywords: missing data;slow
seo-description: 次の情報は、Analyticsデータのレポートスイートの遅延の問題のトラブルシューティングに役立ちます。
seo-title: データの可用性と遅延
solution: Analytics
subtopic: 現在のデータ
title: データの可用性と遅延
topic: レポート
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Adobe Analyticsでのデータの可用性と遅延

通常、データが収集されてから2時間後に、レポートに完全なデータが表示されることが予想されます。 次の情報は、Analyticsデータのレポートスイートの遅延の問題のトラブルシューティングに役立ちます。

## データのバッチ処理について

各データ収集サーバーは、生の解析データをキャプチャし、処理して、レポートを作成するために 1 時間単位でバッチデータをアップロードします。転送プロセスには、通常、30 分かかります。そのため、前回のアップロードプロセスが完了した直後に発生したトラフィックの通常の遅延は約 90 分になります（次のバッチアップロードが実行されるまで 60 分かかり、その後、ファイルの転送と表示に 30 分かかります）。アップロードの直前に発生するトラフィックの場合、データの遅延は30分ほど短くなる可能性があります（次のバッチアップロードが発生するまで0分、ファイルの転送と表示に30分かかります）。

If needed, Adobe Customer Care can enable 30 minute batched data uploads (instead of hourly) for your most-used report suites.

## Contributors to latency

Latency is a delay that is longer than the typical 2 hours it takes for data collection servers to fully process data. It does not affect data collection; data is still collected for a working implementation, regardless of how latent a report suite is. Its severity (how current the data is) and length (the time it takes to resolve) can vary greatly. It is usually limited to a single report suite.

遅延は、次の一般的なカテゴリのいずれかによって生じます。

* **** 予期しないトラフィックの急増：このタイプの遅延は、契約上のコミットや予想以上に多くのデータがレポートスイートに送信される場合に発生します。 遅延の最も一般的な原因でもあります。
* **** Normal hardware issues: Adobe employs best-in-class strategies for data center management and monitoring, data redundancy, and hardware reliability. ハードウェアは定期的に、公開されているメンテナンス時間枠内に更新されます。Emergency maintenance of failing hardware can require a necessary and temporary halt in data processing (not in data collection) as replacement hardware is brought online. このデータ処理の一時的な停止により、明らかな遅延が発生する場合があります。
* **** 異常なデータ：ボットやクローラーによる異常な長さの訪問など、不自然なデータパターンは、特定の処理負荷を一時的に増やして遅延を引き起こす可能性があります。

## 遅延に依存する機能

Some capabilities in the Adobe Experience Cloud come with an innate amount of latency on top of standard processing time.

* Analytics for Target (A4T) requires an additional 5-10 minutes of latency to allow collected data from both platforms to be stored in the same hit.
* タイムスタンプ付きのデータは、このデータが処理されるサーバーが異なるので、追加の時間が必要です。 リアルタイムに受信したタイムスタンプ付きのヒットは、最大15分かかる場合があります。 Hits received with a timestamp of yesterday can take up to 2 hours. Older hits can take longer, increasing each day up to a cap of approximately 24 hours.

## 遅延を軽減または防止する方法

遅延の防止や回復時間の短縮を実現する幾つかの方法があります。

* **** Notify Adobe of expected traffic spikes: While it is impossible to anticipate every traffic spike to your site, there may be cases where you are expecting to receive a significant increase in traffic. Examples include a particularly successful holiday period, or shortly after a large campaign push. そのような場合、予想されるトラフィックの上昇についてアドビに通知を送る仕組みがあり、Adobe では該当するレポートスイートに追加のプロセシング用リソースを割り振ることができます。See Schedule a traffic spike in the Admin user guide to learn how to notify Adobe of increased traffic.[](../admin/c-traffic-management/t-traffic-schedule-spike.md)
* **** 新しい機能をアクティブ化する際は、処理の負荷を考慮します。一部の機能は、他の機能よりも処理の負荷が高くなります。 レポートスイートで有効にされている機能が多いほど、遅延から回復するのが遅くなります。レポートスイートで機能を有効にする際、次のような場合には処理するデータ量が増えることを念頭に置きます。

   * Implementing more than 20 events on the same page
   * 複雑な VISTA ルール
   * 製品変数に 20 を超える値がある
   * イベントのシリアル化

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/c_bot_rules.html) can greatly reduce latency if your report suite is frequented by bots or crawlers. [Interactive Advertising Bureau](https://www.iab.net/about_the_iab) が更新し管理する IAB ボットリストを使用することが推奨されています。ユーザーは、IABのボットルールを補完するために独自のボットルールをカスタマイズできます。

## 遅延の対処法

In cases where latency occurs, rest assured that Adobe proactively monitors the processing pipeline and does everything possible to return processing time back to normal as quickly as possible. 遅延問題の多くは数時間で解決します。特定のレポートスイートについて問題が生じた場合、貴社のサポート対象ユーザーがカスタマーケアに連絡して、遅延の生じているレポートスイート ID を伝えることができます。Adobe の担当者が遅延を検証し、問題の改善と解決の見通しについて連絡します。
