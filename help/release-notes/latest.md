---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7a245e2c24e8763c93150aa5b9f3ac2d197f6f1f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 62%

---

# 現在の Adobe Analytics リリースノート（2026年4月）

**最終更新日**：2026年4月9日（PT）

これらのリリースノートは、2026年4月のリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 そのため、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analytics用MCP サーバー** <br/>MCP （Model Context Protocol）を使用して、Adobe Analyticsを既存のエージェント型ワークフローに関連付けることができるようになりました。 自然言語を使ってレポートやインサイトをリクエストできます。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年4月末 |
| **ストリーミングメディアサービス：スケジュールのデータをサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュール済みデータをアップロードして、視聴者をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |
| **追加のAPI日付範囲の書式設定**<br/> Analytics 2.0 API レポート要求で日付範囲を指定するために、2つの新しい形式がサポートされるようになりました。 これには、日付式と混合形式が含まれます。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | 2026年3月 |
| **API レポート要求のオプション ディメンション**<br/> レポート API要求ではディメンション オブジェクトは必要ありません。 ディメンションが指定されていない場合、応答には合計レポートのデータが表示されます。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | 2026年3月 |
| **日付トレンドの高度なAPI レポート**<br/>&#x200B;新しいAdobe Analytics 2.0 API日付トレンドの高度なレポートガイド。 日付範囲の比較とセグメントを使用して、高度な日付トレンドのAPI レポートを作成します。 [詳細情報](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | 2026年3月 |

## Adobe Analytics の修正点

**Activity Map**:
**Analysis Workspace**: AN-442813、AN-442410、AN-441943、AN-441717、AN-434855、AN-431409、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215
**分類**: AN-443453, AN-443275, AN-443148, AN-442906, AN-442232, AN-442207, AN-442148, AN-442133, AN-441937, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302, AN-441149, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-440716 440511 440496 432100, AN-, AN-, AN-
**データフィードとData Warehouse**: AN-442211、AN-441719、AN-441183、AN-441011、AN-440625、AN-438953
**移行**: AN-442467、AN-440380、AN-440357
**書き出し**:
**Report Builder**: AN-441136、AN-438147、AN-425150
**レポート**: AN-441506、AN-440919、AN-440545、AN-440300
**レポートスイート**:AN-439429、AN-439423、AN-430988
**スケジュール済みレポート**:
**セグメント化**:
**その他**: AN-423359、AN-406242、AN-397985


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Livestream 処理の機能強化** | 2026年1月14日（PT） | アドビでは、LiveStream ペイロードの形式に対して機能強化と変更を行う予定です。これらのアップデートにより、LiveStream と Analysis Workspace などの他の Adobe Analytics 機能との間のパリティが向上します。予定している変更をテストできるプレビューエンドポイントを使用できます。変更の完全なリストとプレビューエンドポイントについて詳しくは、[LiveStream リリースノート](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)を参照してください。アドビでは、2026年4月13日（PT）に、更新されたペイロード形式へのハードカットオーバーを予定しています。 |
| **TLS 1.2暗号スイートの削除** | 2026年2月11日（PT） | 管理者へのお知らせ：Adobeは、2026年5月27日に、Adobe データ収集サーバーから次のTLS 1.2暗号スイートのサポートを削除する予定です。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>ほとんどの実装では、顧客の操作は必要ありません。 この変更は、主に、古いTLS ライブラリを使用するレガシーネイティブアプリケーションから送信されるAnalytics データと、古いブラウザーまたはオペレーティングシステム上の少数のweb訪問者に影響します。 これらの暗号スイートのサポートを削除すると、セキュリティが強化され、Adobeが最新の暗号化標準に準拠します。 現在、これらの暗号スイートに依存するデータ収集トラフィックは、0.1%未満にとどまっています。</p> |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。 すべてのユーザーは、従来のワークブックから[新しい Report Builder](/help/analyze/report-builder/rb-overview.md) へのアップグレードを開始する必要があります。 新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。 [ほぼ同等の機能パリティ](/help/analyze/report-builder/convert-workbooks.md#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。 アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。 新しい Report Builder は、Microsoft ストアを通じてアドインとしてのみ使用できます。 多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。 このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **レガシードメインまたはレガシー SSO 経由のアクセス** | 2025年4月10日（PT） | アドビでは、セキュリティを強化し、ログインエクスペリエンスを効率化するために、ユーザーの Adobe Analytics へのアクセス方法を更新する予定です。 この取り組みの一環として、`my.omniture.com` を含むレガシードメインまたはレガシー SSO 経由のアクセスは、**2026年1月2日（PT）**&#x200B;に完全に廃止されます。 この日以降、レガシーログイン資格情報とレガシー SSO は機能しなくなります。 すべてのユーザーは、Adobe Experience Cloud ID を使用して `experience.adobe.com` 経由でログインする必要があります。 Experience Cloud ID に関するサポートが必要な場合は、組織の Adobe Analytics 管理者または[アドビカスタマーケア](https://helpx.adobe.com/jp/contact.html)にお問い合わせください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。


## 関連リソース

* [2025年の以前のリリースノート](/help/release-notes/2025.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアサービスのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
