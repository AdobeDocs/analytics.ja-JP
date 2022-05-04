---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c29515da8c74ad3332aa9797db9de505af7fe3aa
workflow-type: ht
source-wordcount: '1070'
ht-degree: 100%

---

# 現在の Adobe Analytics リリースノート（2022年4月）

**最終更新日**：2022年4月28日（PT）

## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

## Adobe Analytics の新機能

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| Adobe Analytics ランディングページの更新 | ワークスペースと Reports &amp; Analytics の共同ランディングページが更新され、操作性とナビゲーションのしやすさが改善しました。 [詳細情報](/help/analyze/landing.md) | 2022年4月20日（PT） |
| [!UICONTROL 次の項目] または [!UICONTROL 前の項目]ワークスペースパネル | [!UICONTROL 次または前の項目] パネルでは、選択したディメンション項目の後または前の項目を探索できます。例えば、特定の製品ページの次のページや前のページ、マーケティングチャネル、さらにデバイスタイプを確認する場合に使用します。このパネルは、任意のディメンジョンを参照でき、インサイトを得るために新たな実装を必要としないので、従来の次／前のレポート以上の役割を果たします。[詳細情報](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 2022年4月20日（PT） |
| [!UICONTROL ページの概要]ワークスペースパネル | [!UICONTROL ページの概要]パネルでは、選択したページの詳細な分析結果を提供します。従来の Reports &amp; Analytics における[!UICONTROL ページの概要]レポートと同様の詳細情報に加えて、さらに多くの情報を提供します。[詳細情報](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 2022年4月20日（PT） |
| 2.0 API 呼び出しの `x-proxy-global-company-id` ヘッダーの要件を削除 | この情報はエンドポイント URL の一部であるため、Adobe Analytics 2.0 API では `x-proxy-global-company-id` ヘッダーが不要になりました。このヘッダーを引き続き含めることはできますが、ヘッダーがない場合にエラーが表示されることはなくなりました。 | 2022年4月20日（PT） |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* データフィード UI から作成する際に、データフィードを保存した後に、開始日と終了日が自動的に変更されるというデータフィードの問題を修正しました。日付は 1 日ずつ更新されていました。（AN-281262）
* メールのリンクを使用してスケジュール済みプロジェクトを更新できない問題を修正しました。（AN-283622）
* Apple Safari と Microsoft Edge の最新リリースがアドビのブラウザータイプのルックアップテーブルで正しく識別されない問題を修正しました。[ブラウザーバージョンを更新する](/help/components/dimensions/browser.md)場合と同様に、ブラウザータイプのルックアップテーブルを更新すると、転送するデータのみが修正されます。ブラウザーバージョンのルックアップテーブルは 4月20日（PT）、ブラウザータイプのルックアップテーブルは 4月28日（PT）に更新しました。（AN-284872、AN-285753、AN-286257）

### Adobe Analytics におけるその他の修正点

AN-274486、AN-279258、AN-279995、AN-280918、AN-281423; AN-282084; AN-282435; AN-283508、AN-283517、AN-283706、AN-283762、AN-283921、AN-284195、AN-284663、AN-284573、AN-284721、AN-284790、AN-284867、AN-284870、AN-284872、AN-284884、AN-284914、AN-284930、AN-284933、AN-284967、AN-284970、AN-285187、AN-285328、AN-285337、AN-285375、AN-285447、AN-285724、AN-285753、AN-285761

## Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **クロスデバイス分析（CDA）の使用権限** | 2022年4月13日（PT） | **2022年5月1日（PT）**&#x200B;より、[CDA](/help/components/cda/overview.md) の新規実装は、1 顧客あたり最大 3 つのレポートスイート ID（RSID）に制限されます。 |
| **Experience Edge 経由で収集された A4T データを Adobe Analytics が処理する方法の変更** | 2022年3月31日（PT） | 2022年3月7日（PT）に、Analytics for Target（A4T）レポート用の Target コンテンツを含む Experience Edge からの呼び出しの処理方法を変更しました。3月7日（PT）以降、A4T レポートのコンテンツを含むすべてのヒットが変更され、ページビューイベントやリンクイベントとして扱われなくなります。**2022年3月31日（PT）**&#x200B;以降、ロジックはより選択的になり、標準のページビューイベントとクリックイベントは変更されません。今後、変更されるイベントは、A4T コンテンツのみを持つパーソナライゼーション専用の呼び出しのみになります。 |
| **特定の顧客でサポートされるブラウザー暗号化メソッドへのアップデート** | 2022年3月28日（PT） | アドビでは、2 種類の暗号セキュリティレベルを提供し、1st パーティのデータ収集におけるセキュリティに関するお客様の様々なニーズに対応しています。**2022年6月23日（PT）**&#x200B;に、セキュリティレベルが「高」に設定されているお客様に対して、暗号として知られる特定の HTTPS 暗号化アルゴリズムのサポートを削除します。このアクションは、一部の古いオペレーティングシステムでは最新の暗号化方法に対応していないので、Analytics にデータを送信できなくなったことを意味します。デフォルトの「標準」暗号セキュリティ設定を使用しているお客様には影響はありません。現在「高」の設定を使用しているすべてのお客様には、既にご連絡済みです。この変更による影響を受ける暗号の詳細なリストについては、こちらを参照してください。 |
| **古い予定レポートの一時停止** | 2022年4月12日（PT） | **2022年4月20日（PT）** より、アドビは作成日から 2 年を超える（2020年1月31日以前に作成された）予定レポートをすべて一時停止する予定です。レポートやデータは削除されません。2 年以上経過していると識別されたレポートのみ一時停止され、それ以降予定レポートは送信されません。詳細情報 |
| **2022年 ISO の地域のアップデート** | 2021年3月11日（PT） | **2022年6月10日（PT）**&#x200B;に、2022年の ISO 地域のアップデートを実施します。このリリース以降、マイナーな地域情報に関するアップデートが提供される可能性があります。 |
| **過去のスケジュール済み Report Builder タスクの一時停止** | 2022年4月12日（PT） | **2022年4月20日（PT）** より、アドビは、2 年以上前に作成されたすべてのスケジュール済み Report Builder タスクを一時停止する予定です。特に、この一時停止は、2020年1月31日（PT）より前に作成されたすべてのタスクに適用されます。タスク、ワークブックまたはデータは削除されません。ただし、2 年以上経過していると識別されたタスクは一時停止され、スケジュールされたタスクはそれ以上送信されません。詳細情報 |
| **従来の Analytics OAuth／JWT 統合向け許可リスト EOL 拡張機能の有効期限** | 2022年1月14日（PT） | **2022年5月25日（PT）**&#x200B;に、[Analytics 1.3 API、1.4 SOAP API および Legacy Analytics OAuth／JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 許可リスト拡張機能の有効期限が切れます。この拡張機能は、従来の [!DNL Adobe Analytics] OAuth／JWT 認証情報を使用している顧客に、クライアント統合を[アドビ IMS 認証報](https://developer.adobe.com/console)に移行するための時間的余裕を提供するために提供されました。この有効期限は、必要な IMS 移行を完了していない [!DNL Adobe Analytics Livestream] および [!DNL Adobe Campaign] のお客様が対象となります（ただし、これに限定されるものではありません）。現在、許可リスト拡張機能により従来の [!DNL Analytics] OAuth／JWT 認証情報を使用しているお客様は、2022年5月25日（PT）までに IMS 認証情報への移行が完了しない場合、アドビサービスへのアクセスができなくなる可能性があります。Livestream のお客様は、クライアントアプリケーションを IMS 認証情報に移行する関する以下の [説明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) をご覧いただけます。[!DNL Campaign] のお客様は、[!DNL Campaign] の最新バージョンへのアップグレードについて、アドビアカウントチームにお問い合わせください。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日（PT） | **2023年12月31日**（PT）をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
