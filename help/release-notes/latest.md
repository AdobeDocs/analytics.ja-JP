---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: df9e8e323ba12985761b38c403bb4114cc99f5fe
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 96%

---

# 現在の Adobe Analytics リリースノート（2022年6月）

**最終更新日**:2022 年 7 月 14 日

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| **新しいフロービジュアライゼーション UI** | フロービジュアライゼーションがさらに強力で高機能になる追加の機能を提供します。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=ja) | 2022年6月15日（PT）に順次展開を開始、2022年6月27日または 28日（PT）までに GA |
| **モバイルスコアカードで注釈を共有** | ワークスペースで作成された注釈をモバイルスコアカードに表示できます。これにより、組織とキャンペーンに関するコンテキストデータのニュアンスやインサイトを、モバイルスコアカードプロジェクト内で直接共有でき、Analytics ダッシュボードモバイルアプリで表示できます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/mobile-annotations.html?lang=ja) | 2022年6月15日（PT） |
| **Edge コレクションを使用したマーチャンダイジング変数の product 構文バージョンのサポート** | 関連する XDM フィールドを設定することで、製品product 構文と同等のものを使用してマーチャンダイジング変数を設定できるようになりました。`products` 変数を使用したWeb SDK 構文について詳しくは[ products 変数](../implement/vars/page-vars/products.md)を、使用できる変数の一覧については[Adobe Experience Edge の Analytics 変数マッピング](../implement/aep-edge/variable-mapping.md)を参照してください。 | 2022年6月15日（PT） |
| **Experience Edge を通じてライフサイクルディメンションと指標を入力する** | Experience Edge を介して送信されたモバイルライフサイクルデータが、Analytics レポートに表示されるようになりました。XDM フィールドを既存のモバイルライフサイクルレポートにマッピングする方法について詳しくは、ドキュメントを参照してください。[詳細情報](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) | 2022年5月27日（PT） |
| **Analytics の処理ルールで使用可能な Mobile Service の処理ルール** | Adobe Mobile Services の提供終了日は、2022年12月31日（PT）です。Adobe Mobile Services で作成または生成された既存の処理ルールは、Adobe Analytics の処理ルールへと自動的に移行され、そこで編集および管理できます。 これらは表示できますが、製品が廃止されるまで、Mobile Services では編集できなくなります。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](https://experienceleague.adobe.com/docs/mobile-services/using/eol.html?lang=ja) | 2022年6月15日（PT） |
| **分類セット - フェーズ 1** | 新しい分類ユーザーエクスペリエンスの段階的リリースにより、顧客が所有する分類データの可視性が大幅に向上しました。詳しくは、[分類セット](../components/classifications/sets/overview.md)を参照してください。 | 2022年6月15日（PT）限定テスト開始、一般公開は2023年初頭を予定 |

{style=&quot;table-layout:auto&quot;}

### Adobe Analytics の修正点

AN-251686、AN-283542、AN-286572、AN-286945、AN-286784、AN-286944、AN-287012、AN-287319、AN-287333、AN-287348、AN-287429、AN-288238、AN-288281、AN-288660、AN-288769、AN-288798、AN-288871、AN-288872、AN-288941、AN-288951、AN-288952、AN-288956、AN-289062、AN-289340、AN-289346、AN-289488、AN-289562、AN-289580、AN-289861、AN-289892;

### Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **システムで生成された E メールの新しいドメイン** | 2022 年 7 月 14 日 | Adobeは最近、Workspace プロジェクト、アラート、および超過アラートからの E メールの送信者ドメインを、次の場所から変更しました： `noreply@omniture.com` から `noreply@adobe.com`. 組織が特定の送信者のみを許可している場合は、許可リストにこの新しいメールを追加します。 |
| **Reports &amp; Analytics での予定レポートの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、以前に発表された Reports &amp; Analytics の提供終了に備えて、予定レポートに固有のいくつかの機能が廃止されることを発表しました。これらの機能には、新規レポートのスケジュール設定機能と、新規データ抽出機能が含まれていました。<p>延長を求めるお客様の要求に応え、Reports and Analytics からの移行を容易にするために、これらの機能へのアクセスを **2023年1月31日（PT）**&#x200B;まで延長することに決定しました。レポートとデータ抽出の両方の有効期限は、引き続き 9 か月に制限されることに注意してください。レポートおよびデータ抽出の配信は、スケジュールが再アクティブ化されない限り、この期間終了後に一時停止されます。<p>繰り返しになりますが、これらの機能は 2023年1月31日（PT）に廃止されます。この日付までに、予定レポートを Adobe Analytics で使用できる他のメカニズムのいずれかに移行する必要があります。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Report Builder での予定タスクの一時停止** | 2022年6月8日（PT） | 2022年4月21日（PT）に、パフォーマンスと配信の最適化の一環として、Report Builder のスケジュールされたタスクに変更を加えました。これらの変更には、スケジュールされた配信の「x 回後に終了」機能が削除されることが含まれています。代替案の検討や導入にさらなる時間の確保が必要であるとのお客様の要望に応えて、アドビでは、 **2023年1月31日（PT）**&#x200B;まで限定的にこのオプションを復元することが決定されました。<p>1 時間ごとの Report Builder タスクのスケジュールを継続し、最大 99 回発生した後にタスクを終了させることができます。ロールバックは 1 時間ごとのタスクにのみ適用されることに注意してください。「x 回後に終了する」は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できません。このオプションは、2023年1月31日（PT）に廃止されることに注意してください。その他の質問やサポートについては、アドビのカスタマーケアにお問い合わせください。[詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP アップグレード** | 2022年5月9日（PT） | 以前 2022年5月にアドビがセキュアファイル転送プロトコル（SFTP）サービスをアップグレードし、ファイル転送のセキュリティを強化することをお伝えしました。このアップグレードは **2022年夏**&#x200B;に延期となりました。この変更が行われると、特定の SFTP クライアント設定はサポートされなくなります。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| **特定の顧客でサポートされるブラウザー暗号化メソッドへのアップデート** | 2022年3月28日（PT） | アドビでは、2 種類の暗号セキュリティレベルを提供し、1st パーティのデータ収集におけるセキュリティに関するお客様の様々なニーズに対応しています。**2022年6月23日（PT）**&#x200B;に、セキュリティレベルが「高」に設定されているお客様に対して、暗号として知られる特定の HTTPS 暗号化アルゴリズムのサポートを削除します。このアクションは、一部の古いオペレーティングシステムでは最新の暗号化方法に対応していないので、Analytics にデータを送信できなくなったことを意味します。デフォルトの「標準」暗号セキュリティ設定を使用しているお客様には影響はありません。現在「高」の設定を使用しているすべてのお客様には、既にご連絡済みです。この影響を受ける暗号の詳細リスト |
| **2022年 ISO の地域のアップデート** | 2021年3月11日（PT） | **2022年6月10日（PT）**&#x200B;に、2022年の ISO 地域のアップデートを実施します。このリリース以降、マイナーな地域情報に関するアップデートが提供される可能性があります。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日（PT）**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

