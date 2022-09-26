---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 8ac0c2ccd23aac4916f43c0f046be769e6b13d0b
workflow-type: tm+mt
source-wordcount: '1407'
ht-degree: 55%

---

# 現在の Adobe Analytics リリースノート（2022年9月）

**最終更新日**：2022年9月26日（PT）

Adobe Analyticsのリリースは [連続配信モデル](releases.md) これにより、機能のデプロイメントに向けて、よりスケーラブルで段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 定期的に確認してください。

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能または更新された機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| Workspace での複合グラフのビジュアライゼーション | 複合グラフを使用すると、Workspace 内で指標をより簡単かつ直感的に比較できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts.html?lang=ja) | 2022 年 9 月 14 日から段階的なロールアウトが開始されます |
| AppMeasurement バージョン2.23.0 | AppMeasurement で、Chromium ブラウザー (Google Chrome およびMicrosoft Edge) がデバイス情報の提供に使用する、高エントロピーのユーザーエージェントクライアントヒントのコレクションがサポートされるようになりました。 クライアントヒントは、タグを介して設定するか、「collectHighEntropyUserAgentHints」フラグを使用して設定できます。 高エントロピーのヒントのコレクションは、デフォルトではオフになっています。 [詳細情報](/help/technotes/client-hints.md) | 2022年22月9日（PT） |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* 分類の読み込みと書き出しの問題を修正しました。（AN-299267）

**個人のお客様向けの修正点**：

AN-288519、AN-289300、AN-297387、AN-297465、AN-297520、AN-297641、AN-298134、AN-298351、AN-298429、AN-298483、AN-298520、AN-298582、AN-298816、AN-298832、AN-298855、AN-298864、AN-299407、AN-299545、AN-299644、AN-299715

## Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **新しい NetAcuity 通信事業者データベースの更新** | 2022年26月9日（PT） | この更新は、2022 年 10 月 5 日に当初予定されていたもので、に延期されました。 **2023 年 1 月**. 次に保存されている通信事業者関連の情報： `carrier` Adobe AnalyticsData Warehouseおよび Analytics データフィードのフィールドが変更されます。 従来、その列のデータ形式は `<domain>:<ISP>` でした。Adobeは、これらをマッピングする内部ルックアップテーブルを維持しています `<domain>:<ISP>` の値をAdobe Analyticsのレポートツール (Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など ) でレポート目的で通信事業者名に追加します。 ルックアップファイル（`carrier.tsv`）にもデータフィードが用意されているので、同じマッピングを使用できます。<p>この更新により、NetAcuity のより正確な通信事業者データベースを使用して通信事業者のマッピングが強化されます。データフィードの通信事業者列のデータ形式は、今後変更される予定です。`<domain>:<ISP>` の代わりに、通信事業者名が含まれます。アドビでは、従来のレポートとの継続性をできる限り維持するために、引き続きルックアップテーブルを使用します。アドビがルックアップを適用するレポートツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など）は、より正確なマッピングのメリットを享受できます。一部のマッピング（特に国際ドメインおよび ISP の場合）は、Adobeが新しいデータベースを採用すると、他のマッピングよりも多く変更されます。 データフィード通信事業者ルックアップファイル（`carrier.tsv`）では、古いマッピングが維持され、新しいマッピングが追加されます。<p>Analytics ソースコネクタは、現在、carrier フィールドをマッピングしていないので、carrier レポートは、現在、Experience Platform、CJA などでは使用できません。 したがって、新しい通信事業者データベースの使用は、Analytics ソースコネクタから提供されるデータに基づくExperience Platform内のデータには影響しません。 |
| **IP からジオロケーションへのマッピングの改善** | 2022年26月9日（PT） | IP ルックアップに関する当社のベンダー（Digital Element）は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）にアップグレードしつつあります。当初は 2022 年 10 月に予定されていたので、Adobe Analyticsではこの新しいデータセットを **2023 年 1 月**. 新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p>すべての Adobe Analytics ツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream、データフィードなど）は、新しく改善されたマッピングを自動的に利用します。データフィードのデータの形式は変更されません。Analytics ソースコネクタを通じて提供される CJA データでも、新しいマッピングを自動的に利用します。 |
| **SFTP アップグレード** | 2022年19月9日（PT） | 以前は、Adobeは、Adobeが 2022 年 9 月に Secure File Transfer Protocol(SFTP) サービスをアップグレードして、ファイル転送のセキュリティを強化することを通知していました。 Adobeがこのアップグレードを実行しました： **2022 年 9 月 21 日**. この変更がおこなわれた場合、一部の SFTP クライアント設定はサポートされなくなりました。 これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| **Experience Edge 経由で収集された A4T データを Analytics が処理する方法の変更** | 2022年9月14日（PT） | 2022 年 3 月、Analytics は、A4T データを含む Experience Edge からの一部の呼び出しを処理する方法を変更しました。 ページビュー (`t()`) またはリンクトラッキング (`tl()`) イベントに関する情報です。 このロジックが更新され、 `propositionDisplay` イベントが意図したとおりに変更されていませんでした。 |
| **Web SDK のリスト変数およびリスト prop の自動区切り文字** | 2022年9月14日（PT） | XDM で区切り文字の上書きが指定されていない限り、リスト変数およびリスト prop で、レポートスイート設定で指定された区切り文字が使用されるようになりました。 詳しくは、 [リスト](/help/implement/vars/page-vars/list.md) 変数を参照してください。 |
| **Data Workbench のサポート終了** | 2022年9月14日（PT） | Adobeは、提供終了のData Workbench効果を期待 **2023 年 12 月 31 日**. ご質問がある場合は、のData Workbenchに代わる解決策について、カスタマーケア担当者にお問い合わせください。 |
| **Google クライアントヒントによるデバイス検索の更新** | 2022年8月19日（PT） | 開始日 **2022 年 10 月 27 日** Adobeは、Google Chrome やMicrosoft Edge など、Chromium ブラウザーからのヒットに関する特定のデバイス情報を取得する際に、User-Agent に加えて、クライアントヒントを使用し始めます。 これは、Googleの計画に応じて、クライアントヒントを介して渡されるデータの代わりに、User-Agent 文字列から提供される情報を徐々に減らすことです。 クライアントヒントについて詳しくは、[こちら](https://web.dev/user-agent-client-hints/)を参照してください。<p> 10 月までに、AppMeasurement と Web SDK の両方のコレクションライブラリは、クライアントヒントの収集をサポートし、高エントロピーのクライアントヒントを収集するかどうかを設定します。 この変更の一環として、Adobeは、User-Agent に関連するすべてのデバイス参照に Device Atlas を使用します。 現在、Device Atlas はモバイルのヒットに対してのみ使用されています。これらの更新により、以前はユーザーエージェント（特に、ブラウザー、ブラウザーのタイプ、オペレーティングシステム、オペレーティングシステムのタイプ、モバイルデバイス）から導き出されたデバイス情報に小さな変更が生じる場合があります。 [詳細情報](/help/technotes/client-hints.md) |
| **Reports &amp; Analytics での予定レポートの一時停止** | 2022年6月8日（PT） | 2022 年 4 月 22 日に、Adobeは、以前に Reports &amp; Analytics の提供終了に備えて、予定レポートに固有の機能の一部を廃止することを発表しました。 これらの機能には、新規レポートのスケジュール設定機能と、新規データ抽出機能が含まれていました。<p>Adobeは、拡張機能を求めるお客様の要求に応え、Reports &amp; Analytics からの移行を容易にするために、 **2023 年 1 月 31 日**. レポートとデータ抽出の両方の有効期限は、引き続き 9 か月に制限されることに注意してください。レポートおよびデータ抽出の配信は、スケジュールが再アクティブ化されない限り、この期間終了後に一時停止されます。<p>繰り返しになりますが、これらの機能は 2023年1月31日（PT）に廃止されます。この日付までに、予定レポートを Adobe Analytics で使用できる他のメカニズムのいずれかに移行する必要があります。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Report Builder での予定タスクの一時停止** | 2022年6月8日（PT） | 2022 年 4 月 22 日に、Adobeは、パフォーマンスおよび配信の最適化作業の一環として、Report Builderの予定タスクに対する変更をロールアウトしました。 これらの変更には、スケジュールされた配信の「x 回後に終了」機能の削除が含まれています。お客様の複数の要望に応えて、代替案の調査と導入にさらに時間をかけるため、Adobeは、このオプションを、 **2023 年 1 月 31 日**.<p>1 時間ごとの Report Builder タスクのスケジュールを継続し、最大 99 回発生した後にタスクを終了させることができます。ロールバックは 1 時間ごとのタスクにのみ適用されることに注意してください。「x 回後に終了する」は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できません。このオプションは、2023年1月31日（PT）に廃止されることに注意してください。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日（PT）**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

AppMeasurement リリース（バージョン 2.23.0）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。
