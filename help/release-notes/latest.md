---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 3d3a91e806be36ff1f913bcc336bde7520fb84a2
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 90%

---

# 現在の Adobe Analytics リリースノート（2025年6月リリース）

**最終更新日**：2025年6月18日（PT）

このリリースノートは、2025年6月18日（PT）から 2025年7月15日（PT）のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **ニューReport Builderでのセキュアなクラウド宛先のサポート** | Javascript Report Builder アドインで、次のクラウドストレージの宛先へのレポートの書き出しがサポートされるようになりました。<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>以前は、FTP とメールの宛先のみを使用できました。 セキュリティ上の問題により、FTP はサポートされなくなりました。</p><p>詳しくは、[ クラウド宛先への書き出しによるワークブックのスケジュール設定 ](/help/analyze/report-builder/report-builder-export.md) を参照してください。</p><p>これらの変更に加えて、Adobe Analyticsで場所を作成する際に、「次で使用」フィールドに、Report Builderで場所を使用するオプションが追加されました。詳しくは、[ クラウドの読み込み場所と書き出し場所の設定 ](/help/components/locations/configure-import-locations.md) を参照してください。</p> |  | 2025 年 6 月 19 日（Pt）（当初は 6 月 18 日（Pt）） |
| **新しいプレビューエクスペリエンス** | セグメントや計算指標などをプレビューするために使用されるプレビューパネルでは、ドーナツビジュアライゼーションではなく、横棒グラフビジュアライゼーションが使用されるようになりました。 |  | 2025年6月18日（PT） |
| **変更されたアトリビューションモデルダイアログ** | アトリビューションモデルダイアログでコンテナと期間を個別に定義できるようになりました。 |  | 2025年6月18日（PT） |
| **顧客属性 UI へのナビゲーションを更新しました** | Adobe Experience Cloud のアプリセレクターから顧客属性ユーザーインターフェイスに直接アクセスできるようになりました。 |  | 未定 |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。<ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。<p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に関連付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに関連付けることはできませんでした。詳細情報 |  | 2025年6月25日（PT） |

## Adobe Analytics の修正点

**A4T**：AN-379045
**Advertising Analytics**：AN-377338
**アラート**：AN-377229
**Analysis Workspace**：AN-378891、AN-379589、AN-379604、AN-381270、AN-382264、AN-382414、
**API 1.4**：AN-380188
**API 2.0**： AN-373078、 AN-379006、AN-381248
**分類**：AN-379209、AN-379315、AN-379567、AN-379573、AN-379749、AN-379764、AN-379818、 AN-380433、AN-381670、 AN-381751、AN-381994、AN-382055、AN-382682、 AN-383059、AN-383409
**貢献度分析**：AN-369822
**データフィード**：AN-365552、AN-367158、AN-378288、AN-379754、AN-380433、AN-380855、AN-380959、AN-381115、AN-381657、AN-381931
**Data Warehouse**：AN-379244
**プラットフォーム**：AN-375847
**処理ルール**：AN-375157
**Report Builder**：AN-371395、AN-372174、AN-373815、AN-383194
**サーバーコール**：AN-380930
**使用状況およびアクセスログ**：AN-372130、AN-382123
**仮想レポートスイート**：AN-382010


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。すべてのユーザーは、従来のワークブックから[新しい Report Builder](https://experienceleague.adobe.com/ja/docs/analytics/analyze/report-builder/rb-overview) へのアップグレードを開始する必要があります。新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。[ほぼ同等の機能パリティ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/report-builder/convert-workbooks#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。新しい Report Builder は、Microsoft ストアを通じてアドインとしてのみ使用できます。多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **レガシードメインまたはレガシー SSO 経由のアクセス** | 2025年4月10日（PT） | アドビでは、セキュリティを強化し、ログインエクスペリエンスを効率化するために、ユーザーの Adobe Analytics へのアクセス方法を更新する予定です。この取り組みの一環として、`my.omniture.com` を含むレガシードメインまたはレガシー SSO 経由のアクセスは、**2026年1月2日（PT）**&#x200B;に完全に廃止されます。この日以降、レガシーログイン資格情報とレガシー SSO は機能しなくなります。すべてのユーザーは、Adobe Experience Cloud ID を使用して `experience.adobe.com` 経由でログインする必要があります。Experience Cloud ID に関するサポートが必要な場合は、組織の Adobe Analytics 管理者または[アドビカスタマーケア](https://helpx.adobe.com/jp/contact.html)にお問い合わせください。 |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2025年1月17日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年6月30日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |



## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。


## 関連リソース

* [2025年の以前のリリースノート](/help/release-notes/2025.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
