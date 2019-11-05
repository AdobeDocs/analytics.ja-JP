---
title: サードパーティの分析プラットフォームから Adobe Analytics への移行
description: Google Analyticsなど、他のプラットフォームに詳しいユーザーを対象にした、レポートを取得するための主要概念について説明します。
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# サードパーティの分析プラットフォームから Adobe Analytics への移行

このガイドでは、Adobe Analyticsの主要な概念とワークフローを学ぶのに役立つ、アドビと他の一般的なツールとの主な類似点と違いに焦点を当てた一般的なレポートタイプを示します。 このガイドは、デジタル解析の基本概念に詳しいが、Adobe Analyticsを初めて使用するアナリストを対象としています。 組織に、アドビのデータ収集サーバーにデータを送信する実装が正常に行われていることを前提としています。 組織でAdobe Analyticsの実装をまだ設定していない場合は、まず『 [Adobe Analytics First Admin Guide』を参照してください](/help/admin/admin-console/first-admin-guide.md)。

Google AnalyticsとAdobe Analyticsは、Webサイトのパフォーマンスに対する価値あるインサイトを得るための強力なプラットフォームです。 それぞれに独自の処理アーキテクチャとユーザーインターフェイスがあり、プラットフォームごとに異なる利点があります。 このガイドは、Google Analyticsでの経験を持つユーザーをAdobe Analyticsに適合させるのに役立つように設計されています。

Adobe Analyticsでは、Adobe Experience cloudにログインした後に基本レポートを取り込む方法は2つあります。

* **Reports &amp; Analyticsは** 、基本的なレポートを取り込む過去の方法です。 左側のメニューには、プレハブレポートのリストが表示され、ユーザは必要なレポートに移動してデータを取得できます。 セグメントと指標は、追加のカスタマイズを提供できます。 Google Analyticsのレポートに慣れているユーザーは、このレイアウトを使い慣れていると思われます。
* **ほとんどのレポートを取り込むには** 、Analysis Workspaceが推奨される方法です。 左側のメニューを使用すると、ユーザーはコンポーネントをドラッグ&amp;ドロップして独自のレポートを作成できます。 これにより、正確なレポートのニーズを満たすための自由度が大幅に向上します。 Google Analyticsのダッシュボードとカスタムレポートの作成経験がある方は、このレイアウトを使い慣れていると思います。

ほとんどのレポートは、Reports &amp; AnalyticsとAnalysis Workspaceの両方で作成できます。 ただし、一部のレポートは、一方のプラットフォームを使用してのみ取り込むことができます。 特定の機能がReports &amp; Analyticsでのみ使用できる場合を除き、ほとんどの場合、Analysis Workspaceの使用をお勧めします。

## 推奨学習パス

レポートデータの取得に関する基本事項から始めることをお勧めします。

* [Analysis Workspace for GA での基本レポートの作成](reports/create-report.md)

Analysis Workspaceのコンポーネントについて理解したら、適切なコンポーネントを使用してほとんどのレポートを再作成する方法を学ぶことができます。

* [Adobe Analyticsでリアルタイムレポートを作成する](reports/realtime-reports.md)
* [Adobe Analyticsでのオーディエンスレポートの作成](reports/audience-reports.md)
* [Adobe Analyticsでの獲得レポートの作成](reports/acquisition-reports.md)
* [Adobe Analyticsでの行動レポートの作成](reports/behavior-reports.md)
* [Adobe Analyticsでのコンバージョンレポートの作成](reports/conversions-reports.md)

レポートの取り込みを学習した後、処理とア [ーキテクチャの違いを理解する](processing-differences.md) と、プラットフォーム間で取得される異なる数値を調整できます。 FAQも [あり](faq.md) 、
