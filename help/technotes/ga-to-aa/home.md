---
title: サードパーティの分析プラットフォームからAdobe Analyticsへの移行
description: Googleアナリティクスなど、他のプラットフォームに精通しているユーザー向けのレポートを取得するための主要概念について説明します。
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# サードパーティの分析プラットフォームからAdobe Analyticsへの移行

このガイドでは、Adobe Analyticsの中核的な概念やワークフローを学習し、Adobe Analyticsと他の一般的なツールの違いに焦点を当てる、基本的な概念やワークフローについて説明します。このガイドは、基本的なデジタル解析概念に精通しているが、Adobe Analyticsの新しい概念に精通していることを目的としています。Adobeデータ収集サーバーにデータを送信する作業環境があることを前提としています。If your organization has not yet set up an Adobe Analytics implementation, start with the [Adobe Analytics First Admin Guide](../../admin/admin-console/first-admin-guide.md).

Google AnalyticsとAdobe Analyticsは共に強力なプラットフォームであり、Webサイトのパフォーマンスに貴重なインサイトを得ることができます。それぞれに独自の処理アーキテクチャとユーザーインターフェイスがあり、各プラットフォーム固有の利点があります。このガイドは、Adobe Analyticsに関してGoogle Analyticsに精通したユーザーを支援するために設計されています。

Adobe Analyticsでは、Adobe Experience Cloudにログインした後に基本レポートを取り込む2つの主な方法があります。

* **Reports&amp; Analytics** は基本的なレポートを引き出すための履歴です。左側のメニューには、プリタブ化されたレポートのリストが表示され、ユーザーは目的のレポートに移動してデータを取得できます。セグメントと指標によって、追加のカスタマイズを提供できます。Google Analyticsレポートに精通しているユーザーは、このレイアウトを熟知している可能性があります。
* **分析ワークスペース** は、ほとんどのレポートを引き出すための現在の推奨方法です。左側のメニューを使用すると、ユーザーはコンポーネントをドラッグ&amp;ドロップして独自のレポートを作成できます。正確なレポートのニーズをはるかに満たすことができます。Google Analyticsのダッシュボードとカスタムレポートの作成経験があるユーザーは、このレイアウトを熟知している可能性があります。

ほとんどのレポートは、Reports&amp; AnalyticsとAnalysis Workspaceの両方で作成できます。ただし、一部のレポートは1つのプラットフォームのみを使用して取り込むことができます。ほとんどの場合、特定の機能がReports&amp; Analyticsでのみ利用可能でない限り、アドビではAnalysis Workspaceの使用を推奨しています。

## 推奨される学習パス

レポートデータの取得については、基本的な基本原則から始めてください。

* [GAユーザー用のAnalysis Workspaceでの基本レポートの作成](reports/create-report.md)

Analysis Workspaceのコンポーネントに慣れたら、適切なコンポーネントを使用して、ほとんどのレポートを再作成する方法を学習できます。

* [Adobe Analyticsでリアルタイムレポートを作成する](reports/realtime-reports.md)
* [Adobe Analyticsでのオーディエンスレポートの作成](reports/audience-reports.md)
* [Adobe Analyticsでの獲得レポートの作成](reports/acquisition-reports.md)
* [Adobe Analyticsでの行動レポートの作成](reports/behavior-reports.md)
* [Adobe Analyticsでのコンバージョンレポートの作成](reports/conversions-reports.md)

After learning to pull reports, understanding [processing and architecture differences](processing-differences.md) can help reconcile the different numbers obtained between platforms. [FAQ](faq.md) もご利用いただけます。
