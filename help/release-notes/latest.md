---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ded4f0b735c19457c63c80f5a0c52f6b306c7b6f
workflow-type: tm+mt
source-wordcount: 922
ht-degree: 61%

---

# 最新のAdobe Analytics リリースノート（2026年7月）

**最終更新**: 2026年7月8日

これらのリリースノートは、2026年7月のリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **サブヒット分析** <br/> サブヒット分析では、ヒットレベルよりも詳細なレベルで製品データを分析できます。 ヒット全体をフィルタリングするのではなく、ヒット内の個々の商品をセグメント化できます。 <p>例えば、同じ注文で購入された他の商品をすべて含めずに、特定の商品カテゴリーでセグメンテーションできます。</p><p>詳しくは、[&#x200B; サブヒット分析](/help/components/segmentation/sub-hit.md)を参照してください。</p> | 7月8日（PT） | 2026年7月末 |
| **Activity Map拡張機能：UIの更新** <br/>Activity Map オーバーレイ拡張機能のルックアンドフィールが更新され、今後の機能強化をサポートする基本的な機能強化も含まれています。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年7月末 |
| **AA 2.0 API検索機能ガイド** <br/>検索機能を使用して[&#x200B; レポートでディメンション項目のサブセットを返す](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters)。<p>詳しくは、Adobe Developerのレポートエンドポイントガイドの[検索機能](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters)を参照してください。 | | 2026年7月1日（PT） |
| **AA APIを使用した定期的なレポートの自動作成** <br/>Report APIを使用して、スケジュールに従って新しい指標を使用したデータパイプラインの定期的な自動Adobe Analytics レポートを設定します。 <p>詳しくは、Adobe Developerの[繰り返しAnalytics レポートの自動化エンドポイント ガイド &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/recurring)を参照してください。</p> | | 2026年7月1日（PT） |
| **AA**&#x200B;の新しい拡張パラメーター<br/>新しいDimension API拡張パラメーターを使用して、割り当てタイプ、有効期限、データタイプ、マーチャンダイジングのeVar設定フィールドを取得します。 <p>詳しくは、Adobe Developerの[API Reference](https://developer.adobe.com/analytics-apis/docs/2.0/apis/#operation/dimensions_getDimensions)および[Dimensions エンドポイントガイド &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)を参照してください。</p> | | 2026年7月1日（PT） |

### Adobe Analytics の修正点

**Activity Map**：
**Analysis Workspace**: AN-449890、AN-457527、AN-451161、AN-459034、AN-458071、AN-458398
**分類**: AN-453318、AN-456739、AN-455828、AN-455270、AN-460272、AN-459367、AN-459239、AN-458418、AN-458417
**データフィードとData Warehouse**:AN-456945、AN-460700
**移行**：
**書き出し**：
**Report Builder**:AN-457533、AN-453683
**レポート**: AN-447692、AN-451259、AN-455713
**レポートスイート**：
**スケジュール済みレポート**: AN-450715
**セグメント化**：
**その他**: AN-453982、AN-455771

### 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。 すべてのユーザーは、従来のワークブックから[新しい Report Builder](/help/analyze/report-builder/rb-overview.md) へのアップグレードを開始する必要があります。 新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。 [ほぼ同等の機能パリティ](/help/analyze/report-builder/convert-workbooks.md#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。 アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。 新しい Report Builder は、Microsoft ストアを通じてアドインとしてのみ使用できます。 多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。 このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) を参照してください。</p> |

## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。

## 延期された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールされたデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。 | 2025年10月29日（PT） | 未定<p>（当初は2025年10月29日に予定）</p> |


>[!MORELIKETHIS]
>
>* [2026年の以前のリリースノート &#x200B;](/help/release-notes/2026.md)
>* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
>* [ストリーミングメディアサービスのリリースノート](https://experienceleague.adobe.com/ja/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

