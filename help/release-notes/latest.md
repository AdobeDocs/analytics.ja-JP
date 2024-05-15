---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a4efa48df735eacbda0f53ba30064da7d8f71028
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 46%

---

# 最新の Adobe Analytics リリースノート（2024年5月）

**最終更新日**：2024年5月15日（PT）

これらのリリースノートは、2024 年 5 月 15 日（PT）から 6 月までのリリース期間を対象としています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関する新しいドキュメント** | Adobe AnalyticsからCustomer Journey Analyticsにアップグレードする場合、組織の現在のAdobe Analyticsの実装と長期目標に基づいて、複数のアップグレードオプションや多くの考慮事項に留意する必要があります。 次の内容をより深く理解するのに役立つ新しいドキュメントリソースが利用できるようになりました。<ul><li>存在するさまざまなアップグレードパス</li><li>組織の現在のAdobe Analytics実装に基づいて使用可能なアップグレードパス</li><li>各アップグレードパスのメリットとデメリット</li><li>各アップグレードパスのステップバイステップのガイダンス</li><li>履歴データの処理に関する考慮事項</li></ul>[Customer Journey Analyticsへのアップグレードの概要](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 今すぐ利用可能 |
| **を設定 `contextData` xdm を使用したフィールド** | エクスペリエンスEdge Networkを介してAdobe Analyticsにデータを送信するお客様は、次のことができます [コンテキストデータ値の設定](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/contextdata) xdm 内またはペイロードの「データ」部分のいずれかで直接。 |  | 今すぐ利用可能 |
| **Analytics リアルタイムレポート 2.0 API** | Adobe Analyticsの新しいリアルタイムレポート API 2.0 では、お客様の統合が向上し、迅速なレポート結果が得られます。 これらの結果は、プログラムを使用して、基本、トレンド、分類の各レポートを操作できます。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/real-time/) | | 2024年5月30日（PT） |
| **ストリーミングメディア：Web SDK を使用したAdobe Experience Platform Edge Networkへの web データの送信** | Adobe Experience Platform Web SDK を使用して、ストリーミングメディア web データをAdobe Experience Platform Edge Networkに送信できるようになりました。 この機能強化により、よりパーソナライズされたキャンペーンを作成し、よりパーソナライズされたコンテンツを提供できるので、レポートするトラッキングデータが増えます。<p>この変更により、Customer Journey Analytics、Adobe Real-time CDP、Adobe Journey Optimizer、イベント転送など、すべての Platform ソリューションにわたる Web 実装の統合的な収集手段が提供されます。 以前は、Streaming Media web データをEdge Networkに送信する唯一の方法は、Media Edge API を使用することでした。 [詳細情報](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) | | 2024年5月31日（PT） |
| **デフォルトの低トラフィックしきい値の増加** | **2024年4月中旬**&#x200B;に、アドビは、次のように、デフォルトのレポートスイートの低トラフィックしきい値を引き上げ始めます。![低トラフィックしきい値](assets/thresholds.png)：これは、現在新しいしきい値を下回って設定されている変数にのみ影響します。 この度の変更は段階的に行われ、作業は **5月末**&#x200B;に完了する予定です。 この度の増加がロールアウトされると、高基数変数の変更に気付く場合があります。<ul><li>レポートには、より多くのディメンション値を使用できる場合があります。</li><li>セグメントと計算指標に含まれるデータの量が多くなる場合があります。</li><li>セグメントに基づく仮想レポートスイートには、より多くのデータが含まれる場合があります。</li><li>分類の書き出しには、より多くのデータが含まれる場合があります。</li></ul> | 2024年4月中旬 | 2024年5月31日（PT） |
| **Web SDK に対するサーバーコールの数を減らすActivity Map** | 現在、Activity Map リンクイベントは独自のイベントとしてカウントされ、追加費用が発生します。この機能強化により、AppMeasurementでのイベントの処理方法と同様に、一部のリンクイベントが取得され、次のヒットにパッケージ化されます。 （書類を添付） |  | 2024年5月31日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* An-343186、AN-344711、AN-344856、AN-345094、AN-345179、AN-346265、AN-345288、AN-346339、AN-346560、AN-347572、AN-347681、AN-347768、AN-348024 の分類の問題を修正しました。
* Data Warehouseに関する AN-346789; AN-347031; AN-347568;
* データフィードの問題（AN-343616、AN-345831、AN-345988、AN-346124、AN-346232、AN-346972、AN-347680、AN-347755、AN-347954）を修正しました。
* データソース AN-347890 の問題を修正しました。
* Analysis Workspaceの次の問題を修正しました。AN-321503、AN-343103、AN-343471、AN-345171、AN-345223、AN-345912、AN-346026、AN-346330、AN-346839、AN-347679
* 次の A4T の問題を修正しました。AN-345118;

### Analytics のその他の修正

AN-327749; AN-332949; AN-342881; AN-343171; AN-343708; AN-344034; AN-345559; AN-346023; AN-346230; AN-346330; AN-346469 346606; AN-346750; AN-346973; AN-347026; AN-347110; AN-347439;

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **ISO 地域の更新** | 2024年5月10日（PT） | Adobeは、2024 年 6 月 7 日に、2024 年の ISO 地域の更新を実施します。 このリリース以降、マイナーな地域情報（地域）に関するアップデートが提供される可能性があります。 |
| **保存された`cust_visids`** の有効期限は 13 か月 | 2024年3月20日（PT） | Analytics のヒット処理エンジンの次回リリース（4月または 5月を予定）では、保存された `cust_visids` に 13 か月の有効期限が適用されます。 レポートスイートで「訪問者のステッチを有効にする」が有効になっている場合、この設定は、ヒット時の `cust_visid` がない `visid_high/visid_low value` で、`cust_visid` を見つける際に使用します。 現在、`visid_high/visid_low` に対する `cust_visid` のマッピングに有効期限はありません。 このリリースでは、それ以降 13 か月以上が経過している場合 `visid_high/visid_low` に、 `cust_visid` ヒットすると、マッピングは期限切れになります。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。 Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2023年の以前のリリースノート](/help/release-notes/2023.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
