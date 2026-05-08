---
description: Analysis Workspace でジャーニーキャンバスを使用する方法について説明します。
title: ジャーニーキャンバスの概要
feature: Visualizations
hide: true
role: User, Admin
source-git-commit: f8a0dd0c4b1ab0aa3c5cbb7d2032fafc61aef2db
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 88%

---

# ジャーニーキャンバスの概要 {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="ジャーニーキャンバス"
>abstract="人物が一連のタッチポイントを通過またはフォールアウトする仕組みを示します。 複数のエントリポイントとパスを持つジャーニーに使用します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="ジャーニーキャンバス"
>abstract="人物が定義されたジャーニーを通過またはフォールアウトする仕組みを分析します。 イベント、ディメンション項目およびセグメントの任意の組み合わせを表すノードと矢印の柔軟なグラフを作成して、ユーザージャーニーの分析を作成します。 キャンバス上のノードをドラッグして、ジャーニーのイベントと条件を並べ替えます。 これを行うと、それに応じてデータが更新されます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button2"
>title="ジャーニーキャンバス"
>abstract="人物が一連のタッチポイントを通過またはフォールアウトする仕組みを示します。 複数のエントリポイントとパスを持つジャーニーに使用します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel2"
>title="ジャーニーキャンバス"
>abstract="人物が定義されたジャーニーを通過またはフォールアウトする仕組みを分析します。 イベント、ディメンション項目およびセグメントの任意の組み合わせを表すノードと矢印の柔軟なグラフを作成して、ユーザージャーニーの分析を作成します。 キャンバス上のノードをドラッグして、ジャーニーのイベントと条件を並べ替えます。 これを行うと、それに応じてデータが更新されます。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_この記事では、この記事の_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;版について、_Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg) ![Adobe Analytics_ _**ジャーニー**<br/><br/>_ジャーニーキャンバスの概要](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas)を参照してください。[

>[!ENDSHADEBOX]

{{release-limited-testing}}

ジャーニーキャンバスビジュアライゼーションを使用すると、ユーザーやお客様に提供するジャーニーを分析し、深いインサイトを得ることができます。 ジャーニーを定義し、ジャーニーの途中で離脱した顧客や離脱した顧客を把握できます。

イベント、ディメンション項目、セグメント、日付範囲を任意に組み合わせてジャーニーノードを作成して、[ユーザージャーニーの分析を作成](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)できます。 ノードを接続してジャーニーのフローを作成し、複数のパスと決定ポイントを含めます。 キャンバス上のノードをドラッグして、ジャーニーのイベントと条件を並べ替えます。 変更を行うと、データがリアルタイムで更新されます。

[ ノードは、](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes)を「最終パス」として接続しています。つまり、訪問者は、2つのノード間で発生するイベントに関係なく、最終的に1つのノードから他のノードに移動する限りカウントされます。 ユーザーがパスに沿って移動するために割り当てられた時間は、コンテナの設定によって決まります。

![ジャーニーキャンバス](assets/journey-canvas.png)

## 主な特長

ジャーニーキャンバスビジュアライゼーションの主な機能は次のとおりです。

* 最も複雑なユーザージャーニーに対応するフォールアウトとフォールスルーの詳細な分析。

* ユーザージャーニーの様々なエントリ ポイント、ノード、パスをマッピングおよび視覚化するためのキャンバス。

* キャンバスにコンポーネントを追加したり、既存のノードを再配置したりするためのドラッグ＆ドロップ操作。

## 潜在的なインサイト

ジャーニーキャンバスは、最も複雑なジャーニーに対して実用的なインサイトを提供します。

### コンバージョン率が最も高いパス {#conversion-rate-caption}

ジャーニーキャンバスで最も顕著なインサイトは、キャンバス自体の上部にキャプションとして表示されます。

このキャプションは、ジャーニー内のすべてのパスの中で、コンバージョン率が最も高かったパスを要約したものです。

ジャーニーに複数の開始ノードが含まれる場合、キャプションは次のようになります。

![ジャーニーキャンバスインサイトキャプション](assets/journey-canvas-caption.png)

ジャーニーに単一の開始ノードが含まれる場合、キャプションは次のようになります。

![ジャーニーキャンバスインサイトキャプションの単一の開始ノード](assets/journey-canvas-caption-singlestart.png)

このキャプションを解釈する際は、次の点を考慮します。

* _パス_&#x200B;は、開始ノードと終了ノードが矢印で接続され、その間に任意の数のノードが接続されたものとして定義されます。

* コンバージョン率の計算は、ジャーニーのタイプ（ジャーニーに含まれる開始ノードおよび終了ノードの数と、これらの間のパスが交差するかどうか）によって異なります。

  次の表に、ジャーニータイプに基づくコンバージョン率の計算方法を示します。

  | ジャーニータイプ | コンバージョン率の計算 | 例 |
  |---------|----------|---------|
  | **単一の開始ノードと単一の終了ノード** | コンバージョン率は、終了ノードの数を開始ノードの数で割ることによって計算されます。 | ![複数の開始点が共通のノードに収束するジャーニー](assets/journey-canvas-single-path.png) |
  | **単一の開始ノードと複数の終了ノード** | コンバージョン率は、最大の数値を持つ終了ノードを見つけ、その数値を開始ノードの数値で割ることによって計算されます。 | ![複数の開始点が共通のノードに収束するジャーニー](assets/journey-canvas-singlestart-multiend.png) |
  | **単一の開始ノードと単一の終了ノードが含まれる複数のスタンドアロンパス** | コンバージョン率は、終了ノードの数を開始ノードの数で割ることによって計算されます。 コンバージョン率が最も高いパスがキャプションに記載されます。 | ![複数の開始点が共通のノードに収束するジャーニー](assets/journey-canvas-multi-start-separate.png) |
  | **ジャーニーの任意の時点で共通のノードに収束する複数の開始ノード** | コンバージョン率は、最大の数値を持つ終了ノードを見つけ、その数値を最も低い数値を持つ開始ノードの数値で割ることによって計算されます。 | ![複数の開始点が共通のノードに収束するジャーニー](assets/journey-canvas-multi-start-converge.png) |

### フォールスルー、フォールアウトなど

ジャーニーキャンバスが提供できる他のインサイトの例を以下に示します。 これらのインサイトが、レポートスイート内のすべてのユーザー、ジャーニーを開始したすべてのユーザー、またはジャーニーの前のノードのすべてのユーザーに基づくかどうかを選択できます。

#### フォールスルー

* ジャーニを完了した（終了ノードに到着した）人物の数と割合

* ジャーニーの特定のノードに到達した人物の数と割合

* ジャーニーの特定のノードの後または前に発生した最も一般的な手順

#### フォールアウト

* 人物が最も共通してジャーニーからフォールアウトしたジャーニーのノード（すぐ次のノードのいずれにも到達しなかった）

#### 各ノードの追加データ

* ジャーニーの任意のノードに分類ディメンションを追加して、その特定のノードの追加データを表示します

## ジャーニーキャンバス、フォールアウト、フローのいずれかのビジュアライゼーションの選択

ジャーニーキャンバスビジュアライゼーションは、[フォールアウトビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md)や[フロービジュアライゼーション](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)と似ていますが、重要な違いがあります。

### 違いについて

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### ジャーニーキャンバスを使用するタイミング

ジャーニーキャンバスは、次の場合に不可欠です。

* 複数のエントリポイントとパスを持つジャーニーが関与するフォールアウト分析。

* 事前定義済みのページのシーケンスを使用した、複数のエントリポイントとパスを持つ非線形ジャーニー。

* 事前定義済みのジャーニーに基づく探索的、Ad Hoc Analysis。

* セッション、ユーザー、発生件数以外のプライマリ指標を必要とする分析。

ジャーニーキャンバスビジュアライゼーション、フォールアウトビジュアライゼーションおよびフロービジュアライゼーションの違いを理解するには、[上記の表](#understand-the-differences)を参照してください。

## ジャーニーキャンバスでの分析の作成

Analysis Workspace で使用可能な任意のディメンションまたは指標に基づく分析を、ジャーニーキャンバスで作成できます。 詳しくは、[ジャーニーキャンバスビジュアライゼーションの設定](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)を参照してください。


>[!MORELIKETHIS]
>
> * [Adobe Customer Journey Analytics でのジャーニーキャンバスビジュアライゼーションのガイド](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

