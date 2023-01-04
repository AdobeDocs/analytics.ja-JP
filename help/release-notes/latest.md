---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: be32a2278ac3686d814b25d8a4a857b9f0ddc771
workflow-type: tm+mt
source-wordcount: '1457'
ht-degree: 97%

---

# 最新のAdobe Analyticsリリースノート

**最終更新日**:2023 年 1 月 5 日

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## Adobe Analytics の新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **[!UICONTROL 主要指標の概要]**&#x200B;のビジュアライゼーション | [!UICONTROL 主要指標の概要]のビジュアライゼーションを使用すると、1 つの期間内で重要な指標のトレンドを確認できます。また、2 つの期間で指標のパフォーマンスを比較することもできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=ja) | 2022年10月5日（PT） | 2023年10月19日（PT） |
| **複数値の変数で大文字と小文字が区別されない** | 大文字と小文字を区別しない複数値変数の場合、データフィードの `mvvar1 - mvvar3` と `post_mvvar1 - post_mvvar3` に格納される値は、自動的に小文字に変換されなくなります。代わりに、データフィード（および Analytics ソースコネクタを通じて Adobe Experience Platform と CJA に渡されるデータ）は、ページから渡された元のケースを反映します。 | 該当なし | 2022年10月24日（PT） |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* 最新の macOS バージョンの名前が誤って「Macintosh」になっていた問題を修正しました。この修正により、OS ディメンションは、macOS 11 から「macOS」バージョンの番号で表記されるようになります。(AN-301834)
* Report Builder で「固定日付」の日付範囲で発生していた問題を修正しました。(AN-303684)
* データフィード UI が読み込まれない問題を修正しました。（AN-303803、AN-303784）

### その他の修正点

-295574、AN-296354、AN-297143、AN-299501、AN-301755、AN-302054、AN-302304、AN-302631、AN-302811、AN-303090、AN-303372、AN-、AN-303428、AN-303429、AN-303432、AN-303434、AN-303437、AN-303438、AN-303519、AN-303610、AN-303656、AN-303659、AN-303663、AN-303664、AN-303818、AN-303823、AN-303837、AN-304036、AN-304195、AN-304321、AN-304325、AN-304339、AN-304356、AN-304435、AN-304457、AN-304509、AN-304519、AN-304534

## Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **IP からジオロケーションへのマッピングの改善** | 2023 年 1 月 5 日 | IP ルックアップに関する当社のベンダー（Digital Element）は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）にアップグレードしつつあります。当初は 2022 年 10 月に予定されていたので、Adobe Analyticsでは、この新しいデータセットを **2023 年 1 月 12 日**. 新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p>すべての Adobe Analytics ツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream、データフィードなど）は、新しく改善されたマッピングを自動的に利用します。データフィードのデータの形式は変更されません。Analytics ソースコネクタを通じて提供される CJA データでも、新しいマッピングを自動的に利用します。 |
| **新しい NetAcuity 通信事業者データベースの更新** | 2023 年 1 月 5 日 | この更新は、もともと 2022 年 10 月 5 日に予定されていたもので、今後は **2023 年 1 月 12 日**. Adobe Analytics Data Warehouse および Analytics データフィードの `carrier` フィールドに保存されている通信事業者関連の情報が変更されます。従来、その列のデータ形式は `<domain>:<ISP>` でした。Adobe Analytics レポートツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など）でレポートを作成するために、これらの `<domain>:<ISP>` 値を通信事業者名にマッピングするための内部ルックアップテーブルがメンテナンスされました。ルックアップファイル（`carrier.tsv`）にもデータフィードが用意されているので、同じマッピングを使用できます。<p>この更新により、NetAcuity のより正確な通信事業者データベースを使用して通信事業者のマッピングが強化されます。データフィードの通信事業者列のデータ形式は、今後変更される予定です。`<domain>:<ISP>` の代わりに、通信事業者名が含まれます。アドビでは、従来のレポートとの継続性をできる限り維持するために、引き続きルックアップテーブルを使用します。アドビがルックアップを適用するレポートツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など）は、より正確なマッピングのメリットを享受できます。新しいデータベースを採用すると、一部のマッピング（特に国際ドメインおよび ISP の場合）は、他のマッピングよりも変更が多くなります。データフィード通信事業者ルックアップファイル（`carrier.tsv`）では、古いマッピングが維持され、新しいマッピングが追加されます。<p>Analytics ソースコネクタでは、現在、通信事業者フィールドのマッピングは行っていません。そのため、通信事業者レポートは、現在、Experience Platform、CJA などでは使用できません。したがって、新しい通信事業者データベースを使用しても、Analytics ソースコネクタから提供されるデータに基づいている限り Experience Platform での影響はありません。 |
| **トラフィックスパイク通知のガイドラインを更新しました** | 2022年11月18日（PT） | 以前のガイドラインは、ヒット数に厳密に基づいていました。[新しいガイドライン](https://experienceleague.adobe.com/docs/analytics/admin/traffic-management/traffic-lead-time.html?lang=ja)は、レポートスイートのサイズと増加率の組み合わせに基づいています。 |
| **Google クライアントヒントによるデバイス検索の更新** | 2022年10月14日（PT） | デバイス検索でのクライアントヒントの使用は、当初 2022年10月26日に予定されていましたが、 **2023年1月**&#x200B;に延期されました。 <p> <p>2022年10月から、Web SDK または AppMeasurement JavaScript ライブラリを使用してクライアントヒントを収集できるようになります。ただし、クライアントヒントは、2023年1月まではデバイス検索に組み込まれません。 2023年1月にアドビは、Google Chrome および Microsoft Edge など Chromium ブラウザーからのヒットに関する特定のデバイス情報を取得する際に、User-Agent に加えてクライアントヒントも使用するようになります。これは、クライアントヒントを介して渡されるデータの代わりに User-Agent 文字列から提供される情報を徐々に減らす Google の計画に対応するものです。 <p> <p>この変更の一環として、アドビでは、User-Agent に関連するすべてのデバイス検索に対して Device Atlas を使用します。[詳細情報](/help/technotes/client-hints.md) |
| **デフォルトのランディングページ** | 2022年9月29日（PT） | 今年初めに導入された[新しいランディング ページ](/help/analyze/landing.md)は、**2023年1月**&#x200B;にすべてのユーザーにとってデフォルトエクスペリエンスになります。現在のページは廃止される予定で、すべてのユーザーは新しいエクスペリエンスを利用する必要があります。 |
| **[!UICONTROL 異常値検出]の自動実行条件** | 2022年9月29日（PT） | 現在、[!UICONTROL 異常値検出]は、時系列フリーフォームテーブルのすべての列に対して自動実行されます。 分析のデータを確保したりプロジェクトの読み込みを高速化したりするために、アドビでは異常値検出の自動実行方法を変更します。 **2022年10月26（PT）**&#x200B;以降[!UICONTROL 異常値検出]は、テーブルの最初の指標列でのみ自動実行されます。 必要に応じて、他の列で異常値検出を実行するように列設定を設定できます。 |
| **Reports &amp; Analytics での予定レポートの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、アドビは、以前に発表された Reports &amp; Analytics の提供終了に備えて、予定レポートに固有のいくつかの機能が廃止されることを発表しました。これらの機能には、新規レポートのスケジュール設定機能と、新規データ抽出機能が含まれていました。<p>延長を求めるお客様の要求に応え、Reports &amp; Analytics からの移行を容易にするために、アドビでは、これらの機能へのアクセスを **2023年1月31日（PT）**&#x200B;まで延長することに決定しました。レポートとデータ抽出の両方の有効期限は、引き続き 9 か月に制限されることに注意してください。レポートおよびデータ抽出の配信は、スケジュールが再アクティブ化されない限り、この期間終了後に一時停止されます。<p>繰り返しになりますが、これらの機能は 2023年1月31日（PT）に廃止されます。この日付までに、予定レポートを Adobe Analytics で使用できる他のメカニズムのいずれかに移行する必要があります。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Report Builder での予定タスクの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、アドビは、パフォーマンスと配信の最適化の一環として、Report Builder のスケジュールされたタスクに変更を加えました。これらの変更には、スケジュールされた配信の「x 回後に終了」機能の削除が含まれています。代替案の検討や導入にさらなる時間の確保が必要であるとのお客様の要望に応えて、アドビでは、 **2023年1月31日（PT）**&#x200B;まで限定的にこのオプションを復元することが決定されました。<p>1 時間ごとの Report Builder タスクのスケジュールを継続し、最大 99 回発生した後にタスクを終了させることができます。ロールバックは 1 時間ごとのタスクにのみ適用されることに注意してください。「x 回後に終了する」は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できません。このオプションは、2023年1月31日（PT）に廃止されることに注意してください。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## 提供終了に関する注意事項

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2022年9月29日（PT） | Reports &amp; Analytics の提供終了（EOL）の一環として、発行リストは **2023年12月**&#x200B;に提供終了になる予定です。新しいパブリッシュリストを作成するか既存のパブリッシュリストにアクセスして、Analysis Workspace プロジェクトの送信やスケジュールを行うことはできなくなります。 |
| **Data Workbench のサポート終了** | 2022年9月14日（PT） | **2023年12月31日（PT）**&#x200B;をもって、アドビは Data Workbench のサポートを終了する予定です。詳しくは、[Data Workbench の提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日（PT）**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

AppMeasurement リリース（バージョン 2.23.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
