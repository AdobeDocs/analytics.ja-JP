---
description: Adobeは、使用できる様々な計算指標を提供します。 このページでは、これらの指標とその意図された用途を示します。
title: デフォルトの計算指標
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: 61a0292bf2f8ff22b414c2e91da476c1da69d163
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 41%

---

# デフォルトの計算指標

Adobe Analyticsには、最も一般的な使用例に対応するための様々な計算指標が用意されています。 これらの計算指標は、Analysis Workspaceではデフォルトで使用できます。

次に、Adobeが提供する各計算指標と、その計算に使用する基になる関数の一覧を示します。

>[!NOTE]
>
>このページで説明するデフォルトの計算指標に加えて、レポートスイートに計算指標を追加することもできます。
>
>次のことができます。
> * ストリーミングメディア用のデフォルトの計算指標を追加します。詳しくは、 [計算指標](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 既存の指標からカスタム計算指標を作成する ( [計算指標および高度な計算（派生）指標](/help/components/c-calcmetrics/cm-overview.md).



| 計算指標名 | 関数 | 数式 |
| --- | --- | --- |
| ダウンロード計測用リンククリック数 | サイトへのトラフィックを推進するように設計されたリンクをユーザーがクリックした回数。 | `[Campaign Click-throughs]` |
| アクション | アプリで実行されたアクションの合計数 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| アプリのユーザー | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 平均セッション時間（モバイル） | 訪問者が 1 回のセッションでサイトに滞在した平均時間。 | 空白 |
| サイトでの平均時間 | 訪問者がサイトを離れるか離れるまでの平均滞在時間。 | `[Average Time Spent on Site (Seconds)]` |
| バウンス率 | そのページの訪問数に対する、ヒットが 1 回だけ含まれた訪問の割合。 この指標は、バウンス率が最も高いディメンション項目を把握したり、サイトのバウンス率の合計を時間の経過と共に確認したりするのに役立ちます。 | `[Bounces] / [Entries]` |
| ボットページビュー数の比率 | ページビューの合計数に対する、ボットページビューの割合。 | `[Bot Page Views] / [Page Views]` |
| コンテンツベロシティ | 新しいコンテンツがサイト上で作成および公開される速度と、そのコンテンツがユーザーエンゲージメントを生成する速度。 | `[Page Views] / [Visits]` |
| コンバージョン率 | 購入など、目的のアクションを行った訪問者の割合。 | `[Orders] / [Visits]` |
| 入口率 | サイトの合計セッション数と比較した、特定のページでサイトに入った訪問者の割合。 | `[Entries] / [Visits]` |
| 推定ユニーク訪問者 (ITP 2.1) | ITP 訪問者（Safari ブラウザーを使用するユーザー）の場合、個別訪問者数を 2 以下で割ります。 この計算指標は、（CNAME 実装を使用せずに）クライアント側の JavaScript を使用して cookie を設定していることを前提としています。 クライアント側 JavaScript を使用して Cookie を設定する実装は、ITP 2.1 以降に影響を受けました。詳しくは、 [Intelligent tracking prevention](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 」を参照してください。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID の適用範囲 | Experience Cloud ID を持つ訪問者の割合。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 出口率 | 特定のページを表示した後にサイトを離れた訪問者の割合。 | `[Exits] / [Visits]` |
| ITP 2.1 個別訪問者/個別訪問者 | ITP 2.1 Cookie の制限の影響を受けるブラウザーを使用している個別訪問者の割合。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 注文支援 | チャネルまたはソースが、購入に至るまでの顧客のジャーニーに貢献したが、最終的な購入には至らなかった回数。 | `[Orders (Visit Participation)] - [Orders]` |
| 注文件数/訪問回数 | 完了したトランザクションにつながったサイトへの訪問の割合。 | `[Orders] / [Visits]` |
| 注文件数/訪問者数 | サイトの個々の訪問者が発生した注文またはトランザクションの平均数 | `[Orders] / [Unique Visitors]` |
| ページビュー / 推定ユニーク訪問者 (ITP 2.1) | 推定ユニーク訪問者数 (ITP 2.1) で表示されたページの平均数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| ページビュー / ユニーク訪問者 | サイトへの各ユニーク訪問者に表示されたページの平均数。 | `[Page Views] / [Unique Visitors]` |
| ページビュー数/訪問回数 | ユーザーが 1 回のサイト訪問中に表示するページの平均数。 | `[Page Views] / [Visits]` |
| ページベロシティ | コンテンツの一部が生成する追加のページビューの数。 この指標は、どのコンテンツが追加のエンゲージメントを促すかを判断するのに役立ちます。 | `[Page Views] / [Visits]` |
| リロード回数/ページビュー数 | ページのリロードまたは更新につながったページビューの割合。 | `[Reloads] / [Page Views]` |
| 売上高/注文 | サイト上で完了したトランザクションまたは注文ごとに生成された平均収益額。 | `[Revenue] / [Orders]` |
| 売上高/訪問回数 | サイトへの 1 回の訪問で得られる平均収益額。 | `[Revenue] / [Visits]` |
| 売上高/訪問者 | サイトへの各訪問者個人が生成した平均収益額。 | `[Revenue] / [Unique Visitors]` |
| 状態ビュー | アプリの様々な状態または画面へのビュー数 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| 滞在時間/ユーザー（状態） | 平均訪問者がサイトで特定の状態に滞在した時間の長さ。 | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 個別訪問者数/7 日後に再訪する個別訪問者数 | 7 日以上の期間の後に再訪問するユニーク訪問者の割合。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| ユーザー（モバイル） | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 訪問回数/訪問者 | ユニーク訪問者がサイトに訪問した平均回数。 | `[Visits] / [Unique Visitors]` |
| 重み付けられた直帰率 | 関数 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
