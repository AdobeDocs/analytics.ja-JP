---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 94200622454fe2845a3b86025cd1796d29663736
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 54%

---

# 最新のAdobe Analyticsリリースノート（2022 年 7 月）

**最終更新日**:2022 年 7 月 14 日

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| XDM でのエッジコレクション用マーチャンダイジング変数のサポート | Experience Edge/Web SDK を介してデータを収集するお客様が XDM を使用して、マーチャンダイジング変数 (eVar) の様々な値を指定できるようにします。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar-merchandising.html?lang=en) | 2022年6月29日（PT） |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* 一部のセグメントコンバージョンエラーを修正しました。 （AN-291262、AN-294092）

**個々のお客様向けの修正点**:

AN-280192;AN-281628;AN-287022;AN-287104;AN-287876;AN-288802;AN-288457;AN-288779;AN-288799;AN-289198;AN-289852;AN-289931;AN-290162;AN-290213;AN-291059;AN-291090;AN-291270;AN-294091;AN-294135;AN-294152;AN-294158;AN-294285;AN-294317;AN-294404;AN-294531;AN-294769;AN-294984;AN-295172;AN-295211;AN-295224;AN-295413;AN-295440;AN-295465;AN-295499;AN-295516;

## Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **システムで生成された E メールの新しいドメイン** | 2022 年 7 月 14 日 | オン **2022 年 5 月 19 日**、Adobeは、Workspace プロジェクト、アラート、超過アラートからの電子メールの送信者のドメインを、次の場所から変更しました： `noreply@omniture.com` から `noreply@adobe.com`. 組織が特定の送信者のみを許可している場合は、許可リストにこの新しいメールを追加します。 |
| **新しい NetAcuity キャリアデータベースの更新** | 2022 年 7 月 12 日 | **2022 年 10 月開始**、 `carrier` Adobe AnalyticsData Warehouseおよび Analytics データフィードのフィールドが変更されます。 従来、この列のデータ形式は `<domain>:<ISP>`. Adobeは、これらをマッピングする内部ルックアップテーブルを維持しています `<domain>:<ISP>` Adobe Analyticsのレポートツール (Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など ) で、レポート目的で通信事業者名に また、ルックアップファイル (carrier.tsv) にはデータフィードが用意されているので、データフィードのお客様は同じマッピングを使用できます。<p>この更新により、NetAcuity のより正確な通信事業者データベースを使用して通信事業者のマッピングを強化します。 データフィードの carrier 列のデータの形式は、今後変更される予定です。 の代わりに `<domain>:<ISP>`の場合、通信事業者名が含まれます。 Adobeは、過去のレポートとの連続性を可能な限り維持するために、引き続きルックアップテーブルを使用します。 検索がAdobe(Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream など ) によって適用されるレポートツール は、より正確なマッピングのメリットを受けます。 一部のマッピング（特に国際ドメインおよび ISP の場合）は、新しいデータベースを採用する際に他のマッピングよりも多く変更されます。 データフィード通信事業者参照ファイル (carrier.tsv) は、古いマッピングを維持し、新しいマッピングを追加します。<p>Analytics ソースコネクタは、現在、carrier フィールドをマッピングしていないので、通信事業者レポートは、現在、AEP、CJA などでは使用できません。 したがって、新しい通信事業者データベースの使用は、Analytics ソースコネクタから提供されるデータに基づく AEP 内のデータには影響しません。 |
| **IP とジオロケーションのマッピングの改善** | 2022 年 7 月 12 日 | IP 検索 (Digital Element) に関する当社のベンダーは、IP とジオロケーションのマッピング用に新しく改良されたデータセット (NetAcuity Pulse) にアップグレードしています。 Adobe Analyticsは、 **2022 年 10 月** 期間。 新しいデータベースは、以前のバージョンよりも正確になります。 新しいデータベースを採用する際に、一部の IP と地域とのマッピングは変更/改善されます。<p>すべてのAdobe Analyticsツール (Analysis Workspace、Reports &amp; Analytics、レポート API、Data Warehouse、LiveStream、データフィードなど ) は、新しく改善されたマッピングを自動的に利用します。 データフィードのデータの形式は変更されません。 Analytics ソースコネクタを通じて提供される CJA データも、新しいマッピングを自動的に利用します。 |
| **Reports &amp; Analytics での予定レポートの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、以前に発表された Reports &amp; Analytics の提供終了に備えて、予定レポートに固有のいくつかの機能が廃止されることを発表しました。これらの機能には、新規レポートのスケジュール設定機能と、新規データ抽出機能が含まれていました。<p>延長を求めるお客様の要求に応え、Reports and Analytics からの移行を容易にするために、これらの機能へのアクセスを **2023年1月31日（PT）**&#x200B;まで延長することに決定しました。レポートとデータ抽出の両方の有効期限は、引き続き 9 か月に制限されることに注意してください。レポートおよびデータ抽出の配信は、スケジュールが再アクティブ化されない限り、この期間終了後に一時停止されます。<p>繰り返しになりますが、これらの機能は 2023年1月31日（PT）に廃止されます。この日付までに、予定レポートを Adobe Analytics で使用できる他のメカニズムのいずれかに移行する必要があります。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Report Builder での予定タスクの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、パフォーマンスと配信の最適化の一環として、Report Builder のスケジュールされたタスクに変更を加えました。これらの変更には、スケジュールされた配信の「x 回後に終了」機能が削除されることが含まれています。代替案の検討や導入にさらなる時間の確保が必要であるとのお客様の要望に応えて、アドビでは、 **2023年1月31日（PT）**&#x200B;まで限定的にこのオプションを復元することが決定されました。<p>1 時間ごとの Report Builder タスクのスケジュールを継続し、最大 99 回発生した後にタスクを終了させることができます。ロールバックは 1 時間ごとのタスクにのみ適用されることに注意してください。「x 回後に終了する」は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できません。このオプションは、2023年1月31日（PT）に廃止されることに注意してください。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP アップグレード** | 2022年5月9日（PT） | 以前 2022年5月にアドビがセキュアファイル転送プロトコル（SFTP）サービスをアップグレードし、ファイル転送のセキュリティを強化することをお伝えしました。このアップグレードは **2022年夏**&#x200B;に延期となりました。この変更が行われると、特定の SFTP クライアント設定はサポートされなくなります。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日（PT）**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

