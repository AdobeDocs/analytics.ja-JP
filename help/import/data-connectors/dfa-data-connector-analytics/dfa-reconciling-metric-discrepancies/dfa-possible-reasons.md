---
description: Adobe Analytics と DFA のレポートでデータの不一致が発生する理由をいくつか示します。
keywords: DFA
seo-description: Adobe Analytics と DFA のレポートでデータの不一致が発生する理由をいくつか示します。
seo-title: 不一致について考えられる理由
solution: Analytics
title: 不一致について考えられる理由
topic: Data Connectors
uuid: fd414cc6- d568-491e-9b1c-5d493dcfbe45
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 不一致について考えられる理由{#possible-reasons-for-discrepancies}

Adobe Analytics と DFA のレポートでデータの不一致が発生する理由をいくつか示します。

## Safari ブラウザーおよびサードパーティ cookie をブロックする他のブラウザーのユーザー {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

サードパーティ cookie の承認は、通常、Adobe Analytics と DFA の不一致の最大の原因です。Safari および一部の他のブラウザーは、デフォルトでサードパーティ cookie をブロックします。これは、Safari は、デフォルトでほとんどの Analytics 実装で使用されるファーストパーティ cookie を承認し、DFA で使用されるサードパーティ cookie を拒否することを意味します。

Analytics15ベータ版のお客様のデータサンプルは、通常、ファーストパーティcookieを拒否していますが、5~12%のユーザーはサードパーティcookieを拒否しています（これらの拒否の多くは、デフォルトのブラウザー設定による可能性が高くなります）。

この不一致は、Analytics と DFA によって収集されたデータで大きな違いになる可能性があります。

## DFA でレポートされたインプレッション数が Adobe Analytics でレポートされたインプレッション数よりも多いのはなぜですか。 {#section-db0ad070a65a4985bcc589b2d0d30b90}

* DFA は、夜間のバッチで Adobe データコレクションサーバーにデータを送信するので、Analytics のインプレッションデータは、DFA レポートに最大 2 日間遅れる可能性があります。
* アドビでは、SAINT 分類を使用して、インポートされた DFA トラッキングコードを集計の様々なレベル（キャンペーン名、プレースメント名、広告名など）に分類します。分類レポートを実行する際に不一致が表示されたら、シンプルなテストを実行して、分類がインポートされた指標にまだ対応していないかどうかを確認します。

   * 分類レポートで、「なし」という行項目を探します。
   * 生の DFA ID レポート（キャンペーン ID など）を使用して、この行項目を同じ変数で分類します。
   * このレポートでは、DFA:XXXXX:XXXXX ... という形式の未分類の DFA トラッキングコードに注意します。
   * これらのトラッキングコードの多くが存在する場合、夜間の SAINT 分類処理を調査します。

## DFA クリック数が Adobe Analytics クリックスルーより多いのはなぜですか。 {#section-2fce4608ed044bdc9cf812cb719d5d35}

* DFA は、訪問者が顧客の Web サイトに到着する前のクリックを記録します。Analytics は、ランディングページで Adobe JavaScript ビーコンが読み込まれ、実行された後のクリックスルーを記録します。通常、不一致は、DFA がクリックをトラッキングしてから訪問者がランディングページに到着していないか、*`s.maxDelay`* タイマーがヒットされていることが原因です。
* Floodlight 設定のすべてのプレースメントおよびクリエイティブにランディングページ URL の clickThroughParam が含まれていることを確認します（例：「?CID=1」）。このパラメーターの設定に失敗すると、Adobe Analytics JavaScript が訪問の最初のヒットの後に発生したクリックスルーを見逃す原因となります。
* すべてのプレースメントおよびクリエイティブに、JavaScript でタグ付けされ、DFA Integrate モジュールを持つランディングページがあり、そのランディングページの Floodlight 設定 ID が提供された広告の Floodlight 設定 ID と一致することを確認します。多くの場合、不一致は、広告のランディングページがサードパーティサイト、または提供された広告に設定されていることが原因です。
* リッチメディア広告または Flash（swf）広告を使用する場合、DFA クリックトラッカーがヒットするたびに、訪問者のブラウザーも、クエリ文字列に含まれる `clickThroughParam` と共にランディングページにリダイレクトされていることを確認します。ブラウザーのリダイレクトに失敗すると、クリックスルーが記録されません。
* タイムアウトは、DFA データは利用できたが JavaScript が時間どおりに応答を受け取らなかったインスタンスを表します。訪問者がランディングページに到着すると、Adobe JavaScript は、DFA の fls.doubleclick.net サービスからの訪問者の情報をリクエストします。"*`s.maxDelay`* パラメーターは、JavaScript が Floodlight Service（FLS）データを待機する時間を決定します。If *`s.maxDelay`* is too high, visitors can leave the site before Adobe collects the hit data; meaning that no click data is recorded. If *`s.maxDelay`* is set too low, the visitor's Internet connection cannot retrieve the FLS data in time; meaning that the hit is sent to Adobe without DFA click information. See [Tuning s.maxDelay](../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d) for a further discussion on this subject.

* ボットトラフィックが DFA クリック数を水増しする可能性があります。ボットは、広告をクリックする機能を持つ場合がありますが、Analytics ビーコンを実行したり、同期スクリプトタグを実行して Floodlight サーバーリクエストデータを読み込んだりする複雑さは持たない可能性があります。これらのボットがクリック数の数から削除されない場合、これが不一致を生み出します。
* ページを離脱した訪問者&#x200B;*`s.maxDelay`* が切れる前、および DFA データが返される前にページを離れた訪問者は、失われます。DFA または訪問者データは、収集されません。
* Analytics は、キャンペーンごと、訪問ごとに 1 回だけカウントされるように、重複したクリックスルー数を識別および削除しようとします。DFA は、「戻る」をクリックして広告のリダイレクトを複数回通過した訪問者を追加の ACM クリック数としてカウントするのに対して、Analytics はこれらを複数のクリックスルーとしてカウントしません。
* DFA Floodlight タグは、JavaScript が有効であることに依存しませんが、Analytics は依存します。このため、Analytics が記録しないときに DFA がヒットを記録する可能性があります。これが問題になるかどうかを特定するには、訪問者プロファイルメニューの Analytics JavaScript レポートを使用します。

## DFA のインプレッション後のアクティビティが Adobe Analytics ビュースルーより多いのはなぜですか。 {#section-5daa91039c404df48b6a3447c20406f7}

* Analytics は、キャンペーンごと、訪問ごとに 1 回だけカウントされるように、重複したクリックスルー数を識別および削除しようとします。DFA は、「戻る」をクリックして広告のリダイレクトを複数回通過した訪問者を追加の ACM クリック数としてカウントするのに対して、Analytics はこれらを複数のクリックスルーとしてカウントしません。
* DFA Floodlight タグは、JavaScript が無効であることに依存しませんが、Analytics は依存します。このため、Analytics が記録しないときに DFA がヒットを記録する可能性があります。
* DFA は、Floodlight タグを使用する際にインプレッション後のアクティビティをカウントします。これはクライアント Web サイトに配置できます。Analytics は、JavaScript ビーコン（イメージリクエスト）が実行された後でビュースルーをカウントします。Web ページにコードを配置すると、中止したページ読み込みをインプレッション後のアクティビティとしてカウントするかビュースルーとしてカウントするかを決定できます。

## 不一致が許容範囲をはるかに超えており、前述の考えられる理由が適用されない場合、どうすればいいですか。 {#section-ca50eb75dd5d4d0396f4668b44d7547c}

統合コンサルタントまたは Adobe ClientCare に問い合わせて、不一致を文書に記録して Data Connectors エンジニアリングチームに報告してください。リクエストを迅速に処理するために、2 ～ 3 日分のデータで問題の指標を（キャンペーンコードレベルで）比較してください。リクエストでは、不一致を調整するために既におこなったすべてのアクションを特定してください。
