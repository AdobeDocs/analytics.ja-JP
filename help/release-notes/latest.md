---
title: Analytics の最新リリースノート
description: 現在の Adobe Analytics のリリースノートを見る.
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 511e3f4c621137d76b40fcc04ea849a0bba9e3fa
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 59%

---

# 最新のAdobe Analyticsリリースノート（2022 年 2 月）

>[!IMPORTANT]
>
>これらのリリースノートには、変更される可能性のあるリリース前の情報が含まれています。

**最終更新日**:2022 年 2 月 11 日

[Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html) の最新のリリース更新について説明します。Experience League に関する最新のセルフヘルプドキュメント、チュートリアル、コースを入手します。

## Adobe Analytics の新機能 {#aa-features}

| 機能 | 説明 | [ターゲット日](releases.md) |
| ----------- | ---------- | ------- |
| モバイルスコアカードプロジェクトのプレビューモード | Analytics ダッシュボードアプリでのモバイルスコアカードの表示方法を、スコアカードビルダーから直接開始します。 プレビューモードを使用すると、ユーザーはアプリ内と同じ方法でフィルターやグラフを操作でき、スコアカードを保存および共有する前にエクスペリエンスをプレビューできます。 また、デバイスピッカーをプレビューモードで使用して、様々なデバイスでのスコアカードの表示を確認することもできます。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=en#preview) | 2022年2月16日（PT） |
| API プロジェクトエンドポイント | API を使用して、Analysis Workspaceプロジェクトを追加、編集または削除します。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | 2022 年 2 月 2 日 |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

* の [!UICONTROL サーバーコールの使用状況]. （AN-279134、AN-279878、AN-280802、AN-279097、AN-191284、AN-269720）
* Data Warehouseが空の.csv ファイルを書き出す問題を修正しました。 （AN-280291）
* 最近のセグメントのオーディエンス名が入力されない問題を修正しました。 （AN-279715）
* レポート時間が遅かった問題を修正しました。 （AN-280055）
* 分類で、すべてのディメンション項目が分類されない問題を修正しました。 （AN-280031）

### Adobe Analytics のその他の修正点

AN-268093、AN-273820、AN-274435、AN-274904、AN-275356、AN-276160、AN-276258、AN-276705、AN-277051、AN-277957、AN-278693、AN-AN-279046、AN-AN-AN-AN-278882AN AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-ANANANANANANANANANANANANANANANANANAN-ANAN-ANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANANAN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN

## [!DNL Analytics] 管理者向けの重要な注意事項 

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| 従来の Analytics OAuth／JWT 統合の許可リスト EOL 拡張機能の有効期限 | 2022年1月14日（PT） | **2022年5月25日（PT）**&#x200B;に、[Analytics 1.3 API、1.4 SOAP API および Legacy Analytics OAuth／JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) 許可リスト拡張機能の有効期限が切れます。この拡張機能は、従来の [!DNL Adobe Analytics] OAuth／JWT 認証情報を使用している顧客に、クライアント統合を[アドビ IMS 認証報](https://developer.adobe.com/console)に移行するための時間的余裕を提供するために提供されました。この有効期限は、必要な IMS 移行を完了していない [!DNL Adobe Analytics Livestream] および [!DNL Adobe Campaign] のお客様に影響します（ただし、これに限定されるものではありません）。現在、許可リスト拡張機能により従来の [!DNL Analytics] OAuth／JWT 認証情報を使用しているお客様は、2022年5月25日（PT）までに IMS 認証情報への移行が完了しない場合、アドビサービスへのアクセスができなくなる可能性があります。Livestream のお客様は、クライアントアプリケーションを IMS 認証情報に移行する関する以下の [説明](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) をご覧いただけます。[!DNL Campaign] のお客様は、[!DNL Campaign] の最新バージョンへのアップグレードについて、アドビアカウントチームにお問い合わせください。 |
| [!DNL Reports & Analytics] のサポート終了  | 2022年1月4日（PT） | **2023 年12月31日**（PT）をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |
| セキュアファイル転送プロトコル（SFTP）サービスのアップグレード | 2022年1月13日（PT） | **2022年5月2日（PT）**、[!DNL Adobe Analytics] はファイル転送のセキュリティを強化するために、Secure File Transfer Protocol（SFTP）サービスをアップグレードします。この変更により、一部の SFTP クライアント設定はサポートされなくなります。また、**2022年3月1日（PT）** までに利用可能となる接続オプションをいくつか追加します。これは、SFTP を使用してAdobe Analyticsに送信された、またはから取得されたデータにのみ影響します。 FTP プロトコルに影響はありません。 サービスの中断を避けるために、SFTP クライアント（コード、ツール、サービス）が、詳細に説明された変更に従っていることを確認してください [ここ](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=ja). |

## AppMeasurement {#appm}

AppMeasurement リリース（バージョン 2.22.4）の最新のアップデートについては、[JavaScript リリースノートの AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics]  リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
