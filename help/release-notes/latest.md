---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 88d60f38d5a87bacb755a49dc884700ac66039ce
workflow-type: ht
source-wordcount: '725'
ht-degree: 100%

---

# 最新の Adobe Analytics リリースノート（2024年8月）

**最終更新日**：2024年8月14日（PT）

このリリースノートは、2024年8月14日（PT）～2024年9月のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **リンクトラッキングに関する Web SDK の改善** | Web SDK の最新バージョンでは、リンクトラッキングに関するいくつかの注目すべき改善が行われ、Activity Map に直接メリットをもたらします。これらの新機能は、Web SDK JavaScript ライブラリと Web SDK タグ拡張機能の両方で利用できます。<ul><li>イベントのグループ化：訪問者が内部リンクをクリックすると、リンクトラッキング用に別のイベント呼び出しをトリガーする代わりに、次のページでイベントデータをグループ化することを選択できます。この改善により、契約上の制限に対して Web SDK で使用するイベントの数が削減されます。</li><li>フィルタークリックプロパティ：`OnBeforeLinkClickSend` に代わる新しいコールバックです。このコールバックを使用すると、リンク関連のデータをアドビに送信する前にフィルタリングまたは不明化できます。</li></ul><p>詳しくは、Web SDK ユーザーガイドの [clickCollection](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/clickcollection) を参照してください。</p> | オープンベータ版は 2024年7月10日（PT）から開始 | 2024年7月18日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* Workspace で複数の不明な値が表示される問題を修正しました（AN-353632）
* Admin Console で新規顧客または新規 Analytics 製品プロファイルを追加した後、通知メールが送信されない問題を修正しました（AN-350930）

### Analytics のその他の修正

AN-354361、AN-354248、AN-354211、AN-354324、AN-351532、AN-349808、AN-347831、AN-353777、AN-354092、AN-354064、AN-354202、AN-354006、AN-354097、AN-352548、AN-353819、AN-353818、AN-353628、AN-353747、AN-353527、AN-353490、AN-352647、AN-352656、AN-351274、AN-352135、AN-351519、AN-344906、AN-353697、AN-354499、AN-354402、AN-354062、AN-353905、AN-353932、AN-354142、AN-354194、AN-354182、AN-353758、AN-353039、AN-353612、AN-350799、AN-354414、AN-354636、AN-354249、AN-353637、AN-350949、AN-349402、AN-355103、AN-354174、AN-353823、AN-354819、AN-354215、AN-354219、AN-354040、AN-354763、AN-354597、AN-354478、AN-354528、AN-354335

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **保存された`cust_visids`** の有効期限は 13 か月 | 2024年5月22日（PT） | Analytics のヒット処理エンジンの次回リリース（**2024年7月を予定**）では、保存された `cust_visids` に 13 か月の有効期限が適用されます。レポートスイートで「訪問者のステッチを有効にする」が有効になっている場合、この設定は、ヒット時の `cust_visid` がない `visid_high/visid_low value` で、`cust_visid` を見つける際に使用します。 現在、`visid_high/visid_low` に対する `cust_visid` のマッピングに有効期限はありません。 このリリースでは、`visid_high/visid_low` にヒット時の `cust_visid` が設定されてから 13 か月以上が経過すると、マッピングが期限切れになります。 |

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
