---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d2f87c771ec2d5ab671cd8f022a2bd2e23a51ccb
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 45%

---

# 最新のAdobe Analytics リリースノート（2025 年 6 月リリース）

**最終更新日**：2025年6月18日（PT）

これらのリリースノートは、2025 年 6 月 18 日（PT）から 7 月 15 日（PT）までのリリース期間に対応しています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **ニューReport Builderでの安全な宛先のサポート** | 新しい書き出し先がReport Builder アドインに追加されました。 次のクラウドストレージの宛先がサポートされています。 <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> セキュリティ上の問題により、FTP はサポートされなくなりました。 （ドキュメントへのリンクを添付） |  | 2025 年 6 月 19 日（Pt）（当初は 6 月 18 日（Pt）） |
| **新しいプレビューエクスペリエンス** | セグメントや計算指標などをプレビューするためのプレビューパネルでは、ドーナツビジュアライゼーションではなく、横棒ビジュアライゼーションを使用するようになりました。 |  | 2025年6月18日（PT） |
| **変更されたアトリビューションモデルダイアログ** | アトリビューションモデルダイアログで、コンテナと期間を別々に定義できるようになりました。 |  | 18,2025年6月 |
| **顧客属性 UI へのナビゲーションを更新しました** | 顧客属性ユーザーインターフェイスに、Adobe Experience Cloudのアプリセレクターから直接アクセスできるようになりました。 |  | 未定 |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツの予定データをアップロードして、より簡単かつ正確に視聴者を追跡できるようになりました。 スケジュールデータのアップロードでサポートされるライブコンテンツの例を以下に示します。<ul><li>FAST （無料広告に対応した TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul>スケジュールデータをアップロードすると、アップロードファイルで指定した時間内に実行された個々のプログラムの視聴者データを追跡できます。 特定のトピックやプログラムセグメントの視聴者データを収集することもできます。 これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。<p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に関連付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに関連付けることはできませんでした。 詳細情報 |  | 2025年6月25日（PT） |

## Adobe Analytics の修正点

**A4T**: AN-379045
**Advertising Analytics**: AN-377338
**アラート**:AN-377229
**Analysis Workspace**: AN-378891; AN-379589; AN-379604; AN-381270; AN-382264; AN-382414;
**API 1.4**: AN-380188
**API 2.0**: AN-373078; AN-379006; AN-381248
**分類**: AN-379209; AN-379315; AN-379567; AN-379573; AN-379749; AN-379764; AN-379818; AN-380433; AN-381670; AN-381751; AN-381994; AN-382055; AN-382682; AN-383059; AN-383409
**貢献度分析**: AN-369822
**データフィード**: AN-365552; AN-367158; AN-378288; AN-379754; AN-380433; AN-380855; AN-380959; AN-381115; AN-381657; AN-381931
**Data Warehouse**: AN-379244
**Platform**: AN-375847
**処理ルール**:AN-375157
**Report Builder**: AN-371395; AN-372174; AN-373815; AN-383194
**サーバーコール**:AN-380930
**使用状況およびアクセスログ**:AN-372130; AN-382123
**仮想レポートスイート**:AN-382010


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | 従来のReport Builder アドインは、2026 年 6 月に廃止されます。 すべてのユーザーは、従来のワークブックから [ ニューReport Builder](https://experienceleague.adobe.com/ja/docs/analytics/analyze/report-builder/rb-overview) へのアップグレードを開始する必要があります。 新しいReport Builderは、Adobe AnalyticsとCustomer Journey Analyticsの両方のお客様が利用できます。 [ ほぼ同等の機能 ](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks#unsupported) に加えて、多くの新しい便利な機能と UI の強化があります。 アップグレードプロセスを容易にするために、新しいReport Builderには、ブックの簡単な変換機能が含まれています。 新しいReport Builderは、Microsoft ストアを通じてアドインとしてのみ使用できます。 多くの組織では、ユーザーがアドインを使用できるように、内部の承認プロセスが必要です。 このプロセスには時間を割いて今すぐ組織との連携を開始し、EOL 日までにワークブックをアップグレードするのに十分な時間を確保してください。 |
| **レガシードメインまたはレガシー SSO 経由のアクセス** | 2025年4月10日（PT） | アドビでは、セキュリティを強化し、ログインエクスペリエンスを効率化するために、ユーザーの Adobe Analytics へのアクセス方法を更新する予定です。この取り組みの一環として、`my.omniture.com` を含むレガシードメインまたはレガシー SSO 経由のアクセスは、**2026年1月2日（PT）**&#x200B;に完全に廃止されます。この日以降、レガシーログイン資格情報とレガシー SSO は機能しなくなります。すべてのユーザーは、Adobe Experience Cloud ID を使用して `experience.adobe.com` 経由でログインする必要があります。Experience Cloud ID に関するサポートが必要な場合は、組織の Adobe Analytics 管理者または[アドビカスタマーケア](https://helpx.adobe.com/jp/contact.html)にお問い合わせください。 |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2025年1月17日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年6月30日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Adobe Analytics API （バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |



## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。


## 関連リソース

* [2025年の以前のリリースノート](/help/release-notes/2025.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
