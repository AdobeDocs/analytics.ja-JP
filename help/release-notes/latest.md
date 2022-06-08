---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 8666c32ffe907ad486778fa382404807459be03c
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 62%

---

# 最新の Adobe Analytics リリースノート（2022年5月）

**最終更新日**:2022 年 6 月 9 日

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| Experience Edge を通じてライフサイクルディメンションと指標を入力する | Experience Edge を介して送信されたモバイルライフサイクルデータが、Analytics レポートに表示されるようになりました。Experience Edge を介して収集されるライフサイクルデータと、それが既存のライフサイクルレポートにどのように対応するかについて詳しくは、ドキュメントを参照してください。[詳細情報](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 2022年5月27日（PT） |

{style=&quot;table-layout:auto&quot;}

### Adobe Analytics の修正点

（複数のお客様に対する修正点）

該当なし

### Adobe Analytics におけるその他の修正点

（個人のお客様向けの修正点）

AN-274429、AN-279640、AN-280918、AN-280945、AN-282884、AN-283565、AN-284785、AN-284814、AN-284854、AN-284989、AN-285244、AN-285253、AN-285432、AN-285528、AN-285535、AN-285710、AN-286255、AN-286340、AN-286434、AN-286454、AN-286630、AN-286716、AN-286854、AN-286911

### Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| Reports &amp; Analytics での予定レポートの一時停止 | 2022 年 6 月 9 日 | 2022 年 4 月 22 日に、以前に発表したに備えて、予定レポートに固有の機能のいくつかは廃止されることを発表しました [Reports &amp; Analytics の提供終了](https://express.adobe.com/page/6WnF8JK6IRDhf/). これらの機能には、新しいレポートのスケジュール設定機能と、新しいデータ抽出機能が含まれていました。<p>Reports and Analyticsからの移行を容易にするために、拡張機能を求めるお客様の要求に応えて、以下の機能へのアクセスをまで拡張することにしました。 **2023 年 1 月 31 日**. レポートとデータ抽出の両方の有効期限は、引き続き 9 か月に制限されます。レポートおよびデータ抽出の配信は、スケジュールが再度アクティブ化されない限り、この期間の終わりに一時停止します。 <p>繰り返しますが、これらの機能は 2023 年 1 月 31 日に廃止されます。その前に、予定レポートをAdobe Analyticsで使用可能な他のメカニズムの 1 つに移行する必要があります。 その他の質問やサポートについては、Adobe カスタマーケアにお問い合わせください。 |
| スケジュールされたタスクのReport Builder | 2022 年 6 月 9 日 | 2022 年 4 月 22 日に、パフォーマンスと配信の最適化の一環として、Report Builderの予定タスクに変更を加えました。 これらの変更により、スケジュールされた配信の「x 回後に終了」機能が削除されることが含まれていました。 お客様の複数の要望に応えて、代替案の検討や導入にさらに時間をかけようと、アドビでは、このオプションを以前まで限られた方法で復元することにしました。 **2023 年 1 月 31 日**.<p>引き続き、時間別のReport Builderタスクをスケジュールでき、最大 99 回のタスクの後にタスクを終了させることができます。 ロールバックは時間別タスクにのみ適用されることに注意してください。「x 回後に終了する」回数は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できなくなります。 このオプションは 2023 年 1 月 31 日に廃止されます。 その他の質問やサポートについては、Adobeカスタマーケアにお問い合わせください。 |
| **SFTP アップグレード** | 2022年5月9日（PT） | 以前 2022年5月にアドビがセキュアファイル転送プロトコル（SFTP）サービスをアップグレードし、ファイル転送のセキュリティを強化することをお伝えしました。このアップグレードを **2022 年夏**. この変更が行われると、特定の SFTP クライアント設定はサポートされなくなります。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| **特定の顧客でサポートされるブラウザー暗号化メソッドへのアップデート** | 2022年3月28日（PT） | アドビでは、2 種類の暗号セキュリティレベルを提供し、1st パーティのデータ収集におけるセキュリティに関するお客様の様々なニーズに対応しています。**2022年6月23日（PT）**&#x200B;に、セキュリティレベルが「高」に設定されているお客様に対して、暗号として知られる特定の HTTPS 暗号化アルゴリズムのサポートを削除します。このアクションは、一部の古いオペレーティングシステムでは最新の暗号化方法に対応していないので、Analytics にデータを送信できなくなったことを意味します。デフォルトの「標準」暗号セキュリティ設定を使用しているお客様には影響はありません。現在「高」の設定を使用しているすべてのお客様には、既にご連絡済みです。この変更による影響を受ける暗号の詳細なリストについては、こちらを参照してください。 |
| **2022年 ISO の地域のアップデート** | 2021年3月11日（PT） | **2022年6月10日（PT）**&#x200B;に、2022年の ISO 地域のアップデートを実施します。このリリース以降、マイナーな地域情報に関するアップデートが提供される可能性があります。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日**（PT）をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

