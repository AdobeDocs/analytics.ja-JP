---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 945a495dfea2f4564d39457528a185b6b75c7d17
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 76%

---

# 現在の Adobe Analytics リリースノート（2022年2月）

**最終更新日**:2022 年 3 月 4 日

[Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html) の最新のリリース更新について説明します。Experience League に関する最新のセルフヘルプドキュメント、チュートリアル、コースを入手します。

## Adobe Analytics の新機能 {#aa-features}

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| モバイルスコアカードプロジェクトのプレビューモード | Analytics ダッシュボードアプリでモバイルスコアカードがどのように表示されるかのプレビューを、スコアカードビルダーから直接開始します。プレビューモードを使用すると、ユーザーはアプリ内と同じ方法でフィルターやグラフを操作でき、スコアカードを保存および共有する前にエクスペリエンスをプレビューできます。また、デバイスピッカーをプレビューモードで使用して、様々なデバイスでのスコアカードの表示を確認することもできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=ja#preview) | 2022年2月16日（PT） |
| API プロジェクトエンドポイント | API を使用して、Analysis Workspaceプロジェクトを追加、編集または削除します。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | 2022 年 2 月 2 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* [!UICONTROL サーバーコールの使用状況]に関するいくつかの問題を修正しました。（AN-279134、AN-279878、AN-280802、AN-279097、AN-191284、AN-269720）
* Data Warehouse が空の .csv ファイルを書き出す問題を修正しました。（AN-280291）
* 最近のセグメントのオーディエンス名が入力されない問題を修正しました。 （AN-279715）
* レポート時間が遅い問題を修正しました。（AN-280055）
* すべてのディメンション項目が分類されない問題を修正しました。（AN-280031）

### Adobe Analytics におけるその他の修正点

AN-268093、AN-273820、AN-274435、AN-274904、AN-275356、AN-275947、AN-276160、AN-276258、AN-276705、AN-277051、AN-277957、AN-278693、AN-278882、AN-279000、AN-279046、AN-279362、AN-279460、AN-279488、AN-279554、AN-279572、AN-279663、AN-279755、AN-279825、AN-280002、AN-280013、AN-280019、AN-280033、AN-280086、AN-280232、AN-280264、AN-280288、AN-280342、AN-280347、AN-280360、AN-280370、AN-280724、AN-280830、AN-280941、AN-281353、AN-281424、AN-281533

## [!DNL Analytics] 管理者向けの重要な注意事項 

**更新日： 2022 年 3 月 4 日**

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| Experience Edge 経由で収集された A4T データを Analytics が処理する方法の変更 | 2022年2月25日（PT） | オン **2022 年 3 月 8 日**&#x200B;を使用する場合、Experience Edge を介してAdobe Analyticsに送信される Target 関連のデータの処理方法を変更します。 Adobe Experience Platform Web SDK を Analytics および Target で使用する場合、一部のパーソナライゼーションイベントが [!DNL Adobe Analytics] as [!UICONTROL ページビュー数]. これにより、ページビュー数と追加のサーバー呼び出しが水増しされました。 この変更により、Analytics コンテンツを持たないパーソナライゼーション呼び出しは無視されます。 A4T データを使用したパーソナライゼーション呼び出しは、A4T データを記録しますが、課金対象のサーバー呼び出しとして記録されず、ページビュー数やリンクイベント指標にも影響しません。 |
| 過去の予定Report Builderタスクの一時停止 | 2022年2月24日（PT） | **2022 年 4 月 15 日から有効**&#x200B;のAdobeは、2 年以上前に作成された、スケジュールされたすべてのReport Builderタスクを一時停止する予定です。 特に、この一時停止は、2020 年 1 月 31 日より前に作成されたすべてのタスクに適用されます。 タスク、ワークブック、またはデータは削除されません。 ただし、2 年を超えたタスクは一時停止され、追加のスケジュール済みタスクは送信されません。 [詳細情報](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| 従来の Analytics OAuth／JWT 統合の許可リスト EOL 拡張機能の有効期限 | 2022年1月14日（PT） | **2022年5月25日（PT）**&#x200B;に、[Analytics 1.3 API、1.4 SOAP API および Legacy Analytics OAuth／JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 許可リスト拡張機能の有効期限が切れます。この拡張機能は、従来の [!DNL Adobe Analytics] OAuth／JWT 認証情報を使用している顧客に、クライアント統合を[アドビ IMS 認証報](https://developer.adobe.com/console)に移行するための時間的余裕を提供するために提供されました。この有効期限は、必要な IMS 移行を完了していない [!DNL Adobe Analytics Livestream] および [!DNL Adobe Campaign] のお客様に影響します（ただし、これに限定されるものではありません）。現在、許可リスト拡張機能により従来の [!DNL Analytics] OAuth／JWT 認証情報を使用しているお客様は、2022年5月25日（PT）までに IMS 認証情報への移行が完了しない場合、アドビサービスへのアクセスができなくなる可能性があります。Livestream のお客様は、クライアントアプリケーションを IMS 認証情報に移行する関する以下の [説明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) をご覧いただけます。[!DNL Campaign] のお客様は、[!DNL Campaign] の最新バージョンへのアップグレードについて、アドビアカウントチームにお問い合わせください。 |
| [!DNL Reports & Analytics] のサポート終了  | 2022年1月4日（PT） | **2023年12月31日**（PT）をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |
| セキュアファイル転送プロトコル（SFTP）サービスのアップグレード | 2022 年 3 月 4 日 | **2022年5月15日（PT）**、[!DNL Adobe Analytics] はファイル転送のセキュリティを強化するために、Secure File Transfer Protocol（SFTP）サービスをアップグレードします。この変更により、一部の SFTP クライアント設定はサポートされなくなります。また、**2022年3月1日（PT）** までに利用可能となる接続オプションをいくつか追加します。これは、SFTP を使用して Adobe Analytics に送信された、または Adobe Analytics から取得されたデータにのみ影響します。FTP プロトコルは影響を受けません。サービスの中断を避けるために、お使いの SFTP クライアント（コード、ツール、サービス）が、[ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja)で詳細に説明された変更に従っていることを確認してください。 |

## AppMeasurement {#appm}

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
