---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1843989f77482152adeaee1f1c9e523d0c55dc21
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 79%

---

# 最新のAdobe Analyticsリリースノート（2022 年 10 月）

**最終更新日**:2022 年 10 月 6 日

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能または更新された機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| **[!UICONTROL 主要指標の概要]** 視覚化 | この [!UICONTROL 主要指標の概要] ビジュアライゼーションを使用すると、1 つの期間内で重要な指標がどのようにトレンドを示しているかを確認できます。 また、2 つの期間にわたる指標のパフォーマンスを比較することもできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=en) | 2022 年 10 月 6 日からの段階的な展開 |
| 新規 **[!UICONTROL 分類セット]** ユーザーエクスペリエンス | この新しいユーザーエクスペリエンスは、分類とルールを管理する単一のインターフェイスを備え、顧客が所有する分類データをより可視性が高まります。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=en) | 2022 年 10 月 6 日 |
| モバイルアプリ： **カスタム詳細ビュー** | カスタムの詳細ビューを使用すると、最も重要な情報に焦点を当てることで、オーディエンスと共有する情報に関してさらにターゲットを絞ることができます。 各スコアカードタイルに関連付けられた詳細ビューのレイアウトを変更し、テキストを追加して、エンドユーザーがデータに表示する内容をより深く説明することができます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=ja) | 2022 年 10 月 6 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

AN-298512;AN-300117;AN-301754;AN-301584;AN-301685;AN-301783;AN-301818;AN-301825;AN-301834;AN-301965;AN-302095;AN-302189;AN-302269;AN-302290;AN-302301;AN-302348;AN-302531;AN-302533;


## Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **デフォルトのランディングページ** | 2022年9月29日（PT） | この [新規ランディングページ](/help/analyze/landing.md) 今年初めに導入されたは、 **2023 年 1 月**. 現在のページは非推奨となり、新しいエクスペリエンスを使用するには全員が必要になります。 |
| **の EOL [!UICONTROL 発行リスト] 機能** | 2022年9月29日（PT） | Reports &amp; Analytics のサポート終了の一環として、発行リストは、 **2023 年 12 月**. 新しい発行リストを作成したり、既存の発行リストにアクセスしてAnalysis Workspaceプロジェクトを送信したり、スケジュールを設定したりすることはできません。 [詳細情報](/help/admin/admin/publishing-list.md) |
| **[!UICONTROL 異常値検出] 自動実行条件** | 2022年9月29日（PT） | 今日、 [!UICONTROL 異常値検出] 時系列フリーフォームテーブルのすべての列で自動実行されます。 データを分析やプロジェクトの読み込みを高速化するために、Adobeは異常値検出の自動実行方法を変更します。 開始中 **2022 年 10 月 27 日**, [!UICONTROL 異常値検出] は、テーブルの最初の指標列でのみ自動実行されます。 必要に応じて、他の列で異常値検出を実行するように列設定を指定できます。 |
| **新しい NetAcuity 通信事業者データベースの更新** | 2022年9月26日（PT） | この更新は、当初 2022年10月5日（PT）に予定していましたが、**2023年1月**&#x200B;に延期されました。Adobe Analytics Data Warehouse および Analytics データフィードの `carrier` フィールドに保存されている通信事業者関連の情報が変更されます。従来、その列のデータ形式は `<domain>:<ISP>` でした。Adobe Analytics レポートツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など）でレポートを作成するために、これらの `<domain>:<ISP>` 値を通信事業者名にマッピングするための内部ルックアップテーブルがメンテナンスされました。ルックアップファイル（`carrier.tsv`）にもデータフィードが用意されているので、同じマッピングを使用できます。<p>この更新により、NetAcuity のより正確な通信事業者データベースを使用して通信事業者のマッピングが強化されます。データフィードの通信事業者列のデータ形式は、今後変更される予定です。`<domain>:<ISP>` の代わりに、通信事業者名が含まれます。アドビでは、従来のレポートとの継続性をできる限り維持するために、引き続きルックアップテーブルを使用します。アドビがルックアップを適用するレポートツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など）は、より正確なマッピングのメリットを享受できます。新しいデータベースを採用すると、一部のマッピング（特に国際ドメインおよび ISP の場合）は、他のマッピングよりも変更が多くなります。データフィード通信事業者ルックアップファイル（`carrier.tsv`）では、古いマッピングが維持され、新しいマッピングが追加されます。<p>Analytics ソースコネクタでは、現在、通信事業者フィールドのマッピングは行っていません。そのため、通信事業者レポートは、現在、Experience Platform、CJA などでは使用できません。したがって、新しい通信事業者データベースを使用しても、Analytics ソースコネクタから提供されるデータに基づいている限り Experience Platform での影響はありません。 |
| **IP からジオロケーションへのマッピングの改善** | 2022年9月26日（PT） | IP ルックアップに関する当社のベンダー（Digital Element）は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）にアップグレードしつつあります。当初 2022年10月に予定していましたが、Adobe Analytics では、**2023年1月**&#x200B;にこの新しいデータセットを採用します。新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p>すべての Adobe Analytics ツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream、データフィードなど）は、新しく改善されたマッピングを自動的に利用します。データフィードのデータの形式は変更されません。Analytics ソースコネクタを通じて提供される CJA データでも、新しいマッピングを自動的に利用します。 |
| **SFTP アップグレード** | 2022年9月19日（PT） | 以前、アドビは、2022年9月にセキュアファイル転送プロトコル（SFTP）サービスをアップグレードし、ファイル転送のセキュリティを強化することをお伝えしました。アドビでは、このアップグレードを **2022年9月20日**（PT）に実施しました。この変更により、特定の SFTP クライアント設定がサポートされなくなりました。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| **Data Workbench のサポート終了** | 2022年9月14日（PT） | **2023年12月31日（PT）**&#x200B;をもって、アドビは Data Workbench のサポートを終了する予定です。Data Workbench の代替ソリューションに関してご不明な点がある場合は、カスタマーケア担当者にお問い合わせください。 |
| **Google クライアントヒントによるデバイス検索の更新** | 2022年8月19日（PT） | **2022年10月26日**&#x200B;以降、アドビでは、Google Chrome および Microsoft Edge などの Chromium ブラウザーからのヒットに関する特定のデバイス情報を取得する際に、User-Agent に加えて、クライアントヒントを使用するようになります。これは、クライアントヒントを介して渡されるデータの代わりに、User-Agent 文字列から提供される情報を徐々に減らす Google の計画に対応するものです。クライアントヒントについて詳しくは、[こちら](https://web.dev/user-agent-client-hints/)を参照してください。<p> 10月まで、AppMeasurement および Web SDK の両方のコレクションライブラリは、クライアントヒントの収集と、高エントロピーなクライアントヒントを収集するかどうかの設定をサポートします。この変更の一環として、アドビは、User-Agent に関連するすべてのデバイス検索に対して Device Atlas を使用します。現在、Device Atlas はモバイルのヒットに関してのみ使用されています。これらのアップデートにより、以前は User-Agent（特に、ブラウザー、ブラウザーのタイプ、オペレーティングシステム、オペレーティングシステムのタイプ、モバイルデバイス）から導き出されたデバイス情報に小さな変更が生じる場合があります。[詳細情報](/help/technotes/client-hints.md) |
| **Reports &amp; Analytics での予定レポートの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、アドビは、以前に発表された Reports &amp; Analytics の提供終了に備えて、予定レポートに固有のいくつかの機能が廃止されることを発表しました。これらの機能には、新規レポートのスケジュール設定機能と、新規データ抽出機能が含まれていました。<p>延長を求めるお客様の要求に応え、Reports &amp; Analytics からの移行を容易にするために、アドビでは、これらの機能へのアクセスを **2023年1月31日（PT）**&#x200B;まで延長することに決定しました。レポートとデータ抽出の両方の有効期限は、引き続き 9 か月に制限されることに注意してください。レポートおよびデータ抽出の配信は、スケジュールが再アクティブ化されない限り、この期間終了後に一時停止されます。<p>繰り返しになりますが、これらの機能は 2023年1月31日（PT）に廃止されます。この日付までに、予定レポートを Adobe Analytics で使用できる他のメカニズムのいずれかに移行する必要があります。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Report Builder での予定タスクの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、アドビは、パフォーマンスと配信の最適化の一環として、Report Builder のスケジュールされたタスクに変更を加えました。これらの変更には、スケジュールされた配信の「x 回後に終了」機能の削除が含まれています。代替案の検討や導入にさらなる時間の確保が必要であるとのお客様の要望に応えて、アドビでは、 **2023年1月31日（PT）**&#x200B;まで限定的にこのオプションを復元することが決定されました。<p>1 時間ごとの Report Builder タスクのスケジュールを継続し、最大 99 回発生した後にタスクを終了させることができます。ロールバックは 1 時間ごとのタスクにのみ適用されることに注意してください。「x 回後に終了する」は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できません。このオプションは、2023年1月31日（PT）に廃止されることに注意してください。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日（PT）**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

AppMeasurement リリース（バージョン 2.23.0）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。
