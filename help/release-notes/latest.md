---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 74c347c72394b75cc332ae459b9cbf1f72fa033b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 最新のAdobe Analyticsリリースノート（2022 年 9 月）

**最終更新日**:2022 年 9 月 10 日

>[!NOTE]
>
>このページに記載される内容は、リリース前の情報であり、変更される可能性があります。

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能または更新された機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| Workspace でのコンボグラフのビジュアライゼーション | コンボグラフを使用すると、Workspace 内で指標をより簡単かつ直感的に比較できます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts.html) | 2022 年 9 月 15 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* 分類のインポートとエクスポートの問題を修正しました。 (AN-299267)

**個人のお客様向けの修正点**：

AN-288519;AN-289300;AN-297387;AN-297465;AN-297520;AN-297641;AN-298134;AN-298351;AN-298429;AN-298483;AN-298520;AN-298582;AN-298816;AN-298832;AN-298855;AN-298864;AN-299407;AN-299545;AN-299644;AN-299715

## Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **SFTP アップグレード** | 2022 年 9 月 10 日 | 以前は、Adobeが 2022 年 9 月に Secure File Transfer Protocol(SFTP) サービスをアップグレードして、ファイル転送のセキュリティを強化することをお知らせしていました。 このアップグレードを **2022 年 9 月中旬～後半**. この変更が行われると、特定の SFTP クライアント設定はサポートされなくなります。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| **Data Workbench用 EOL** | 2022 年 9 月 10 日 | Adobeは、有効なサポート終了のData Workbenchを意図しています **2023 年 12 月 31 日**. 詳細は近日中に伝えられます。 |
| **Google クライアントヒントによるデバイス検索の更新** | 2022 年 9 月 10 日 | 開始日 **2022 年 9 月 30 日** Adobeは、Google Chrome やMicrosoft Edge など、Chromium ブラウザーからのヒットに関する特定のデバイス情報を取得する際に、ユーザーエージェントに加えて、クライアントヒントを使用し始めます。 これは、Googleの計画に応じて、クライアントヒントを介して渡されるデータの代わりに、ユーザーエージェント文字列から提供される情報を徐々に減らすようにするものです。 クライアントヒントについて詳しくは、[こちら](https://web.dev/user-agent-client-hints/)を参照してください。<p> 10月までに、AppMeasurement および Web SDK の両方のコレクションライブラリは、クライアントヒントの収集と、高エントロピーなクライアントヒントを収集するかどうかの設定をサポートします。この変更の一環として、アドビは、ユーザーエージェントに関連するすべてのデバイス検索に対して Device Atlas を使用します。現在、Device Atlas はモバイルのヒットに対してのみ使用されています。これらの更新により、以前はユーザーエージェント（特に、ブラウザー、ブラウザーのタイプ、オペレーティングシステム、オペレーティングシステムのタイプ、モバイルデバイス）から導き出されたデバイス情報に小さな変更が生じる場合があります。 |
| **新しい NetAcuity 通信事業者データベースの更新** | 2022 年 9 月 10 日 | **2022 年 10 月 6 日以降**、 `carrier` Adobe AnalyticsData Warehouseおよび Analytics データフィードのフィールドが変更されます。 従来、その列のデータ形式は `<domain>:<ISP>` でした。Adobe Analytics レポートツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など）でレポートを作成するために、これらの `<domain>:<ISP>` 値を通信事業者名にマッピングするための内部ルックアップテーブルがメンテナンスされました。ルックアップファイル（`carrier.tsv`）にもデータフィードが用意されているので、同じマッピングを使用できます。<p>この更新により、NetAcuity のより正確な通信事業者データベースを使用して通信事業者のマッピングが強化されます。データフィードの通信事業者列のデータ形式は、今後変更される予定です。`<domain>:<ISP>` の代わりに、通信事業者名が含まれます。アドビでは、従来のレポートとの継続性をできる限り維持するために、引き続きルックアップテーブルを使用します。アドビがルックアップを適用するレポートツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など）は、より正確なマッピングのメリットを享受できます。新しいデータベースを採用すると、一部のマッピング（特に国際ドメインおよび ISP の場合）は、他のマッピングよりも変更が多くなります。データフィード通信事業者ルックアップファイル（`carrier.tsv`）では、古いマッピングが維持され、新しいマッピングが追加されます。<p>Analytics ソースコネクタでは、現在、通信事業者フィールドをマッピングしていないので、通信事業者レポートは、現在、AEP、CJA などでは使用できません。したがって、新しい通信事業者データベースを使用しても、Analytics ソースコネクタから提供されるデータに基づいている限り AEP での影響はありません。 |
| **IP からジオロケーションへのマッピングの改善** | 2022 年 9 月 10 日 | IP ルックアップに関する当社のベンダー（Digital Element）は、IP からジオロケーションへのマッピング用に新しく改善されたデータセット（NetAcuity Pulse）にアップグレードしつつあります。 Adobe Analyticsは、 **2022 年 10 月 6 日**. 新しいデータベースは、以前のバージョンよりも正確になります。新しいデータベースを採用する際に、IP からジオロケーションへのマッピングは一部変更または改善されます。<p>すべての Adobe Analytics ツール（Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream、データフィードなど）は、新しく改善されたマッピングを自動的に利用します。データフィードのデータの形式は変更されません。Analytics ソースコネクタを通じて提供される CJA データでも、新しいマッピングを自動的に利用します。 |
| **Reports &amp; Analytics での予定レポートの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、以前に発表された Reports &amp; Analytics の提供終了に備えて、予定レポートに固有のいくつかの機能が廃止されることを発表しました。これらの機能には、新規レポートのスケジュール設定機能と、新規データ抽出機能が含まれていました。<p>延長を求めるお客様の要求に応え、Reports and Analytics からの移行を容易にするために、これらの機能へのアクセスを **2023年1月31日（PT）**&#x200B;まで延長することに決定しました。レポートとデータ抽出の両方の有効期限は、引き続き 9 か月に制限されることに注意してください。レポートおよびデータ抽出の配信は、スケジュールが再アクティブ化されない限り、この期間終了後に一時停止されます。<p>繰り返しになりますが、これらの機能は 2023年1月31日（PT）に廃止されます。この日付までに、予定レポートを Adobe Analytics で使用できる他のメカニズムのいずれかに移行する必要があります。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Report Builder での予定タスクの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、パフォーマンスと配信の最適化の一環として、Report Builder のスケジュールされたタスクに変更を加えました。これらの変更により、スケジュールされた配信の「x 回後に終了」機能が削除されることが含まれていました。 代替案の検討や導入にさらなる時間の確保が必要であるとのお客様の要望に応えて、アドビでは、 **2023年1月31日（PT）**&#x200B;まで限定的にこのオプションを復元することが決定されました。<p>1 時間ごとの Report Builder タスクのスケジュールを継続し、最大 99 回発生した後にタスクを終了させることができます。ロールバックは時間別タスクにのみ適用されることに注意してください。「x 回後に終了する」回数は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できなくなります。 このオプションは、2023年1月31日（PT）に廃止されることに注意してください。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日（PT）**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。以下を実現するレポート、ビジュアライゼーションおよび基盤となるテクノロジー [!DNL Reports & Analytics] もはやAdobeの技術基準を満たさない ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

