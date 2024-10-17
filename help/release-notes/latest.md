---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 21cf08af6922aaaed2f0b3e4c0fcd701b54473ee
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 92%

---

# 現在の Adobe Analytics リリースノート（2024年10月）

**最終更新日**：2024年10月17日（PT）

このリリースノートは、2024年10月2日～2024年10月22日（PT）のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| Adobe Analyticsの新しいReport Builder | 新しいReport Builderアプリケーションは、パフォーマンスの向上、合理化されたユーザーインターフェイス、2.0 API のサポート、Mac、Windows および web ブラウザー上のMicrosoft Excel のサポートなど、Adobe Analyticsに更新された機能を提供します。 [詳細情報](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) |  | 2024年10月16日（PT） |

## Adobe Analytics の修正点

Analysis Workspace：AN-343611、AN-355870、AN-357100、AN-358364、AN-358756、AN-359269
Analytics モバイルアプリ：AN-354085
分類：AN-353074、AN-357533、AN-358308、AN-358350、AN-358732、AN-358925、AN-359249
クロスデバイス分析：AN-357968
データフィード：AN-358489、AN-358542
データウェアハウス：AN-352181、AN-356701、AN-356802、AN-356804、AN-359162

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **自動的にマッピングされる追加の実装詳細 XDM フィールド** | 2024年9月11日（PT） | Adobe Experience Platform Edge Network を使用してデータを Adobe Analytics に送信する際に、XDM フィールド `xdm.implementationdetails.name` と `xdm.implementationdetails.environment` は、常にコンテキストデータ変数 `c.a.x.implementationdetails.name` と `c.a.x.implementationdetails.environment` にマッピングされるようになりました。以前は、一部のシナリオで、これらの値が入力されませんでした。これらの値が使用可能になるように、関連する処理ルールを調整してください。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe Analytics API（バージョン 1.4）の EOL（サポート終了）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。 Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2024年の以前のリリースノート](/help/release-notes/2024.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションアドオンのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
