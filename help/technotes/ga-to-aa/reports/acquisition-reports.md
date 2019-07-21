---
title: Adobe Analyticsの獲得レポート
description: Analysis Workspaceを使用して獲得ベースのレポートを作成する方法について説明します。
translation-type: tm+mt
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042

---


# 獲得レポート

獲得レポートには、サイトへの訪問者の獲得方法が表示されます。

In Adobe Analytics, these reports are known as **Marketing Channels**. 基本的な初期セットアップが必要ですが、より多くのカスタマイズされたチャネル表示が可能です。

> [!IMPORTANT]
>
> これらのレポートを使用するようにマーケティングチャネルの処理ルールを設定します。See [Getting Started with Marketing Channels](../../../components/c-marketing-channels/c-getting-started-mchannel.md) for information on how to best configure Marketing Channels in your organization.

このページでは、Analysis Workspaceの使用に関する基本的な知識があると想定しています。See [Create a basic report in Analysis Workspace for Google Analytics users](create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## すべてのトラフィック-チャネル

訪問者がサイトに到達するために使用するすべてのチャネルの集計ビューを表示します。

1. In the Components menu, locate the **Marketing Channel** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## すべてのトラフィック-トレープマップ

チャネルトラフィックのトレリマップを表示します。このレポートはすべてのトラフィック-チャネルに似ていますが、異なる方法で表示されます。

1. 左側のビジュアライゼーションアイコンをクリックし、空のフリーフォームテーブルの上にあるワークスペースにトレリマップビジュアライゼーションをドラッグします。
2. Click the Components icon on the left, then drag the **Marketing Channel** dimension onto the large freeform table area labeled 'Drop a dimension here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.
4. 追加の指標では、追加のトレリマップが作成されます。1つのトレープマップのみが必要な場合:
   1. 目的の指標の上部のセルをクリックして、トレリマップを表します。
   2. 同じ指標列の最後のセルをShiftキーを押しながらクリックすると、その列が青色で強調表示されます。正しく実行されると、ビジュアライゼーションに1つのトレープマップが存在します。
   3. トレリマップビジュアライゼーションの右上隅にある色付きの点をクリックし、チェックボックスの「選択をロック」をクリックします。

トレーママップはマーケティングチャネルだけではなく、あらゆるディメンションに適用できます。

## All Traffic- Source/Medium

ソースレポートと媒体レポートには、サイトへのトラフィックを導いたドメインが表示されます。

* **ソース** のプライマリディメンションは、Analysis Workspaceで **参照ドメイン** ディメンションとして使用できます。
* **Medium** プライマリディメンションは **、リファラータイプ** ディメンションとしてAnalysis Workspaceで使用できます。
* **キーワード** のプライマリディメンションは、Analysis Workspaceで **検索キーワード** ディメンションとして使用できます。

1. コンポーネントメニューで、前述の目的のディメンションを見つけて、「ここにディメンションをドロップ」というラベルの大きなフリーフォームテーブル領域にドラッグします。
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

それぞれのディメンションについて詳しくは、「コンポーネントユーザーガイド」の次のページを参照してください。

* [参照ドメイン](../../../components/c-variables/dimensionslist/reports-referring-domains.md)
* [リファラータイプ](../../../components/c-variables/dimensionslist/reports-ref-types.md)
* [検索キーワード](../../../components/c-variables/dimensionslist/reports-search-keywords.md)

## すべてのトラフィック-照会

* **ソース** のプライマリディメンションは、Analysis Workspaceで **参照ドメイン** ディメンションとして使用できます。
* **ランディングページ** のプライマリディメンションは、Analysis Workspaceで **入口ページ** ディメンションとして使用できます。

1. In the components menu, locate the **Referring Domain** or **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

See the [Referring Domain](../../../components/c-variables/dimensionslist/reports-referring-domains.md) dimension in the Components user guide for more information.

## Google広告レポートおよび検索コンソールレポート

Adobeは、Analysis Workspaceと呼ばれる分析ワークスペースの機能を使用して、Googleを含め、複数のプラットフォームから広告および検索データを取り込みます。

広告分析機能には、データを返すための設定が必要です。See [Advertising Analytics Help](../../../integrate/c-advertising-analytics/overview.md) for details on how to enable these additional dimensions in Analysis Workspace.

## Social レポート

Socialレポートは、ソーシャルネットワークのコンテキストを除き、それぞれの行動レポートと同様の情報を提供します。このデータは、ディメンションとセグメントを組み合わせて、Analysis Workspaceで使用できます。

訪問者が同じセッションで複数のチャネルを通してサイトに到達することがあります。例えば、訪問者がソーシャルメディアページをクリックしてから数分間後に、数分間後に検索エンジンを訪問したとします。この場合、ソーシャルドメイン以外のドメインがこのレポートに表示されます。ソーシャル以外のドメインを除外する場合は、訪問回数でレポートを並べ替えたり、訪問ではなくヒットに基づいてセグメントのコピーを作成したりします。See [Segmentation Containers](../../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### Social-ネットワーク照会

ネットワーク照会レポートは、どのソーシャルネットワークドメインがサイトにトラフィックを導いたかを示します。This data is available in Analysis Workspace using the **Referring Domain** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Referring Domain** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social-ランディングページ

ランディングページレポートは、ソーシャルネットワークを通してリンクをクリックした後に訪問者が辿ったページを示します。This data is available in Analysis Workspace using the **Entry Page** dimension and **Visits from Social Sites** segment.

1. In the Components menu, locate the **Entry Page** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. In the Components menu, locate the **Visits from Social Sites** segment and drag in onto the small area just above the freeform table labeled 'Drop a segment here'.
3. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

### Social-コンバージョン

コンバージョンレポートは、ソーシャルネットワークのコンテキストにおけるeコマースデータを表示します。これらのレポートを両方のプラットフォームで使用するには、追加の実装が必要です。アドビでは、このデータがAnalysis Workspace用に正しく構成されていることを確認するために、導入コンサルタントと協力することを推奨しています。

### Social- Plugins

プラグインレポートは、サイト上の埋め込みソーシャルメディアプラグインと訪問者がどのようにやりとりしたかを示します。Analysis Workspaceで使用するには、追加の実装が必要です。アドビでは、このデータが正確に収集されるように、導入コンサルタントに相談することを推奨しています。

### Social-ユーザーフロー

ユーザーフローレポートは、ソーシャルネットワーク経由で到着した訪問者のコンテキストデータを示します。

1. 左側のビジュアライゼーションアイコンをクリックし、フロービジュアライゼーションをフリーフォームテーブルの上のワークスペースにドラッグします
2. Click the Components icon on the left, then drag the **Visits from Social Sites** segment onto the small area just above the flow visualization labeled 'Drop a Segment here'.
3. **ページ** ディメンションを見つけて、矢印アイコンをクリックしてページ値を表示します。ディメンション値は黄色で表示されます。
4. 開始するページ値を探し、「ディメンションまたは項目」という名前のスペースにドラッグします
5. このフローレポートはインタラクティブです。任意の値をクリックして、後続のページまたは前のページにフローを展開します。右クリックメニューを使用して、列を展開または折りたたみます。同じフローレポート内でも異なるディメンションを使用できます。

## キャンペーン-すべて

The campaigns report is available in Analysis Workspace using the **Tracking Code** dimension. トラッキングコードディメンションを使用するには、データを収集するための追加の実装が必要です。

カスタム変数（eVar）を使用して、Adobe AnalyticsでUTMパラメーターを収集できます。Adobe Analyticsでトラッキングコードの値が正確に収集されるように、導入コンサルタントに相談することをお勧めします。

1. In the Components menu, locate the **Tracking Code** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## キャンペーン-有料キーワード

有料キーワードレポートは、訪問者が検索エンジンから有料検索リンクをクリックした後にどのように実行されるかを示します。**検索キーワード-有料** ディメンションはAnalysis Workspaceで使用できますが、データ収集には有料検索検知の1回限りの設定が必要です。See [Paid Search Detection](../../../admin/admin/paid-search-detection/paid-search-detection.md) in the Admin user guide for setup details.

1. In the Components menu, locate the **Search Keyword - Paid** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## キャンペーン-オーガニックキーワード

オーガニックキーワードレポートは、訪問者が検索エンジンからオーガニック検索リンクをクリックした後にどのように実行されるかを示します。**検索キーワード-自然** ディメンションは、Analysis Workspaceで使用できます。有料検索検知が設定されていない場合、このディメンションは有料キーワードと自然キーワードの両方を収集します。

1. In the Components menu, locate the **Search Keyword - Natural** dimension and drag it onto the large freeform table area labeled 'Drop a Dimension here'.
2. Drag the desired metrics onto the workspace alongside the automatically created **Occurrences** metric. See the [Metric translation guide](common-metrics.md) for details on how to obtain each respective metric.

## コスト分析

このレポートには、有料マーケティングチャネルの訪問、コスト、売上高のパフォーマンスデータが表示されます。アドビは、Adobe Advertising Cloudというインサイトを提供する専用の製品を提供しています。組織がこの製品の使用を希望する場合は、貴社のアカウントマネージャーにお問い合わせください。
