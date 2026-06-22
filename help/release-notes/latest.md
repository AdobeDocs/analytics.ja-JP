---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2: id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8bfb44d4eeb1812ec9b91a68bd37c2b660eae76e
workflow-type: tm+mt
source-wordcount: 573
ht-degree: 91%

---

# 現在の Adobe Analytics リリースノート（2026年5月）

**最終更新**: 2026年6月22日（PT）

これらのリリースノートは、2026年6月のリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analyticsのジャーニーキャンバス** <br/>ジャーニーキャンバスは、Analysis Workspace 内のビジュアライゼーションで、ユーザーがジャーニーをどのように進めたり、そこから離脱したりするかを分析することで、定義済みのジャーニーに関する深いインサイトを得ることができます。 これにより、ジャーニーに含まれるイベント、ディメンション項目およびセグメントの任意の組み合わせを表すノードと矢印の柔軟なグラフを作成できます。 キャンバス上のノードをドラッグするか、ジャーニーのイベントと条件を並べ替えると、データが更新されます。<p>ジャーニーキャンバスは、以前は Customer Journey Analytics でのみ使用できました。</p><p>Adobe Analytics のジャーニーキャンバスの詳細について詳しくは、[ジャーニーキャンバスの概要](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)を参照してください。 </p><p>Adobe Analytics のジャーニーキャンバスビジュアライゼーションの作成方法について詳しくは、[ジャーニーキャンバスの設定](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)を参照してください。</p> | 2026年5月18日（PT） | 2026年6月5日（PT） |

### Adobe Analytics の修正点

**Activity Map**：
**Analysis Workspace**: AN-452009、AN-450375、AN-449870、AN-450814、AN-450698
**分類**:
**データフィードとData Warehouse**:
**移行**：
**書き出し**：
**Report Builder**: AN-440912
**レポート**:AN-423516
**レポートスイート**: AN-455684
**予定レポート**：
**セグメント化**：
**その他**：


### 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。 すべてのユーザーは、従来のワークブックから[新しい Report Builder](/help/analyze/report-builder/rb-overview.md) へのアップグレードを開始する必要があります。 新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。 [ほぼ同等の機能パリティ](/help/analyze/report-builder/convert-workbooks.md#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。 アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。 新しい Report Builder は、Microsoft ストアを通じてアドインとしてのみ使用できます。 多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。 このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。


>[!MORELIKETHIS]
>
>* [2026年の以前のリリースノート ](/help/release-notes/2026.md)
>* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
>* [ストリーミングメディアサービスのリリースノート](https://experienceleague.adobe.com/ja/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
