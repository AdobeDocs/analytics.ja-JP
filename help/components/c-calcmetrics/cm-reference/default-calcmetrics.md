---
description: Adobeでは、使用可能な様々な計算指標を提供します。 このページでは、これらの指標とその使用目的を一覧表示します。
title: デフォルトの計算指標
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: 1382d8901b980db016521a3051de23d8d5b71f57
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 41%

---

# デフォルトの計算指標

Adobe Analyticsには、最も一般的なユースケースに対応するための様々な計算指標が用意されています。 これらの計算指標は、デフォルトでAnalysis Workspaceで使用できます。

Adobeが提供する各計算指標、意図した関数、およびその計算に使用される基になる数式のリストを以下に示します。

>[!NOTE]
>
>このページで説明されているデフォルトの計算指標に加えて、レポートスイートに追加の計算指標を追加することもできます。
>
>次のことができます。
> * の説明に従って、ストリーミング メディア コレクション アドオンに既定の計算指標を追加します [計算指標](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * の説明に従って、既存の指標からカスタム計算指標を作成する [計算指標および高度な計算（派生）指標](/help/components/c-calcmetrics/cm-overview.md).


| 計算指標名 | 関数 | 数式 |
| --- | --- | --- |
| 獲得リンククリック数 | サイトへのトラフィックを推進するように設計されたリンクを人物がクリックした回数。 | `[Campaign Click-throughs]` |
| アクション | アプリで実行されたアクションの合計数 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| アプリユーザー | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 平均セッション長（モバイル） | 訪問者が単一セッション中にサイトに滞在した平均時間。 | 空白 |
| サイトでの平均時間 | 訪問者がサイトを離れたり移動したりするまでにサイトに滞在した平均時間。 | `[Average Time Spent on Site (Seconds)]` |
| バウンス率 | そのページの訪問数に対する、ヒットが 1 つのみ含まれる訪問の割合。 この指標は、バウンス率が最も高いディメンション項目を理解したり、サイトのバウンス率の集計合計を経時的に確認したりするのに役立ちます。 | `[Bounces] / [Entries]` |
| ボットページビュー数の割合 | ページビューの合計数に対するボットページビューの割合。 | `[Bot Page Views] / [Page Views]` |
| コンテンツベロシティ | 新しいコンテンツがサイト上で作成および公開される速度と、そのコンテンツがユーザーエンゲージメントを生成する速度。 | `[Page Views] / [Visits]` |
| コンバージョン率 | 購入など、目的のアクションを行った訪問者の割合。 | `[Orders] / [Visits]` |
| 入口率 | サイトの合計セッション数と比較した、特定のページでサイトに入った訪問者の割合。 | `[Entries] / [Visits]` |
| 推定ユニーク訪問者（ITP 2.1） | ITP 訪問者（Safari ブラウザーのユーザー）の場合は、ユニーク訪問者を 2 以下で割ります。 この計算指標は、（CNAME 実装を使用せずに）クライアントサイド JavaScriptを使用して cookie を設定していることを前提としています。 ITP 2.1 以降、クライアントサイド JavaScriptを使用して cookie を設定する実装に影響がありました。参照： [インテリジェントなトラッキングの防止](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) を参照してください。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID の適用範囲 | Experience Cloud ID を持つ訪問者の割合。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 出口率 | 特定のページを表示した後にサイトを離れた訪問者の割合。 | `[Exits] / [Visits]` |
| ITP 2.1 ユニーク訪問者/ ユニーク訪問者 | ITP 2.1 cookie 制限の影響を受けたブラウザーを使用するユニーク訪問者の割合。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 注文支援 | チャネルまたはソースが、購入に至るまでの顧客のジャーニーに貢献したが、最終的な購入には至らなかった回数。 | `[Orders (Visit Participation)] - [Orders]` |
| 注文件数/訪問回数 | 完了したトランザクションにつながったサイトへの訪問の割合。 | `[Orders] / [Visits]` |
| 注文/訪問者 | 各訪問者個人がサイトにもたらした注文またはトランザクションの平均数 | `[Orders] / [Unique Visitors]` |
| ページビュー / 推定ユニーク訪問者 (ITP 2.1) | 推定ユニーク訪問者数 (ITP 2.1) で表示されたページの平均数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| ページビュー / ユニーク訪問者 | サイトへの各ユニーク訪問者に表示されたページの平均数。 | `[Page Views] / [Unique Visitors]` |
| ページビュー / 訪問回数 | ユーザーが 1 回のサイト訪問中に表示するページの平均数。 | `[Page Views] / [Visits]` |
| ページベロシティ | コンテンツが生成する追加のページビューの数。 この指標は、どのコンテンツがエンゲージメントの増加につながるかを判断するのに役立ちます。 | `[Page Views] / [Visits]` |
| リロード/ページビュー数 | ページのリロードまたは更新につながったページビューの割合。 | `[Reloads] / [Page Views]` |
| 売上高/注文 | サイト上で完了した各トランザクションまたは注文によってもたらされた平均売上高。 | `[Revenue] / [Orders]` |
| 売上高/訪問回数 | サイトへの 1 回の訪問によってもたらされた平均売上高。 | `[Revenue] / [Visits]` |
| 売上高/訪問者 | サイトへの各訪問者個人によってもたらされた平均売上高。 | `[Revenue] / [Unique Visitors]` |
| 状態ビュー | アプリの様々な状態または画面へのビュー数 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| 滞在時間/ユーザー（状態） | 平均訪問者がサイトで特定の状態に滞在する時間の長さ | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| ユニーク訪問者/ 7 日後に再訪問したユニーク訪問者 | 7 日以上の期間の後に再訪問するユニーク訪問者の割合。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| ユーザー（モバイル） | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 訪問回数/訪問者 | ユニーク訪問者がサイトに訪問した平均回数。 | `[Visits] / [Unique Visitors]` |
| 重み付けられた直帰率 | 関数 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
