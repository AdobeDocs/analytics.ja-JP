---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f3b62096b481bda29946ccb091771157dce41d9d
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 46%

---

# 最新のAdobe Analyticsリリースノート（2022 年 3 月）

**最終更新日：2022 年 23 月 4 日**

>[!IMPORTANT]
>
>以下の内容は、リリース前の情報に関するもので、変更される可能性があります。

* 2022 年 2 月のリリースノートについては、 [ここ](/help/release-notes/2022.md).
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html) の最新のリリース更新について説明します。Experience League に関する最新のセルフヘルプドキュメント、チュートリアル、コースを入手します。

## Adobe Analytics の新機能 {#aa-features}

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| Workspace の注釈 | Workspace の注釈を使用すると、コンテキストデータのニュアンスやインサイトを組織に効果的に伝えることができます。 [詳細情報](/help/analyze/analysis-workspace/components/annotations/overview.md) | 段階的な展開は 2022 年 3 月 23 日から開始します |
| Adobe Analyticsランディングページの更新 | 共同の Workspace/Reports &amp; Analytics ランディングページが更新され、操作性とナビゲーションが簡単になりました。 [詳細情報](/help/analyze/landing.md) | 2022 年 4 月 2 日 |
| [!UICONTROL 次の項目] または [!UICONTROL 前の項目] Workspace パネル | この [!UICONTROL 次または前の項目] パネルを使用すると、選択したディメンション項目に従う項目、または選択したディメンション項目の前に続く項目を調べることができます。 例えば、特定の製品ページ、マーケティングチャネル、デバイスタイプまで、次のページや前のページを表示したい場合に使用します。 このパネルは、任意のディメンションを参照でき、インサイトを得るために新しい実装は必要ないので、従来の次へ/以前のレポートにとどまりません。 | 2022 年 4 月 2 日 |
| [!UICONTROL ページサマリ] Workspace パネル | この [!UICONTROL ページサマリ] パネルでは、任意のページに関する詳細な分析を行うことができます。 従来の Reports &amp; Analytics と同じ詳細が提供されます [!UICONTROL ページサマリ] レポートに加えて、さらに多くの情報が含まれます。 | 2022 年 4 月 2 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* Activity Mapにアクセスしようとするとエラーが発生する問題を修正しました。 （AN-267177）
* ユーザーアセットの転送が失敗していた問題を修正しました。 （AN-279813）
* A4T Workspace パネルの問題を修正しました。 （AN-281594、AN-282418）
* 一部のユーザーがAdobe Analyticsにアクセスできない問題を修正しました。 （AN-282776）
* 一部の新しく作成されたレポートスイートでデータが収集されない問題を修正しました。 （AN-283114、AN-283311）
* オペレーティングシステムディメンションを使用して Win11 を検出できない問題を修正しました。 (AN-275569、AN-275727、AN-280335)
* データフィード電子メールが正しく送信されない問題を修正しました。 （AN-280255、AN-282051）


### Adobe Analytics におけるその他の修正点

AN-256929;AN-270937;AN-272158;AN-275130;AN-277830;AN-278635;AN-279066;AN-279683;AN-279899;AN-280504;AN-280617;AN-280663;AN-281423;AN-281523;AN-281608;AN-281671;AN-281963;AN-282027;AN-282218;AN-282593;AN-282605;AN-282632;AN-282654;AN-282694;AN-282744;AN-282756;AN-282804;AN-282838;AN-282862;AN-282903;AN-282937;AN-282892;AN-283315;AN-283338;AN-283388;AN-283417;AN-283474;AN-283511;AN-283691、AN-283895、AN-283943;AN-283957;AN-284030;AN-284100;AN-284142;AN-284162

## Adobe Analytics管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| 古い予定レポートの一時停止 | 2022 年 3 月 12 日 | 有効 **2022 年 4 月 16 日**&#x200B;のAdobeは、作成日が 2 年を超える（2020 年 1 月 31 日以前に作成）予定レポートをすべて一時停止します。 レポートやデータは削除されません。 2 年を超えたレポートのみが一時停止され、追加の予定レポートは送信されません。 [詳細情報](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| 2022 年 ISO 地域の更新 | 2021年3月11日（PT） | Adobeは、 **2022 年 6 月 11 日**. このリリース以降、マイナーアップデートが提供される可能性があります。 |
| Experience Edge 経由で収集された A4T データを Analytics が処理する方法の変更 | 2022 年 2 月 25 日（PT） | オン **2022 年 3 月 8 日**&#x200B;を使用する場合、Experience Edge を使用してAdobe Analyticsに送信される Target 関連のデータの処理方法を変更しました。 Adobe Experience Platform Web SDK を Analytics および Target で使用する場合、一部のパーソナライゼーションイベントが [!DNL Adobe Analytics] as [!UICONTROL ページビュー数]. これにより、ページビュー数と追加のサーバー呼び出しが水増しされました。 この変更により、Analytics コンテンツを持たないパーソナライゼーション呼び出しは無視されます。 Personalizationの A4T データ呼び出しは、A4T データを記録しますが、課金対象のサーバーコールとして記録されず、ページビュー数やリンクイベント指標にも影響しません。 |
| 過去の予定Report Builderタスクの一時停止 | 2022 年 2 月 24 日（PT） | **2022 年 4 月 15 日から有効**&#x200B;のAdobeは、2 年以上前に作成された、スケジュールされたすべてのReport Builderタスクを一時停止する予定です。 特に、この一時停止は、2020 年 1 月 31 日より前に作成されたすべてのタスクに適用されます。 タスク、ワークブック、またはデータは削除されません。 ただし、2 年を超えたタスクは一時停止され、追加のスケジュール済みタスクは送信されません。 [詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| 従来の Analytics OAuth／JWT 統合の許可リスト EOL 拡張機能の有効期限 | 2022年1月14日（PT） | **2022年5月25日（PT）**&#x200B;に、[Analytics 1.3 API、1.4 SOAP API および Legacy Analytics OAuth／JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 許可リスト拡張機能の有効期限が切れます。この拡張機能は、従来の [!DNL Adobe Analytics] OAuth／JWT 認証情報を使用している顧客に、クライアント統合を[アドビ IMS 認証報](https://developer.adobe.com/console)に移行するための時間的余裕を提供するために提供されました。この有効期限は、必要な IMS 移行を完了していない [!DNL Adobe Analytics Livestream] および [!DNL Adobe Campaign] のお客様に影響します（ただし、これに限定されるものではありません）。現在、許可リスト拡張機能により従来の [!DNL Analytics] OAuth／JWT 認証情報を使用しているお客様は、2022年5月25日（PT）までに IMS 認証情報への移行が完了しない場合、アドビサービスへのアクセスができなくなる可能性があります。Livestream のお客様は、クライアントアプリケーションを IMS 認証情報に移行する関する以下の [説明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) をご覧いただけます。[!DNL Campaign] のお客様は、[!DNL Campaign] の最新バージョンへのアップグレードについて、アドビアカウントチームにお問い合わせください。 |
| セキュアファイル転送プロトコル（SFTP）サービスのアップグレード | 2022 年 3 月 4 日 | **2022年5月15日（PT）**、[!DNL Adobe Analytics] はファイル転送のセキュリティを強化するために、Secure File Transfer Protocol（SFTP）サービスをアップグレードします。この変更により、一部の SFTP クライアント設定はサポートされなくなります。また、**2022年3月1日（PT）** までに利用可能となる接続オプションをいくつか追加します。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |
| [!DNL Reports & Analytics] のサポート終了  | 2022年1月4日（PT） | **2023年12月31日**（PT）をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

## AppMeasurement {#appm}

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
