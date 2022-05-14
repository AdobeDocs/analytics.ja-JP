---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: aa4dc06dc1719f398c29aeca40051d88f339ce42
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 89%

---

# 最新のAdobe Analyticsリリースノート（2022 年 5 月）

**最終更新日**:2022 年 5 月 12 日

>[!NOTE]
>
>このページに記載される内容は、リリース前の情報であり、変更される可能性があります。

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| 今月は新機能はありません | 該当なし | 該当なし |

{style=&quot;table-layout:auto&quot;}

### Adobe Analytics の修正点

（複数のお客様に対する修正点）

該当なし

### Adobe Analytics におけるその他の修正点

（個々のお客様向けの修正点）

AN-274429;AN-280918;AN-280945;AN-282884;AN-283565;AN-284785;AN-284814;AN-284854;AN-285253;AN-285432;AN-285535;AN-286255;AN-286340;AN-286434;AN-286454;AN-286630;AN-286716;AN-286854;AN-286911

### Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **SFTP アップグレード** | 2022 年 5 月 10 日 | 以前は、Adobeが 2022 年 5 月に Secure File Transfer Protocol(SFTP) サービスをアップグレードして、ファイル転送のセキュリティを強化することを伝えていました。 このアップグレードを 2022 年夏に延期しました。 この変更がおこなわれると、特定の SFTP クライアント設定はサポートされなくなります。 これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| **クロスデバイス分析（CDA）の使用権限** | 2022年4月13日（PT） | **2022年5月1日（PT）**&#x200B;より、[CDA](/help/components/cda/overview.md) の新規実装は、1 顧客あたり最大 3 つのレポートスイート ID（RSID）に制限されます。 |
| **Experience Edge 経由で収集された A4T データを Adobe Analytics が処理する方法の変更** | 2022年3月31日（PT） | 2022年3月7日（PT）に、Analytics for Target（A4T）レポート用の Target コンテンツを含む Experience Edge からの呼び出しの処理方法を変更しました。3月7日（PT）以降、A4T レポートのコンテンツを含むすべてのヒットが変更され、ページビューイベントやリンクイベントとして扱われなくなります。**2022年3月31日（PT）**&#x200B;以降、ロジックはより選択的になり、標準のページビューイベントとクリックイベントは変更されません。今後、変更されるイベントは、A4T コンテンツのみを持つパーソナライゼーション専用の呼び出しのみになります。 |
| **特定の顧客でサポートされるブラウザー暗号化メソッドへのアップデート** | 2022年3月28日（PT） | アドビでは、2 種類の暗号セキュリティレベルを提供し、1st パーティのデータ収集におけるセキュリティに関するお客様の様々なニーズに対応しています。**2022年6月23日（PT）**&#x200B;に、セキュリティレベルが「高」に設定されているお客様に対して、暗号として知られる特定の HTTPS 暗号化アルゴリズムのサポートを削除します。このアクションは、一部の古いオペレーティングシステムでは最新の暗号化方法に対応していないので、Analytics にデータを送信できなくなったことを意味します。デフォルトの「標準」暗号セキュリティ設定を使用しているお客様には影響はありません。現在「高」の設定を使用しているすべてのお客様には、既にご連絡済みです。この変更による影響を受ける暗号の詳細なリストについては、こちらを参照してください。 |
| **古い予定レポートの一時停止** | 2022年4月12日（PT） | **2022年4月20日（PT）** より、アドビは作成日から 2 年を超える（2020年1月31日以前に作成された）予定レポートをすべて一時停止する予定です。レポートやデータは削除されません。2 年以上経過していると識別されたレポートのみ一時停止され、それ以降予定レポートは送信されません。詳細情報 |
| **2022年 ISO の地域のアップデート** | 2021年3月11日（PT） | **2022年6月10日（PT）**&#x200B;に、2022年の ISO 地域のアップデートを実施します。このリリース以降、マイナーな地域情報に関するアップデートが提供される可能性があります。 |
| **過去のスケジュール済み Report Builder タスクの一時停止** | 2022年4月12日（PT） | **2022年4月20日（PT）** より、アドビは、2 年以上前に作成されたすべてのスケジュール済み Report Builder タスクを一時停止する予定です。特に、この一時停止は、2020年1月31日（PT）より前に作成されたすべてのタスクに適用されます。タスク、ワークブックまたはデータは削除されません。ただし、2 年以上経過していると識別されたタスクは一時停止され、スケジュールされたタスクはそれ以上送信されません。詳細情報 |
| **従来の Analytics OAuth／JWT 統合向け許可リスト EOL 拡張機能の有効期限** | 2022年1月14日（PT） | **2022年5月25日（PT）**&#x200B;に、[Analytics 1.3 API、1.4 SOAP API および Legacy Analytics OAuth／JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 許可リスト拡張機能の有効期限が切れます。この拡張機能は、従来の [!DNL Adobe Analytics] OAuth／JWT 認証情報を使用している顧客に、クライアント統合を[アドビ IMS 認証報](https://developer.adobe.com/console)に移行するための時間的余裕を提供するために提供されました。この有効期限は、必要な IMS 移行を完了していない [!DNL Adobe Analytics Livestream] および [!DNL Adobe Campaign] のお客様が対象となります（ただし、これに限定されるものではありません）。現在、許可リスト拡張機能により従来の [!DNL Analytics] OAuth／JWT 認証情報を使用しているお客様は、2022年5月25日（PT）までに IMS 認証情報への移行が完了しない場合、アドビサービスへのアクセスができなくなる可能性があります。Livestream のお客様は、クライアントアプリケーションを IMS 認証情報に移行する関する以下の [説明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) をご覧いただけます。[!DNL Campaign] のお客様は、[!DNL Campaign] の最新バージョンへのアップグレードについて、アドビアカウントチームにお問い合わせください。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日**（PT）をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

