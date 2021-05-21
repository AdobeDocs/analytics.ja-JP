---
title: サードパーティの分析プラットフォームから Adobe Analytics への移行
description: Google Analytics などの他のプラットフォームに詳しいユーザー向けに、レポートの取得に関する概要について説明します。
exl-id: e71b12ad-11b7-48a0-8586-f8eb63975479
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '438'
ht-degree: 100%

---

# サードパーティの分析プラットフォームから Adobe Analytics への移行

このガイドでは一般的なレポートタイプを紹介し、アドビとその他の一般的なツールとの主な類似点と相違点に焦点を当てながら、Adobe Analytics の概要と主なワークフローについて説明します。このガイドは、デジタル分析の基本知識があり、Adobe Analytics を初めて使用するアナリストを対象としています。組織において、アドビのデータ収集サーバーにデータを送信する実装が正常におこなわれていることを前提としています。Adobe Analytics を実装していない場合は、まず「[Adobe Analytics はじめての管理ガイド](/help/admin/admin-console/first-admin-guide.md)」を参照してください。

Google Analytics と Adobe Analytics は、Web サイトのパフォーマンスに対する価値あるインサイトを得るための強力なプラットフォームです。それぞれ独自の処理アーキテクチャとユーザーインターフェイスを備えており、異なる利点があります。このガイドは、Google Analytics を使用したことがあるユーザーを対象に、Adobe Analytics の使用方法を説明することを目的としています。

Adobe Analytics では、Adobe Experience Cloud にログインしたあとに基本レポートを取り込む方法が 2 つあります。

* **Reports &amp; Analytics** は、基本レポートを取り込む従来の方法です。左側のメニューには既製レポートのリストが表示され、適切なレポートに移動してデータを取得できます。セグメントと指標をカスタマイズできます。このレイアウトは、Google Analytics のレポートと類似しています。
* **Analysis Workspace** の使用は、現在最も推奨されるレポート取得方法です。左側のメニューでは、コンポーネントをドラッグ＆ドロップして独自のレポートを作成できます。柔軟性が非常に高く、あらゆるレポートニーズに的確に対応します。このレイアウトは、Google Analytics のダッシュボードとカスタムレポートに類似しています。

ほとんどのレポートは、[!UICONTROL Reports &amp; Analytics] と [!UICONTROL Analysis Workspace] の両方で作成できます。ただし、どちらかのプラットフォームでのみ取り込むことができるレポートもあります。特定の機能が [!UICONTROL Reports &amp; Analytics] でのみ使用できる場合を除き基本的には [!UICONTROL Analysis Workspace] の使用をお勧めします。

## 推奨学習パス

アドビでは、レポートデータの取得に関する基本事項の学習から始めることを推奨しています。

* [Google Analytics ユーザー向け：Analysis Workspace での基本レポートの作成方法](reports/create-report.md)

[!UICONTROL Analysis Workspace] のコンポーネントについて理解できたら適切なコンポーネントを使用して様々なレポートを再作成する方法を学習しましょう。

* [Adobe Analytics でのリアルタイムレポートの作成](reports/realtime-reports.md)
* [Adobe Analytics でのオーディエンスレポートの作成](reports/audience-reports.md)
* [Adobe Analytics での獲得レポートの作成](reports/acquisition-reports.md)
* [Adobe Analytics での行動レポートの作成](reports/behavior-reports.md)
* [Adobe Analytics でのコンバージョンレポートの作成](reports/conversions-reports.md)

レポートの取り込み方法を学習し、[処理方法とアーキテクチャの違い](processing-differences.md)を理解できれば、プラットフォーム間で取得される異なる数値を調整できるようになります。[FAQ](faq.md) も参照してください。
