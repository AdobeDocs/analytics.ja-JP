---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b65da2936efc499df2afbe7c6195f3989ea1a832
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 66%

---

# 最新のAdobe Analytics リリースノート（2025 年 2 月リリース）

**最終更新日**：2024年2月19日（PT）

これらのリリースノートは、2025 年 2 月 11 日（PT）から 3 月中旬のリリース期間に対応しています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **トランザクション ID の保持期間** | トランザクション ID の保持期間は 90 日で、25 か月に延長されます。 `transactionID` 変数はトランザクションを一意に識別し、ヒットがデータソースを介してアップロードされたデータに結び付けられるようにします。詳しくは [ こちら ](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/transactionid) および [ こちら ](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/transactionid) を参照してください。 |  | 2025年2月20日（PT） |
| **データフィード API リファレンス** | データフィード API の [ 参照 ](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) が利用できるようになりました。 |  | 2025年1月30日（PT） |
| **Livestream API - クライアント実装** | Livestream クライアント実装を使用して、Livestream データを使用します。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | 2025年2月18日（PT） |
| **Classifications API の更新** | サーバーから個々の分類フィールドまたはキーを削除できるようになりました。 これにより、DELETEを使用して分類データセット全体を削除する代わりに使用できます。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/) |  | 2025年2月18日（PT） |


## Adobe Analytics の修正点

**Analysis Workspace**: AN-359974; AN-366212; AN-368460
**分類**: AN-367186; AN-367328; AN-368548
**コンポーネントの移行**: AN-364529; AN-366398; AN-367509;
**データフィード**: AN-365685; AN-366745; AN-367256; AN-367349; AN-368363
**Data Warehouse**: AN-368178; AN-368331;
**モバイルアプリ**:AN-367137
**Platform**: AN-351924; AN-365540; AN-365866; AN-366898; AN-367856; AN-367933
**Report Builder**: AN-366456; AN-366655;
**仮想レポートスイート**:AN-367411
**VISTA ルール**: AN-365331

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **Campaign 以外のお客様は、トリガーにアクセスできなくなる** | 2023年10月16日（PT） | 2025 年 1 月 30 日（PT）、Adobe Campaign ライセンスのないAdobe Analytics ユーザーは、[トリガー](https://experienceleague.adobe.com/ja/docs/core-services/interface/services/triggers) を設定して使用する機能にアクセスできなくなります。 お客様は、Campaign を購入、またはトリガーの使用を中止するか、トリガー機能を提供する他の Adobe ツールを検討する必要があります。 |

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2025年1月17日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年6月30日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Adobe Analytics API（バージョン 1.4）の EOL（サポート終了）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2024年の以前のリリースノート](/help/release-notes/2024.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
