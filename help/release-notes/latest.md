---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
hold: true
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
source-git-commit: 6dd4e1e089cf72c03c8d2fd43ac87e919efa0602
workflow-type: tm+mt
source-wordcount: 1061
ht-degree: 49%

---

# 最新のAdobe Analytics リリースノート（2026年9月）

**最終更新**: 2026年9月8日

これらのリリースノートは、2026年9月のリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **レポートの日付範囲にセグメントを制限**<br/> Workspace レポートのデータは、セグメントに日付範囲コンポーネントが含まれている場合、レポートの日付範囲を超えて拡張できます。<p>セグメントに含まれる日付コンポーネントに関係なく、レポート日付範囲に結果を制限できる新しいオプションが利用可能になりました。</p><p>このオプションは、最上位コンテナが訪問者であるセグメントを作成または変更する場合に使用できます。</p><p>詳しくは、[&#x200B; セグメントの構築](/help/components/segmentation/segmentation-workflow/seg-build.md#components)を参照してください。</p> | 2026年8月26日（PT） | 2026年9月9日（PT） |
| **ボット検出の更新**<br/> Web SDKでEdge Data Collectionを使用する場合、次のボット検出の更新が利用できます。<ul><li>ボット検出ルールを作成して、ボットが生成したトラフィックとして扱われる例外を識別できるようになりました。 既存のルールと今後のルールは、デフォルトで一致するトラフィックをボット生成としてマークします。</li><li>カスタムボットルールがIAB ボット検出ルールの前に実行されるようになりました。 この変更はボットスコアには影響しませんが、イベントに関連付けられたボットルール名は変更される可能性があります。</li></ul><p>注意：このアップデートは、Web SDKを使用するEdge Data Collection実装にのみ適用されます。 AppMeasurementなどの古いライブラリには適用されません。</p><p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年9月上旬 |
| **分類セット API アップデート**<br/>&#x200B;分類セット API ドキュメントに、分類セット API リクエストを設定するための更新されたエンドポイントとパラメーター情報が含まれるようになりました。<p>詳しくは、[分類エンドポイントガイド &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)を参照してください。</p> | 2026年9月5日（PT） | 2026年9月30日（PT） |
| **2.0 API レポートガイドの日付itemId エンコーディングガイダンス**<br/> Adobe Analytics 2.0 APIの日付トレンドレポートガイドに、日付`itemId` パラメーターと値のエンコード方法を説明する新しいセクションが追加されました。 これにより、非推奨となった1.4 APIから2.0 API サービスを設定して移行できます。<p>詳細については、[KPI レポート ガイド &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi)および[詳細レポート ガイド &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced)を参照してください。</p> | 2026年9月5日（PT） | 2026年9月30日（PT） |

### Adobe Analytics の修正点

**Activity Map**:AN-488579、AN-487247
**Analysis Workspace**: AN-487374、AN-487119、AN-468907、AN-468810、AN-468363、AN-468096、AN-467414、AN-466986、AN-466982、AN-465073、AN-463571、AN-462373
**分類**: AN-490825, AN-490802, AN-490549, AN-490472, AN-487782, AN-487286, AN-486531, AN-478859, AN-469929, AN-469033, AN-468944, AN-468827, AN-468592, AN-468326, AN-467115, AN-466995, AN-465636, AN-465616, AN-465380, AN-464911, AN-464338 463677 462729 462577 461040 459316, AN-, AN-, AN-, AN-, AN-, AN-FLY
**データフィードとData Warehouse**: AN-487624、AN-487287、AN-479923、AN-479166、AN-479109、AN-468483
**移行**：
**書き出し**: AN-467131
**Report Builder**: AN-487486、AN-478944、AN-470036、AN-468589、AN-468436、AN-456747、AN-456700、AN-442695
**レポート**: AN-468621、AN-465383、AN-463924
**レポートスイート**:AN-468484、AN-468460、AN-465385
**予定レポート**：
**セグメント化**: AN-486561
**その他**: AN-488549、AN-467426、AN-465265、AN-464645、AN-459714、AN-459323、AN-454514

### 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日付または更新日付 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。 すべてのユーザーは、従来のワークブックから[新しい Report Builder](/help/analyze/report-builder/rb-overview.md) へのアップグレードを開始する必要があります。 新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。 [ほぼ同等の機能パリティ](/help/analyze/report-builder/convert-workbooks.md#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。 アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。 新しい Report Builder は、Microsoft Store を通じてアドインとしてのみ使用できます。 多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。 このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026**&#x200B;年8月31日（PT）に、次のAnalytics Legacy API サービスが提供終了し、シャットダウンされました。これらのサービスを使用して構築された統合は機能しなくなります。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) を参照してください。</p> |

## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。

## 延期された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールされたデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（広告付き無料テレビ）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、「[&#x200B; ライブコンテンツを追跡するためのスケジュールデータのアップロード &#x200B;](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)」を参照してください。 | 2025年10月29日（PT） | 未定<p>（当初は2025年10月29日に予定）</p> |


>[!MORELIKETHIS]
>
>* [2026年の以前のリリースノート &#x200B;](/help/release-notes/2026.md)
>* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
>* [ストリーミングメディアサービスのリリースノート](https://experienceleague.adobe.com/ja/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

