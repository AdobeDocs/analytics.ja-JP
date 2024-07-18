---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: cb0eab15dac6d679e9f912010045e6be2e47df4a
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 46%

---

# Adobe Analytics の最新リリースノート（2024年7月）

**最終更新日**：2024年7月17日（PT）

これらのリリースノートは、2024 年 7 月 17 日（PT）から 2024 年 8 月 17 日（PT）までのリリース期間を対象としています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **リンクトラッキングの Web SDK の改善** | Web SDK の最新バージョンでは、リンクトラッキングに関するいくつかの注目すべき改善点が利用可能です。これは、Activity Mapに直接役立ちます。 これらの新機能は、Web SDK JavaScript ライブラリと Web SDK タグ拡張機能の両方で利用できます。<ul><li>イベントのグループ化：訪問者が内部リンクをクリックすると、リンクトラッキング用に別のイベントコールをトリガーする代わりに、次のページのイベントデータをグループ化するように選択できます。 この改善により、Web SDK が契約上の制限に対して使用するイベントの数が減ります。</li><li>フィルタークリックのプロパティ：`OnBeforeLinkClickSend` に代わる新しいコールバック。 このコールバックを使用して、リンク関連のデータをAdobeに送信する前にフィルタリングまたは難読化できます。</li></ul><p>詳しくは、Web SDK ユーザーガイドの [clickCollection](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollection) を参照してください。</p> | オープンBetaは 2024 年 7 月 10 日（PT）に開始されました | 未定 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* ユーザーが Analytics UI にログインできない問題を修正しました（AN-352953）
* ユーザーが Analytics モバイルアプリにログインできない問題を修正しました（AN-352463）
* プロジェクトをPDFとしてダウンロードできない問題を修正しました（AN-352680）
* 分類がインポートされない問題を修正しました（AN-352178）

### Analytics のその他の修正

AN-352905; AN-352902; AN-352693; AN-352659; AN-352619;
AN-352577; AN-352575; AN-352572; AN-352571; AN-352549; AN-352501; AN-352499; AN-352478; AN-352466; AN-352437; AN-352378; AN-352341; AN-352318; AN-352297; AN-352272; AN-352267; AN-352263; AN-352088; AN-352019 352018 351978 351908 351809 351750 351689 351624 351564 351524 351507 351416 351414 351405 351299 351283 351231 350710 349912 349786 348300 348061 347865 347676 347478 343611 343114 334124; AN-352355; AN-COUNTERN; AN-COUNTERN; AN-SMT; AN AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN-AN

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **保存された`cust_visids`** の有効期限は 13 か月 | 2024年5月22日（PT） | Analytics のヒット処理エンジンの次回リリース（**2024年7月を予定**）では、保存された `cust_visids` に 13 か月の有効期限が適用されます。レポートスイートで「訪問者のステッチを有効にする」が有効になっている場合、この設定は、ヒット時の `cust_visid` がない `visid_high/visid_low value` で、`cust_visid` を見つける際に使用します。 現在、`visid_high/visid_low` に対する `cust_visid` のマッピングに有効期限はありません。 このリリースでは、`visid_high/visid_low` にヒット時の `cust_visid` が設定されてから 13 か月以上が経過すると、マッピングが期限切れになります。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe Analytics API （バージョン 1.4）のサポート終了** | 2024年7月17日（PT） | **2026 年 8 月 12 日（PT**、次の Analytics レガシー API サービスの提供が終了し、サービスが停止されます。また、これらのサービスを使用して現在構築されている統合は機能を停止します。<ul><li>Adobe Analytics API （バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API （バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要がありますが、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) で OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問とその他のガイダンスへの回答については ](/help/admin/c-admin-api/c-admin-14-api-eol.md)[Adobe Analytics 1.4 API の EOL （提供終了）に関する FAQ} を参照してください。</p> |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。 Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2024年の以前のリリースノート](/help/release-notes/2024.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションアドオンのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
