---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c101a98e2d2d73fecc39054289f516411d7d529a
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 39%

---

# 最新のAdobe Analyticsリリースノート（2022 年 4 月）

**最終更新日**:2022 年 4 月 20 日

* 2022 年 3 月のリリースノートについては、 [ここ](/help/release-notes/2022.md).

* Customer Journey Analyticsリリースノートについては、 [ここ](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja).

* Media Analytics リリースノートについては、 [ここ](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en).

* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html) の最新のリリース更新について説明します。Experience League に関する最新のセルフヘルプドキュメント、チュートリアル、コースを入手します。


| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| Adobe Analyticsランディングページの更新 | 共同の Workspace/Reports &amp; Analytics ランディングページが更新され、操作性とナビゲーションが簡単になりました。 [詳細情報](/help/analyze/landing.md) | 2022 年 4 月 21 日 |
| [!UICONTROL 次の項目] または [!UICONTROL 前の項目] Workspace パネル | この [!UICONTROL 次または前の項目] パネルを使用すると、選択したディメンション項目に従う項目、または選択したディメンション項目の前に続く項目を調べることができます。 例えば、特定の製品ページ、マーケティングチャネル、デバイスタイプまで、次のページや前のページを表示したい場合に使用します。 このパネルは、任意のディメンションを参照でき、インサイトを得るために新しい実装は必要ないので、従来の次へ/以前のレポートにとどまりません。 | 2022 年 4 月 21 日 |
| [!UICONTROL ページサマリ] Workspace パネル | この [!UICONTROL ページサマリ] パネルでは、任意のページに関する詳細な分析を行うことができます。 従来の Reports &amp; Analytics と同じ詳細が提供されます [!UICONTROL ページサマリ] レポートに加えて、さらに多くの情報が含まれます。 | 2022 年 4 月 21 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* データフィード UI から作成する際に、データフィードを保存した後に、開始日と終了日が自動的に変更されるというデータフィードの問題を修正しました。 日付は 1 日ずつ更新されていました。 （AN-281262）

* 電子メールのリンクを使用してスケジュール済みプロジェクトを更新できない問題を修正しました。 （AN-283622）

### Adobe Analytics におけるその他の修正点

AN-274486;AN-279258;AN-279995;AN-280918;AN-281423;AN-282084;AN-282435;AN-283508;AN-283517;AN-283706;AN-283762;AN-283921;AN-284195;AN-284663;AN-284573;AN-284721;AN-284790;AN-284867;AN-284870;AN-284872;AN-284884;AN-284914;AN-284930;AN-284933;AN-284967;AN-284970;AN-285187;AN-285328;AN-285337;AN-285375;AN-285447;AN-285724;AN-285753;AN-285761;

## Adobe Analytics管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **クロスデバイス分析 (CDA) の使用権限** | 2022 年 4 月 14 日 | 有効 **2022 年 5 月 2 日**、新しい実装 [CDA](/help/components/cda/overview.md) は、1 人の顧客につき最大 3 つのレポートスイート ID(RSID) に制限されます。 |
| **Experience Edge で収集された A4T データをAdobe Analyticsが処理する方法の変更** | 2022 年 3 月 31 日 | 2022 年 3 月 7 日に、Analytics for Target(A4T) レポート用の Target コンテンツを含む Experience Edge からの呼び出しの処理方法を変更しました。 3 月 7 日以降、A4T レポートのコンテンツを含むすべてのヒットが変更され、ページビューイベントやリンクイベントとして扱われなくなりました。 開始中 **2022 年 3 月 31 日**&#x200B;を選択する場合、ロジックをより選択的に変更し、標準のページビューイベントとクリックイベントを変更しないようにしました。 今後、変更されるイベントは、A4T コンテンツのみを持つパーソナライゼーションのみの呼び出しになります。 |
| **特定の顧客でサポートされるブラウザー暗号化方法に対する更新** | 2022 年 3 月 29 日 | Adobeは、ファーストパーティのデータ収集に関するセキュリティに関する様々なお客様のニーズに応える 2 種類の暗号セキュリティレベルを提供します。 オン **2022 年 6 月 24 日** セキュリティレベルを「高」に設定したお客様に対して、暗号と呼ばれる特定の HTTPS 暗号化アルゴリズムのサポートを削除します。 つまり、一部の古いオペレーティングシステムでは、最新の暗号化方法をサポートしていないので、Analytics にデータを送信できなくなります。 デフォルトの「標準」暗号セキュリティ設定を使用しているお客様は影響を受けません。 現在「高」設定を使用しているすべてのお客様は、既に直接連絡済みです。 この変更の影響を受ける暗号の詳細なリストは、こちらを参照してください。 |
| **古い予定レポートの一時停止** | 2022 年 4 月 13 日 | 有効 **2022 年 4 月 21 日**&#x200B;のAdobeは、作成日が 2 年を超える（2020 年 1 月 31 日以前に作成）予定レポートをすべて一時停止します。 レポートやデータは削除されません。 2 年を超えたレポートのみが一時停止され、追加の予定レポートは送信されません。 詳細情報 |
| **2022 年 ISO 地域の更新** | 2021 年 3 月 11 日（PT） | Adobeは、 **2022 年 6 月 11 日**. このリリース以降、マイナーな地域情報の更新がおこなわれることを想定しています。 |
| **以前にスケジュールされた Report Builder タスクの一時停止** | 2022 年 4 月 13 日 | 有効 **2022 年 4 月 21 日**&#x200B;のAdobeは、2 年以上前に作成された、スケジュールされたすべてのReport Builderタスクを一時停止する予定です。 特に、この一時停止は、2020年1月31日（PT）より前に作成されたすべてのタスクに適用されます。タスク、ワークブックまたはデータは削除されません。ただし、2 年以上経過していると識別されたタスクは一時停止され、スケジュールされたタスクはそれ以上送信されません。詳細情報 |
| **従来の Analytics OAuth／JWT 統合の許可リスト EOL 拡張機能の有効期限** | 2022年1月14日（PT） | **2022年5月25日（PT）**&#x200B;に、[Analytics 1.3 API、1.4 SOAP API および Legacy Analytics OAuth／JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 許可リスト拡張機能の有効期限が切れます。この拡張機能は、従来の [!DNL Adobe Analytics] OAuth／JWT 認証情報を使用している顧客に、クライアント統合を[アドビ IMS 認証報](https://developer.adobe.com/console)に移行するための時間的余裕を提供するために提供されました。この有効期限は、必要な IMS 移行を完了していない [!DNL Adobe Analytics Livestream] および [!DNL Adobe Campaign] のお客様に影響します（ただし、これに限定されるものではありません）。現在、許可リスト拡張機能により従来の [!DNL Analytics] OAuth／JWT 認証情報を使用しているお客様は、2022年5月25日（PT）までに IMS 認証情報への移行が完了しない場合、アドビサービスへのアクセスができなくなる可能性があります。Livestream のお客様は、クライアントアプリケーションを IMS 認証情報に移行する関する以下の [説明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) をご覧いただけます。[!DNL Campaign] のお客様は、[!DNL Campaign] の最新バージョンへのアップグレードについて、アドビアカウントチームにお問い合わせください。 |
| **[!DNL Reports & Analytics]** のサポート終了  | 2022年1月4日（PT） | **2023年12月31日**（PT）をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
