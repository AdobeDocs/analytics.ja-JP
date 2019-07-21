---
title: Analyticsプラットフォームの処理とアーキテクチャの違い
description: Adobe AnalyticsやGoogle Analyticsなどのプラットフォーム間でのデータの収集方法と表示方法について説明します。
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Analyticsプラットフォームの処理とアーキテクチャの違い

Adobe AnalyticsとGoogle Analyticsは共にAnalyticsツールですが、プラットフォーム間でデータを収集して処理する方法は非常に異なります。このページを使用して、特定のディメンションや指標がどのように収集されるか、および同様のレポートで異なる数字を表示する理由について説明します。

## バウンス率

直帰率は、ほとんどの解析ツールで有効性とランディングページの関連性を測定するのに役立つ一般的なKPIです。これは一般に、Webサイトに入ってきたが、別のページにクリックを含まない訪問として定義されています。

* In Adobe Analytics, Bounce Rate is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, Bounce Rate is calculated using the formula **Single-page sessions divided by Sessions**.

両方のプラットフォームで、同じ訪問またはセッションで複数のヒットが送信された場合、バウンスと見なされません。Adobe Analyticsでは、カスタムリンクは使用でき、訪問がバウンスとしてカウントされるのを防ぐことができます。通常、Google Analyticsは同じページに複数のデータリクエストを送信しません。

レポートツール間でより優れた結果を得るには、計算指標の一部としてバウンスの代わりに、Adobe Analyticsの直帰数指標を使用します。直帰数指標には、1ページビューのみが含まれているが、その他のページにクリックを含まない訪問者数の合計が含まれます。

See the [Bounce Rate](../../components/c-variables/c-metrics/metrics-bounce-rate.md) metric in the Components user guide for more information.

## 訪問回数とセッション数

訪問回数（Google Analyticsのセッションと呼ばれる）は、同じユーザーが短時間で行ったページビューのグループです。通常、両方のプラットフォームでの訪問は、無操作状態が30分間続くと有効期限が切れます。どちらのプラットフォームでも、訪問の有効期限が切れるとカスタマイズが可能になります。各プラットフォームに違いが生じる可能性があるシナリオがいくつかあります。

* **終了日:** Google Analyticsのすべてのセッションは、特定の日に午後11時59分に終了します。ユーザーが午前12時以降にサイトで引き続きアクティブになっている場合は、新しいセッションが作成されます。Adobe Analyticsは、同じ訪問の一部として次の日に引き続き訪問します。
* **異なるキャンペーン:** Google Analyticsの新しいセッションは、ユーザーのキャンペーンソースが変更された場合に開始されます。Adobe Analyticsで新しいトラッキングコード値が表示された場合、その値は同じ訪問の一部と見なされます。
* **手動セッションの上書き:** Google Analyticsの新しいセッションは、セッションを手動で `sessionControl` 開始または終了するときに開始します。訪問回数は、Adobe Analyticsで手動で終了することはできません。
* **Adobe Analyticsでの外れ訪の検出:** Adobe Analyticsの新しい訪問は、ユーザーが12時間連続してアクティビティ、2500ヒットまたは100秒以内に100ヒットに達すると自動的に開始されます。これらの検出条件はそれぞれボットアクティビティによってトリガーされます。

See the [Visits](../../components/c-variables/c-metrics/metrics-visit.md) metric in the Components user guide for more information.
