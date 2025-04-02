---
description: アドビでは、ユーザーが使用できる様々な計算指標を提供しています。このページでは、これらの指標とその使用目的を一覧表示します。
title: デフォルトの計算指標
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: ht
source-wordcount: '735'
ht-degree: 100%

---

# デフォルトの計算指標

Adobe Analytics には、最も一般的なユースケースに対応するための、様々な計算指標が用意されています。これらの計算指標は、デフォルトで Analysis Workspace で使用できます。

アドビが提供する各計算指標、それらが意図する関数、その計算に使用される基になる数式のリストを以下に示します。

>[!NOTE]
>
>このページで説明しているデフォルトの計算指標に加えて、レポートスイートに追加の計算指標を追加することもできます。
>
>次のことができます。
>
> * [計算指標](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html?lang=ja)の説明に従って、ストリーミングメディアコレクションのデフォルトの計算指標を追加する
> * [計算指標と高度な計算指標](/help/components/c-calcmetrics/cm-overview.md)の説明に従って、既存の指標からカスタムの計算指標を作成する。


| 計算指標名 | 関数 | 数式 |
| --- | --- | --- |
| 獲得リンクのクリック数 | サイトへのトラフィックを推進するように設計されたリンクを人物がクリックした回数。 | `[Campaign Click-throughs]` |
| アクション | アプリで実行されたアクションの合計数 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| アプリユーザー | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| セッションの平均長さ（モバイル） | 訪問者が単一セッション中にサイトに滞在した平均時間。 | 空白 |
| 平均サイト滞在時間 | 訪問者がサイトを離れたり移動したりする前にサイトに滞在した平均時間。 | `[Average Time Spent on Site (Seconds)]` |
| バウンス率 | そのページの訪問数と比較した、確実に 1 つのヒットを含む訪問の割合。この指標を使用すると、バウンス率が最も高いディメンション項目を把握したり、サイトのバウンス率の合計の推移を確認したりできます。 | `[Bounces] / [Entries]` |
| ボットページビュー数の割合 | ページビューの合計数と比較した、ボットページビュー数の割合。 | `[Bot Page Views] / [Page Views]` |
| コンテンツベロシティ | 新しいコンテンツがサイト上で作成および公開される速度と、そのコンテンツがユーザーエンゲージメントを生成する速度。 | `[Page Views] / [Visits]` |
| コンバージョン率 | 購入など、目的のアクションを行った訪問者の割合。 | `[Orders] / [Visits]` |
| エントリ率 | サイトの合計セッション数と比較した、特定のページでサイトに入った訪問者の割合。 | `[Entries] / [Visits]` |
| 推定ユニーク訪問者（ITP 2.1） | ITP 訪問者（Safari ブラウザーのユーザー）の場合は、ユニーク訪問者数を 2 以下で割ります。この計算指標は、クライアントサイド JavaScript（CNAME 実装を使用しない）を使用して Cookie が設定されていることを前提としています。ITP 2.1 以降、クライアントサイド JavaScript を使用して Cookie を設定する実装に影響がありました。詳しくは、[Intelligent Tracking Prevention](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) を参照してください。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID の適用範囲 | Experience Cloud ID を持つ訪問者の割合。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 離脱率 | 特定のページを閲覧した後にサイトを離れた訪問者の割合。 | `[Exits] / [Visits]` |
| ITP 2.1 ユニーク訪問者 / ユニーク訪問者 | ITP 2.1 cookie 制限の影響を受けたブラウザーを使用しているユニーク訪問者の割合。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 購入支援 | チャネルまたはソースが、購入に至るまでの顧客のジャーニーに貢献したが、最終的な購入には至らなかった回数。 | `[Orders (Visit Participation)] - [Orders]` |
| 購入回数 / 訪問回数 | 完了したトランザクションにつながったサイトへの訪問の割合。 | `[Orders] / [Visits]` |
| 購入回数 / 訪問者 | サイトへの各訪問者が生成した注文またはトランザクションの平均数。 | `[Orders] / [Unique Visitors]` |
| ページビュー / 推定ユニーク訪問者（ITP 2.1） | 推定ユニーク訪問者数（ITP 2.1）で表示されたページの平均数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| ページビュー / ユニーク訪問者 | サイトへの各ユニーク訪問者に表示されたページの平均数。 | `[Page Views] / [Unique Visitors]` |
| ページビュー / 訪問回数 | ユーザーが 1 回のサイト訪問中に表示するページの平均数。 | `[Page Views] / [Visits]` |
| ページ速度 | コンテンツが生成する追加のページビューの数。この指標は、追加のエンゲージメントを推進するコンテンツを判断するのに役立ちます。 | `[Page Views] / [Visits]` |
| リロード回数 / ページビュー | ページのリロードまたは更新につながったページビューの割合。 | `[Reloads] / [Page Views]` |
| 売上高 / 購入 | サイト上で完了した各トランザクションまたは注文によってもたらされた平均売上高。 | `[Revenue] / [Orders]` |
| 売上高 / 訪問回数 | サイトへの 1 回の訪問によってもたらされた平均売上高。 | `[Revenue] / [Visits]` |
| 売上高 / 訪問者 | サイトへの各訪問者個人によってもたらされた平均売上高。 | `[Revenue] / [Unique Visitors]` |
| 状態ビュー | アプリの様々な状態または画面へのビュー数 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| 滞在時間 / ユーザー（状態） | 平均訪問者がサイトで特定の状態で滞在する時間の長さ。 | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| ユニーク訪問者 / 7 日後に再訪問するユニーク訪問者 | 7 日以上の期間の後に再訪問するユニーク訪問者の割合。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| ユーザー（モバイル） | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 訪問回数 / 訪問者 | ユニーク訪問者がサイトに訪問した平均回数。 | `[Visits] / [Unique Visitors]` |
| 加重バウンス率 | 関数 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
