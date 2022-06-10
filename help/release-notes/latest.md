---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cf291c4d46a6bff9e1c61804ca7e897ee1d4e4d5
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 49%

---

# 最新のAdobe Analyticsリリースノート（2022 年 6 月）

>[!NOTE]
>
>このページに記載される内容は、リリース前の情報であり、変更される可能性があります。

**最終更新日**:2022 年 6 月 11 日

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| 新しいフロービジュアライゼーション UI | フロービジュアライゼーションに追加の機能を提供して、より強力で高機能にします。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=en) | 2022年6月15日（PT） |
| モバイルスコアカードでの注釈の共有 | Workspace で作成された注釈をモバイルスコアカードに表示できます。 これにより、組織とキャンペーンに関するコンテキストデータのニュアンスやインサイトを、Mobile Scorecard プロジェクト内で直接共有でき、Analytics ダッシュボードモバイルアプリで表示できます。 詳細情報（フォロー） | 2022年6月15日（PT） |
| Edge Collection を使用したマーチャンダイジング変数の製品構文バージョンのサポート | 関連する XDM フィールドを設定することで、製品構文と同等のものを使用してマーチャンダイジング変数を設定できるようになりました。 マーチャンダイジング変数の製品構文の詳細を見る [ここ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=ja). 製品の構文のマッピングを参照してください [ここ](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en#aep-edge). | 2022年6月15日（PT） |
| Experience Edge を通じてライフサイクルディメンションと指標を入力する | Experience Edge を介して送信されたモバイルライフサイクルデータが、Analytics レポートに表示されるようになりました。XDM フィールドを既存のモバイルライフサイクルレポートにマッピングする方法の詳細については、ドキュメントを参照してください。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 2022年5月27日（PT） |
| 新しい分類のエクスペリエンス — フェーズ 1 | 新しい分類セットユーザーエクスペリエンスの段階的リリースにより、顧客が所有する分類データの可視性が大幅に向上しました。 GA は 2023 年初頭に推定されている。 | 制限付きテストは 2022 年 6 月 15 日から開始します |

{style=&quot;table-layout:auto&quot;}

### Adobe Analytics の修正点

AN-251686、AN-283542、AN-286572、AN-286945、AN-286784、AN-286944、AN-287012、AN-287319、AN-287333、AN-287348、AN-287429、AN-288238、AN-288281、AN-288660、AN-288769、AN-288798、AN-288871、AN-288872、AN-288941、AN-288951、AN-288952、AN-288956、AN-289062、AN-289340、AN-289346、AN-289488、AN-289562、AN-289580、AN-289861、AN-289892;

### Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **Reports &amp; Analytics での予定レポートの一時停止** | 2022 年 6 月 9 日 | 2022 年 4 月 22 日に、以前に Reports &amp; Analytics の提供終了に備えて、予定レポートに固有の機能のいくつかは廃止されることを発表しました。 これらの機能には、新しいレポートのスケジュール設定機能と、新しいデータ抽出機能が含まれていました。<p>Reports and Analyticsからの移行を容易にするために、拡張機能を求めるお客様の要求に応えて、以下の機能へのアクセスをまで拡張することにしました。 **2023 年 1 月 31 日**. レポートとデータ抽出の両方の有効期限は、引き続き 9 か月に制限されます。レポートおよびデータ抽出の配信は、スケジュールが再度アクティブ化されない限り、この期間の終わりに一時停止します。<p>繰り返しますが、これらの機能は 2023 年 1 月 31 日に廃止されます。 この日までに、予定レポートをAdobe Analyticsで使用できる他のメカニズムの 1 つに移行する必要があります。 その他の質問やサポートについては、Adobe カスタマーケアにお問い合わせください。[詳細情報](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **スケジュールされたタスクのReport Builder** | 2022 年 6 月 9 日 | 2022 年 4 月 22 日に、パフォーマンスと配信の最適化の一環として、Report Builderの予定タスクに変更を加えました。 これらの変更により、スケジュールされた配信の「x 回後に終了」機能が削除されることが含まれていました。 お客様の複数の要望に応えて、代替案の検討や導入にさらに時間をかけようと、アドビでは、このオプションを以前まで限られた方法で復元することにしました。 **2023 年 1 月 31 日**.<p>引き続き時間別Report Builderタスクのスケジュールを設定し、最大 99 回のタスクの後でタスクを終了させることができます。 ロールバックは時間別タスクにのみ適用されることに注意してください。「x 回後に終了する」回数は、その他のすべての配信間隔（日別、週別、月別、年別）では使用できなくなります。 このオプションは 2023 年 1 月 31 日に廃止されます。 その他の質問やサポートについては、Adobeカスタマーケアにお問い合わせください。 [詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP アップグレード** | 2022年5月9日（PT） | 以前 2022年5月にアドビがセキュアファイル転送プロトコル（SFTP）サービスをアップグレードし、ファイル転送のセキュリティを強化することをお伝えしました。このアップグレードを **2022 年夏**. この変更が行われると、特定の SFTP クライアント設定はサポートされなくなります。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| **特定の顧客でサポートされるブラウザー暗号化メソッドへのアップデート** | 2022年3月28日（PT） | アドビでは、2 種類の暗号セキュリティレベルを提供し、1st パーティのデータ収集におけるセキュリティに関するお客様の様々なニーズに対応しています。**2022年6月23日（PT）**&#x200B;に、セキュリティレベルが「高」に設定されているお客様に対して、暗号として知られる特定の HTTPS 暗号化アルゴリズムのサポートを削除します。このアクションは、一部の古いオペレーティングシステムでは最新の暗号化方法に対応していないので、Analytics にデータを送信できなくなったことを意味します。デフォルトの「標準」暗号セキュリティ設定を使用しているお客様には影響はありません。現在「高」の設定を使用しているすべてのお客様には、既にご連絡済みです。この影響を受ける暗号の詳細なリスト |
| **2022年 ISO の地域のアップデート** | 2021年3月11日（PT） | Adobeは、2022 年に ISO 地域の更新を実行しました： **2022 年 6 月 11 日**. このリリース以降、マイナーな地域情報に関するアップデートが提供される可能性があります。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日**（PT）をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

