---
description: Analysis Workspace でのデフォルトレポートの使用方法の概要。
title: レポートを使用
feature: Analysis Workspace
role: User, Admin
exl-id: 0d43fa5e-9167-4af7-891d-e49b0249bca2
source-git-commit: dcc517c2cd24a1aeeb2594094d09b9187ea7d144
workflow-type: ht
source-wordcount: '1516'
ht-degree: 100%

---

# 事前定義済みレポートの使用

Analysis Workspace の事前定義済みレポートを使用すると、最も一般的なレポートシナリオに対する簡易的なインサイトを得ることができます。事前定義済みレポートを使用して回答できる質問の例を以下に示します。

* サイトの訪問者数
* そのうちのユニーク訪問者数（1 回のみカウント）
* サイトへの来訪経路（リンクをたどって来訪したか、直接来訪したかなど）
* サイトのコンテンツを検索するために使用したキーワード
* 特定のページまたは全サイトでの滞在時間
* 訪問者がクリックしたリンク、およびサイトを離れた日時
* 売上高またはコンバージョンイベントを最も効果的に生み出しているマーケティングチャネル
* ビデオの視聴に費やした時間
* サイトの訪問に使用したブラウザーとデバイス

次に、Analysis Workspace の「[!UICONTROL レポート]」タブから事前定義済みレポートにアクセスして使用する方法について説明します。

## レポートへのアクセスと実行

1. Analysis Workspace で、「[!UICONTROL **ワークスペース**]」タブを選択します。

1. 「[!UICONTROL **レポート**]」を選択します。

   ![「レポート」タブ](assets/view-prebuilt-reports.png)

1. 検索フィールドに、検索するレポートの名前を入力し、レポートのリストから選択します。レポートリストを prop、eVar、イベント番号でも検索できるようになりました。<!-- still true? -->

   または

   表示するレポートのカテゴリを選択し、レポートのリストからレポートを選択します。

   >[!TIP]
   >
   >   矢印キーを使用してメニューを移動するには、スラッシュ（/）キーを押してから、下矢印キーを押します。Enter キーを押して、選択したレポートを読み込みます。

使用可能なレポートのリストについては、[使用可能なレポート](#available-reports)の節を参照してください。

## レポートの保存 {#use-reports}

変更した後にレポートから移動すると、変更を保存するか破棄するように求められます。レポートに対する変更を保存すると、レポートが新しいプロジェクトとして保存されます。

1. 「[!UICONTROL **レポート**]」タブに移動します。
1. 表示するレポートを選択します。例えば、「[!UICONTROL **一番人気**]」で、[!UICONTROL **ページ**]&#x200B;レポートを選択します。

   ![ページレポート](assets/pages-report.png)

1. Analysis Workspace に表示されるページレポートには、2 つの[ビジュアライゼーション](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)（[棒グラフ](/help/analyze/analysis-workspace/visualizations/bar.md)と[概要番号](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)）および[フリーフォームテーブル](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)が表示されます。使用される指標は発生件数です。
1. 次のいずれかの操作を行います。

   * レポートを表示する。
   * 上部のセグメントドロップゾーンに、1 つ以上のセグメントをドラッグする。例えば、[!UICONTROL **モバイル顧客**]&#x200B;セグメントをドラッグし、結果を表示します。
   * 右上のカレンダーに移動して、日付範囲を変更する。
   * ディメンション分類を追加し、他の指標をドラッグして、通常はニーズに合わせてレポートをカスタマイズする。

1. （オプション）[!UICONTROL **プロジェクト**]／[!UICONTROL **保存**]&#x200B;を選択して、レポートをプロジェクトとして保存します。

   レポートが新しいプロジェクトとして保存されます。既存のレポートは変更されません。レポートをプロジェクトとして保存する方法について詳しくは、[プロジェクトの保存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md)を参照してください。

## 使用可能なレポート

次の表に、使用可能な事前定義済みレポートの完全なリストを示します。

一番人気の事前定義済みレポートの一部には、フロー、フォールアウト、マーケティングチャネル、リアルタイムレポートが含まれます。

| メニュー項目 | このメニュー項目のレポート |
| --- | --- |
| **[!UICONTROL 最頻使用]** | <ul><li>トレーニングチュートリアル（既存のワークスペーステンプレート）</li><li>ページ（トップページは何か）</li><li>ページビュー数（生成しているページビュー数はいくつか）</li><li>訪問回数（訪問回数はいくつか）</li><li>訪問者（訪問者は何人か）</li><li>主要指標（最も重要な指標のパフォーマンスはどの程度か）</li><li>サイトセクション（最もページビュー数の多いサイトセクションはどれか）</li><li>リアルタイム（サイトのトレンド分析とは何か、およびこれ行う理由）</li><li>次のページ（訪問者が次に閲覧するページは何か）</li><li>前のページ（訪問者が最後に閲覧したページは何か）</li><li>キャンペーン（主要指標を促しているキャンペーンは何か）</li><li>製品（主要指標を推進しているのはどの製品か）</li><li>ラストタッチチャネル（パフォーマンスが最も高いラストタッチチャネルはどれか）</li><li>ラストタッチチャネルの詳細（他のチャネルよりパフォーマンスが優れているラストタッチチャネルはどれか）</li><li>売上高（売上高のパフォーマンスはどの程度か）</li><li>注文（注文のパフォーマンスはどの程度か）</li><li>点数（販売数はいくつか）</li></ul> |
| **[!UICONTROL エンゲージメント]** | <ul><li>主要指標（最も重要な指標のパフォーマンスはどの程度か）</li><li>ページビュー数（生成しているページビュー数はいくつか）</li><li>ページ（トップページは何か）</li><li>訪問回数（訪問回数はいくつか）</li><li>訪問者（訪問者は何人か）</li><li>訪問別滞在時間（ユーザーの滞在時間は1 回の訪問あたりどのくらいか）</li><li>イベント前の時間（成功イベントの前にユーザーが滞在した時間はどれくらいか）</li><li>サイトセクション（最もページビュー数の多いサイトセクションはどれか）</li><li>Web コンテンツの消費（最も消費され、ユーザーを引き付けているのはどのコンテンツか）</li><li>メディアコンテンツ消費（最も消費され、ユーザーを引き付けているのはどのコンテンツか）</li><li>次と前のページフロー（訪問者がたどった次／前のパスは何か）</li><li>フォールアウト（デジタルプロパティのどこでフォールアウトが発生するか）</li><li>クロスデバイス分析（Analysis Workspace でのクロスデバイス分析の使用）</li><li>Web リテンション（常連ユーザーは誰で、どのような行動を取っているか）</li><li>メディアオーディオ消費（オーディオ消費のトレンドとトップ指標は何か）</li><li>メディアの最新性、頻度、ロイヤルティ（常連読者は誰か）</li><li>ページ分析／リロード回数（最もリロード回数の多いページはどれか）</li><li>ページ分析／ページでの滞在時間（ユーザーがページで滞在した時間はどのくらいか）</li><li>入口と出口／入口ページ（上位の入口ページはどれか）</li><li>入口と出口／オリジナルの入口ページ（訪問者が最初にアクセスしたページはどれか）</li><li>入口と出口／単一ページ訪問数（単一ページ訪問数が最も多いページはどれか）</li><li>入口と出口／出口ページ（上位の出口ページはどれか）</li></ul> |
| **[!UICONTROL コンバージョン]** | <ul><li>製品／製品（主要指標を促しているのはどの製品か）</li><li>製品／製品のパフォーマンス（最もパフォーマンスが高い製品はどれか）</li><li>製品／カテゴリー（最もパフォーマンスの高い製品カテゴリーは何か）</li><li>買い物かご／買い物かご（買い物かごに製品を追加したユーザーは何人か）</li><li>買い物かご／買い物かご表示（訪問者が買い物かごを何回表示したか）</li><li>買い物かご／買い物かごへの追加（ユーザーが買い物かごに製品を追加する頻度はどのくらいか）</li><li>買い物かご／買い物かごからの削除（ユーザーが買い物かごから商品を削除する頻度はどのくらいか）</li><li>購入／売上高（売上高のパフォーマンスはどの程度か）</li><li>購入／注文（注文のパフォーマンスはどの程度か）　</li><li>購入／点数（販売数はいくつか）</li><li>[Magento：マーケティングとコマース](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#commerce)</li></ul> |
| **[!UICONTROL オーディエンス]** | <ul><li>人物指標（ブランドとやり取りしているユーザーは何人か）</li><li>訪問者プロファイル／場所の概要（ユーザーの間で最も多くの利用を促進しているのは場所はどこか）</li><li>訪問者プロファイル／地理特性／地域 - 郡、地域 - 米国の州、地域 - 地域、地域 - 市区町村、地域 - 米国 DMA（ユーザーがアクセスしている地域はどこか）</li><li>訪問者プロファイル／言語（ユーザーが好む言語はどれか）</li><li>訪問者プロファイル／タイムゾーン（ユーザーはどのタイムゾーンから訪問しているか）</li><li>訪問者プロファイル／ドメイン（訪問者がサイトへのアクセスに使用している ISP はどれか）</li><li>訪問者プロファイル／トップレベルドメイン（サイトへのトラフィックを促進しているのはどのドメインか）</li><li>訪問者プロファイル／技術／技術の概要（訪問者がサイトへのアクセスに使用しているのはどのテクノロジーか）</li><li>訪問者プロファイル／技術／ブラウザー、ブラウザータイプ、ブラウザーの幅、ブラウザーの高さ（ユーザーがサイトへのアクセスに使用しているのはどの会社のブラウザー、ブラウザー バージョン、幅と高さか）</li><li>訪問者プロファイル／テクノロジー／オペレーティングシステム、オペレーティングシステムのタイプ（訪問者が使用している OS とバージョンはどれか）。</li><li>訪問者プロファイル／テクノロジー／携帯電話会社（訪問者がサイトへのアクセスに使用する携帯電話会社はどれか）</li><li>訪問者保持率／再来訪頻度（ユーザーの前回の訪問から現在の訪問までの経過時間はどのくらいか）</li><li>訪問者保持率／再来訪（訪問者のうちの、再訪問者の数）</li><li>訪問者保持率／訪問回数（主要指標の大部分を占める訪問回数のバケットはどれか）</li><li>訪問者保持率／販売サイクル／顧客の忠誠度（ユーザーはどのロイヤルティセグメントに属しているか）</li><li>訪問者保持率／販売サイクル／初回購入までの日数（ユーザーの初回訪問から初回購入までの日数はどのくらいか）</li><li>訪問者保持率／販売サイクル／前回購入からの日数（ユーザーの現在の訪問から前回購入までの日数はどのくらいか）をクリックします。</li><li>訪問者保持率／モバイル／デバイスとデバイスのタイプ（訪問が使用しているデバイスとデバイスのタイプはどれか）</li><li>訪問者保持率／モバイル／製造元（訪問者が使用しているモバイルデバイスのメーカーはどれか）</li><li>訪問者保持率／モバイル／画面サイズ、画面の高さ、画面の幅（訪問者のモバイル画面のサイズ/高さ/幅はどれですか？）</li><li>訪問者保持率／モバイル／[モバイルアプリの使用状況](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#mobile)</li><li>訪問者保持率／モバイル／[モバイルアプリジャーニー](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#mobile)</li><li>訪問者保持率／モバイル／[モバイルアプリ指標](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#mobile)</li><li>訪問者保持率／モバイル／[モバイルアプリメッセージ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#mobile)</li><li>訪問者保持率／モバイル／[モバイルアプリのパフォーマンス](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#mobile)</li><li>訪問者保持率／モバイル／[モバイルアプリ保持率](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#mobile)</li></ul> |
| **[!UICONTROL 獲得]** | <ul><li>マーケティングチャネル／ファーストタッチチャネル、ファーストタッチチャネルの詳細（ファーストタッチチャネルの種類と、パフォーマンスが最も高い特定のファーストタッチチャネルの種類はどれか）</li><li>マーケティングチャネル／最後のチャネル、最後のチャネルの詳細（ラストタッチチャネル、および最もパフォーマンスの高い特定のラストタッチチャネルはどれか）</li><li>Campaign／Campaign（主要指標を推進しているキャンペーンはどれか）</li><li>Campaign／キャンペーンのパフォーマンス（最も高い売上を促進しているのはどのキャンペーンか）</li><li>キャンペーン／トラッキングコード（パフォーマンスが最も高いキャンペーントラッキングコードはどれか）</li><li>[Web 獲得](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#web)</li><li>[モバイル獲得](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#mobile)</li><li>[Advertising Analytics: 有料検索](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=ja#advertising)</li><li>検索キーワード - すべて、有料、自然（主要指標を最も促進している検索キーワードおよび有料／自然検索キーワードはどれか）</li><li>検索エンジン - すべて、有料、自然（主要指標を最も促進している検索エンジンおよび有料／自然検索エンジンはどれか）</li><li>すべての検索ページのランク（ユーザーはどの検索ページから訪問しているか）</li><li>参照ドメイン（サイトへのトラフィックを促進しているのはどのドメインか）</li><li>オリジナルの参照ドメイン（サイトを訪問する前に最初に訪問したドメインは何か）</li><li>リファラー（クリックスルーしてサイトにアクセスする前に、ユーザーが閲覧していた URL はどれか）</li><li>リファラータイプ（参照 URL が属するカテゴリはどれか）</li></ul> |
