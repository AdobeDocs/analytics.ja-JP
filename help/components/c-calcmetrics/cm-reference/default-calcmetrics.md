---
description: Adobeは、使用できる様々な計算指標を提供します。 このページでは、これらの指標とその意図された用途を示します。
title: デフォルトの計算指標
feature: calculated metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
source-git-commit: 43bb7102e2caff93c3beea6e8c23500347679327
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 5%

---

# デフォルトの計算指標

Adobe Analyticsには、最も一般的な使用例に対応するための様々な計算指標が用意されています。 これらの計算指標は、Analysis Workspaceではデフォルトで使用できます。

次に、Adobeが提供する各計算指標と、その計算に使用する基になる関数の一覧を示します。

>[!NOTE]
>
>このページで説明するデフォルトの計算指標に加えて、レポートスイートに計算指標を追加することもできます。
>
>次のことができます。
> * ストリーミングメディア用のデフォルトの計算指標を追加します。詳しくは、 [計算指標](/https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 既存の指標からカスタム計算指標を作成する ( [計算指標および高度な計算（派生）指標](/help/components/c-calcmetrics/cm-overview.md).



| 計算指標名 | 関数 | 数式 |
|---------|----------|---------|
| バウンス率 | そのページの訪問数に対する、ヒットが 1 回だけ含まれた訪問の割合。 これは、バウンス率が最も高いディメンション項目を把握したり、サイトのバウンス率の合計を時間の経過と共に確認したりするのに役立ちます。 | `[Bounces] / [Entries]` |
| 売上高/訪問者 | サイトの個々の訪問者が生み出した平均売上高。 | `[Revenue] / [Unique Visitors]` |
| 注文件数/訪問者数 | サイトの個々の訪問者が発生した注文またはトランザクションの平均数 | `[Orders] / [Unique Visitors]` |
| 売上高/訪問回数 | サイトへの 1 回の訪問で生み出された平均売上高。 | `[Revenue] / [Visits]` |
| 売上高/注文 | サイト上のトランザクションまたは注文の完了ごとに発生した売上高の平均金額。 | `[Revenue] / [Orders]` |
| 注文件数/訪問回数 | トランザクションが完了したサイトへの訪問の割合。 | `[Orders] / [Visits]` |
| ページビュー数/訪問回数 | サイトへの 1 回の訪問中にユーザーが閲覧した平均ページ数。 | `[Page Views] / [Visits]` |
| 訪問回数/訪問者 | 個別訪問者がサイトを訪問した平均回数。 | `[Visits] / [Unique Visitors]` |
| リロード回数/ページビュー数 | ページの再読み込みまたは更新につながったページビューの割合。 | `[Reloads] / [Page Views]` |
| 重み付けられた直帰率 | 関数 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 注文支援 | チャネルまたはソースが、購入に向けた顧客のジャーニーに貢献したが、最終購入につながらなかった回数。 | `[Orders (Visit Participation)] - [Orders]` |
| 出口率 | 特定のページの閲覧後にサイトを離れた訪問者の割合。 | `[Exits] / [Visits]` |
| 入口率 | サイトの合計セッション数に対する、特定のページでサイトに入った訪問者の割合。 | `[Entries] / [Visits]` |
| サイトでの平均時間 | 訪問者がサイトを離れるか離れるまでの平均滞在時間。 | `[Average Time Spent on Site (Seconds)]` |
| 滞在時間/ユーザー（状態） | 平均訪問者がサイトで特定の状態に滞在した時間の長さ。 | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| ユーザー（モバイル） | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| アプリのユーザー | モバイルアプリのユーザーの合計数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 状態ビュー | アプリの様々な状態または画面へのビュー数 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| アクション | アプリで実行されたアクションの合計数 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| ダウンロード計測用リンククリック数 | サイトへのトラフィックを促進するために設計されたリンクをクリックした回数。 | `[Campaign Click-throughs]` |
| ページベロシティ | コンテンツの一部が生成する追加のページビューの数。 これは、どのコンテンツが追加のエンゲージメントを促すかを判断するのに役立ちます。 | `[Page Views] / [Visits]` |
| コンバージョン率 | 購入など、目的のアクションを実行した訪問者の割合。 | `[Orders] / [Visits]` |
| 平均セッション時間（モバイル） | 訪問者が 1 回のセッションでサイトに滞在した平均時間。 | 空白 |
| Experience CloudID の適用範囲 | Experience CloudID を持つ訪問者の割合。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| コンテンツベロシティ | サイト上で新しいコンテンツが作成および公開される速度と、そのコンテンツがユーザーエンゲージメントを生み出す速度。 | `[Page Views] / [Visits]` |
| ITP 2.1 個別訪問者/個別訪問者 | ITP 2.1 Cookie の制限の影響を受けるブラウザーを使用している個別訪問者の割合。 つまり、CNAME 実装を使用していないお客様です。 （これは、クライアント側 JavaScript を使用して Cookie を設定するお客様に当てはまります）。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 個別訪問者数/7 日後に再訪する個別訪問者数 | 7 日以上の期間を経て再訪するユニーク訪問者の割合。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| ページビュー / ユニーク訪問者 | サイトの個別訪問者ごとに閲覧された平均ページ数。 | `[Page Views] / [Unique Visitors]` |
| 訪問回数/訪問者数 | 個別訪問者がサイトを訪問した平均回数。 | `[Visits] / [Unique Visitors]` |
| 推定ユニーク訪問者 (ITP 2.1) | ITP 訪問者（Safari ブラウザーを使用するユーザー）の場合、個別訪問者数を 2 以下で割ります。 この計算指標は、（CNAME 実装を使用せずに）クライアント側の JavaScript を使用して cookie を設定していることを前提としています。 クライアント側 JavaScript を使用して Cookie を設定する実装は、ITP 2.1 以降に影響を受けました。詳しくは、 [Intelligent tracking prevention](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 」を参照してください。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| ページビュー / 推定ユニーク訪問者 (ITP 2.1) | 推定個別訪問者 (ITP 2.1) に対して表示された平均ページ数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |

{style="table-layout:auto"}
