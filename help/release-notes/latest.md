---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: ht
source-wordcount: '806'
ht-degree: 100%

---

# 現在の Adobe Analytics リリースノート（2024年10月23日リリース）

**最終更新日**：2024年12月9日（PT）

このリリースノートは、2024年10月16日（PT）～2024年末までのリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Analytics の新しい Report Builder** | 新しい Report Builder アプリケーションは、パフォーマンスの向上、合理化されたユーザーインターフェイス、2.0 API のサポート、Mac、Windows および web ブラウザー上の Microsoft Excel のサポートなど、Adobe Analytics に大幅な更新を提供します。このアプリケーションはレガシーアプリケーションと共に使用できますが、同じファイルでは使用できません。新しいアプリケーションにレガシーワークブックをアップグレードするためのアップグレード機能が提供されます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics/analyze/report-builder/report-buider-overview) |  | 2024年10月16日（PT） |
| **タグ実装を Web SDK タグに移行するための JSON の書き出し** | Analytics タグ拡張機能に対するこのアップデートは、Web SDK への移行に関連するものです。Adobe Analytics 拡張機能に対するこのアップデートをワークフローの一部として使用し、Web SDK 拡張機能を使用して拡張機能の設定を再作成できます。Adobe Analytics タグ拡張機能では、eVar、props およびイベント設定を JSON として表示できます。これらの設定は、編集用に書き出して、Web SDK 拡張機能に含めることができます。 |  | 2024年10月31日（PT） |
| **Analysis Workspace のパフォーマンスのリクエスト要因に関する新しい情報** | Analysis Workspace でパフォーマンスを分析する際に、新しい「リクエスト要因」セクションが使用できるようになりました。リクエストの処理方法と、処理時間に影響を与える様々な要因について詳しくは、[Analysis Workspace のパフォーマンスの最適化](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance)の「リクエスト要因」を参照してください。 |  | 2024年10月1日（PT） |
| **トランザクション ID の保持期間** | トランザクション ID の保持期間である 90 日は、2025年1月に 25 か月に延長されます。`transactionID` 変数はトランザクションを一意に識別し、ヒットがデータソースを介してアップロードされたデータに結び付けられるようにします。 |  | 2025年1月22日（PT） |

## Adobe Analytics の修正点

Analysis Workspace：AN-356287、AN-358435、AN-359456、AN-359826、AN-360215
管理ツール：AN-342485、AN-347931、AN-348704、AN-357723、AN-358453、AN-358717、AN-359548、AN-360136
分類：AN-359025、AN-359283、AN-359368、AN-359710、AN-359752、AN-359759、AN-359799、AN-359887、AN-360543、AN-360566、AN-360612、AN-360741、AN-360942、AN-360952
クロスデバイス分析：AN-359210
顧客属性：AN-357897
データ収集：AN-351131、AN-351309、AN-355678、AN-359856
データフィード：AN-359699
Data Repair API：AN-360256
データソース：AN-359290
Data Warehouse：AN-359820
超過アラート：AN-358132

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **Campaign 以外のお客様は、トリガーにアクセスできなくなる** | 2023年10月16日（PT） | 2025年1月30日（PT）に、Adobe Campaign ライセンスを持たない Adobe Analytics のお客様は、トリガーを設定および使用できなくなります。お客様は、Campaign を購入するか、トリガーの使用を中止するか、トリガー機能を提供する他の Adobe ツールを検討する必要があります。 |
| **自動的にマッピングされる追加の実装詳細 XDM フィールド** | 2024年9月11日（PT） | Adobe Experience Platform Edge Network を使用してデータを Adobe Analytics に送信する際に、XDM フィールド `xdm.implementationdetails.name` と `xdm.implementationdetails.environment` は、常にコンテキストデータ変数 `c.a.x.implementationdetails.name` と `c.a.x.implementationdetails.environment` にマッピングされるようになりました。以前は、一部のシナリオで、これらの値が入力されませんでした。これらの値が使用可能になるように、関連する処理ルールを調整してください。 |

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe Analytics API（バージョン 1.4）の EOL（サポート終了）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。 Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2024年の以前のリリースノート](/help/release-notes/2024.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
