---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9c6da2c1ed5bc2c016da16a5bb821f0064e1ae4f
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 48%

---

# 最新のAdobe Analytics リリースノート（2025 年 5 月リリース）

**最終更新日**：2025年5月14日（PT）

これらのリリースノートは、2025 年 4 月 xx 日から 6 月 18 日までのリリース期間を対象としています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspaceの左パネルが開かなくなり、マウスポインターを置くと閉じる** | Analysis Workspaceの左側のパネルを使用すると、コンポーネント、パネル、ビジュアライゼーションなどをプロジェクトに追加できます。 左端のいずれかのアイコンにマウスポインターを置いて、一時的に左側のパネルを開くオプションは使用できなくなりました。 代わりに、これらのアイコンのいずれかをクリックしてパネルを開いたままにし、同じアイコンをクリックして閉じるだけです。 |  | 2025年5月29日（PT） |


## Adobe Analytics の修正点

**アラート**:AN-378351
**Analysis Workspace**: AN-363521; AN-367366; AN-373575; AN-374238; AN-374295; AN-374382; AN-376938; AN-377176; AN-377467; AN-377942
**資産譲渡**: AN-373381
**分類**: AN-373166; AN-373479; AN-376074; AN-377337; AN-377505
**コンポーネント**:AN-314468
**データフィード**: AN-370241; AN-375267; AN-376940
**データソース**: AN-375259
**Data Warehouse**: AN-370415; AN-372090;
**Platform**: AN-365681; AN-372306; AN-372616;
**リアルタイムレポート**:AN-365681
**Report Builder**: AN-371395
**セグメント化**: AN-373576; AN-375858
**仮想レポートスイート**:AN-377948; AN-377952
**Vista ルール**: AN-373292

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **Analysis Workspaceの左パネルが開かなくなり、マウスポインターを置くと閉じる** | Analysis Workspaceの左側のパネルを使用すると、コンポーネント、パネル、ビジュアライゼーションなどをプロジェクトに追加できます。 左端のいずれかのアイコンにマウスポインターを置いて、一時的に左側のパネルを開くオプションは使用できなくなりました。 代わりに、これらのアイコンのいずれかをクリックしてパネルを開いたままにし、同じアイコンをクリックして閉じるだけです。 |  | 2025年5月29日（PT） |


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **従来のドメインまたは従来の SSO を使用したアクセス** | 2025年4月10日（PT） | Adobeでは、セキュリティを強化しログインエクスペリエンスを効率化するために、ユーザーのAdobe Analyticsへのアクセス方法を更新する予定です。 この取り組みの一環として、従来のドメインまたは `my.omniture.com` を含む従来の SSO を使用したアクセスは、**2026 年 1 月 2 日** に完全に廃止されます。 この期限を過ぎると、従来のログイン資格情報と従来の SSO は機能しなくなります。 すべてのユーザーは、Adobe Experience Cloud ID を使用して `experience.adobe.com` 経由でログインする必要があります。 Experience Cloud ID に関するサポートが必要な場合は、組織のAdobe Analytics管理者または [Adobe カスタマーケア ](https://helpx.adobe.com/contact.html) にお問い合わせください。 |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2025年1月17日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年6月30日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Adobe Analytics API（バージョン 1.4）の EOL（サポート終了）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。


## 関連リソース

* [2025年の以前のリリースノート](/help/release-notes/2025.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
