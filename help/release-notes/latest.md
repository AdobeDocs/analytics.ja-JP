---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 00d716f12a7372ca94f09ddfddd7ffb55d4b1dd2
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 78%

---

# 最新のAdobe Analytics リリースノート（2025 年 7 月リリース）

**最終更新日**：2025年7月16日（PT）

これらのリリースノートは、2025 年 7 月 7 日から 8 月 15 日までのリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **アルゴリズムを使用した Livestream TNT フィールド** | Livestream は、テクノロジーが最新で安定した状態を維持できるよう、更新中です。 その更新の一環として、TNT フィールドにアルゴリズムが含まれている場合は、TNT フィールドを Livestream 出力に組み込み始めます。 ただし、これには、以前サポートされていた要素（`campaignId`、`recipeId`、`trafficType`、`actionId`、`actionName`）のみが含まれます。 Livestream の TNT スキーマ全体は変更されません。 |   | 7,2025年7月 |
| **顧客属性 UI へのナビゲーションを更新しました** | Adobe Experience Cloud のアプリセレクターから顧客属性ユーザーインターフェイスに直接アクセスできるようになりました。 | 2025年7月1日（PT） | 未定 |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。<ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。<p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に関連付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに関連付けることはできませんでした。詳細情報 |  | 2025年6月25日（PT） |

## Adobe Analytics の修正点

**Activity Map**: AN-360987
**Analysis Workspace**: AN-378094; AN-380979; AN-382908; AN-387652;
**分類**: AN-382412; AN-383157; AN-384616; AN-384803; AN-385933; AN-387320; AN-387351; AN-387832; AN-387833; AN-387839; AN-387915;
**データ収集**: AN-387661
**データフィード**: AN-375172; AN-384369; AN-387859; AN-387952; AN-388155;
**Platform**: AN-382813; AN-386627; AN-386815
**プライバシー**:AN-384390
**Report Builder**: AN-388035
**レポート**: AN-380441
**予定レポート**:AN-378280; AN-378331
**セグメント比較**:AN-368766


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。すべてのユーザーは、従来のワークブックから[新しい Report Builder](https://experienceleague.adobe.com/ja/docs/analytics/analyze/report-builder/rb-overview) へのアップグレードを開始する必要があります。新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。[ほぼ同等の機能パリティ](https://experienceleague.adobe.com/ja/docs/analytics/analyze/report-builder/convert-workbooks#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。新しい Report Builder は、Microsoft ストアを通じてアドインとしてのみ使用できます。多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **レガシードメインまたはレガシー SSO 経由のアクセス** | 2025年4月10日（PT） | アドビでは、セキュリティを強化し、ログインエクスペリエンスを効率化するために、ユーザーの Adobe Analytics へのアクセス方法を更新する予定です。この取り組みの一環として、`my.omniture.com` を含むレガシードメインまたはレガシー SSO 経由のアクセスは、**2026年1月2日（PT）**&#x200B;に完全に廃止されます。この日以降、レガシーログイン資格情報とレガシー SSO は機能しなくなります。すべてのユーザーは、Adobe Experience Cloud ID を使用して `experience.adobe.com` 経由でログインする必要があります。Experience Cloud ID に関するサポートが必要な場合は、組織の Adobe Analytics 管理者または[アドビカスタマーケア](https://helpx.adobe.com/jp/contact.html)にお問い合わせください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。


## 関連リソース

* [2025年の以前のリリースノート](/help/release-notes/2025.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアコレクションのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
