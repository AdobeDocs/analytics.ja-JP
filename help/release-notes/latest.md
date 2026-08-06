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
source-git-commit: fb075dbb41d961c625a6af24e70e07b398203b39
workflow-type: tm+mt
source-wordcount: 1270
ht-degree: 43%

---

# 最新のAdobe Analytics リリースノート（2026年8月）

**最終更新**: 2026年8月5日

これらのリリースノートは、2026年8月のリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **Activity Map拡張機能：UIの更新** <br/>Activity Map オーバーレイ拡張機能のルックアンドフィールが更新され、今後の機能強化をサポートする基本的な機能強化も含まれています。<p>Activity Map オーバーレイ拡張機能について詳しくは、[Activity Map拡張機能インターフェイス &#x200B;](/help/analyze/activity-map/overlay/overview.md)を参照してください。</p> | | 2026年8月5日（PT）<p>（当初は7月末予定）</p> |
| **LLM OptimizerでAnalytics データを使用する**<br> LLM Optimizerを組織のCustomer Journey Analytics データと接続して、AI主導の発見が、実際のweb サイトのエンゲージメントとビジネス成果にどのように変換されるかを測定できるようにします。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年8月14日（PT） |
| **ジャーニーキャンバスの機能強化**<br>&#x200B;次のジャーニーキャンバスの機能強化を利用できるようになりました。<ul><li>ジャーニーと過去の期間の比較。 現在のジャーニーを、4週間前、2四半期前、1年前、またはカスタム日付範囲と比較します。</li><li>選択したノードの場合、ジャーニーの任意のポイントで、選択したノードの後に来る最上位のディメンション項目を表示します。 選択したノードが分析の重要なイベントであり、その後のユーザーの行動を確認する場合に使用します。<p>以前は、選択したノードの前または後に表示できるのは、上位の即時ノードのみでした。 </p></li><li>ノード間の矢印の形状とスタイルを変更します。 ノード間で矢印をドラッグして矢印の形状（曲率）を変更し、矢印を右クリックして、スタイルをソリッド、破線、点線、点線、アニメーションのいずれかに変更します。</li></ul><p></p>詳しくは、[ジャーニーキャンバスビジュアライゼーションの設定](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)を参照してください。 | | 2026年8月18日（PT） |
| **Migration Planner: Adobe AnalyticsからCustomer Journey Analyticsへの移行**<br> Migration Plannerは、Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードに関連する最も複雑で時間のかかる作業（XDM スキーマの作成とAppMeasurementからの移行、またはAnalytics拡張機能（タグ）からExperience Platform Web SDKへの移行など）を自動化する移行ウィザードを提供します。 <p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年8月末または9月末 |
| **Analytics API マーケティングチャネルのリファレンス**<br/> Analytics 2.0 API マーケティングチャネルのリファレンスを使用して、Adobe Analytics マーケティングチャネルの情報を取得します。 [Analytics API マーケティングチャネルのリファレンス &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/apis/marketing-channels)を参照してください。 | | 2026年8月1日（PT） |
| **Analytics API マーケティングチャネルのエンドポイントガイド**<br/> Adobe Analytics 2.0 API マーケティングチャネルのエンドポイントガイドでは、エンドポイントを使用するための手順と例を提供します。 「[Analytics API マーケティングチャネル エンドポイントガイド &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/marketing-channels)」を参照してください。 | | 2026年8月1日（PT） |
| **Analytics 1.4 API EOLのお客様に関するFAQ**<br/> Analytics 1.4 API EOLのお客様に関するFAQでは、1.4 APIから離脱するお客様を支援するために、最近の2.0 API開発に関する情報を提供しています。 | | 2026年8月10日（PT） |

### Adobe Analytics の修正点

**Activity Map**: AN-404862
**Analysis Workspace**: AN-466867, AN-465995, AN-465315, AN-465313, AN-464375, AN-463634, AN-463248, AN-463175, AN-463049, AN-462347, AN-462124, AN-461922, AN-458398, AN-457849, AN-455002, AN-453357, AN-456863, AN-459816, AN-459034, AN-460774, AN-460671 457760 443594, AN-, AN-
**分類**: AN-467138, AN-467118, AN-467069, AN-466054, AN-465987, AN-465636, AN-465380, AN-464650, AN-464286, AN-463688, AN-462413, AN-462252, AN-462141, AN-462063, AN-462005, AN-461862, AN-461806, AN-461777, AN-461158, AN-460954, AN-460905, AN-460850 460803 460272 460023 459814 459367 459328 459300 459279 459006 458417 458403 457829 457400 454408 449670 460956 459269 458789 461778 461191 460996 460506 459988 459854 458994 457561 457055 454224 454172 459473 459277 459026 455270, AN-, AN-O AN-⌥, AN-⌥, AN-⌥, AN-⌥, AN-⌥, AN-⌥, AN-⌥, AN-⌥, AN-, AN-, AN-, AN-⌥, AN-, AN-⌥, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-
**データフィードとData Warehouse**: AN-465273、AN-464245、AN-462435、AN-461000、AN-460700、AN-459225、AN-459192
**移行**: AN-458185、AN-454285、AN-459239
**書き出し**：
**Report Builder**: AN-465346, AN-464768, AN-464580, AN-464301, AN-463048, AN-462800, AN-457042, AN-461033, AN-459042, AN-454250, AN-451735, AN-450776, AN-450200, AN-451665
**レポート**: AN-467107、AN-459010、AN-455619、AN-459530、AN-454103
**レポートスイート**:AN-464246、AN-463756、AN-462101
**スケジュール済みレポート**: AN-455009、AN-460037、AN-462093
**セグメント化**: AN-459002、AN-457730、AN-457146
**その他**: AN-467386、AN-466935、AN-462116、AN-458836、AN-451292、AN-454160、AN-458354、AN-455771、AN-426869、AN-437975

### 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日付または更新日付 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。 すべてのユーザーは、従来のワークブックから[新しい Report Builder](/help/analyze/report-builder/rb-overview.md) へのアップグレードを開始する必要があります。 新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。 [ほぼ同等の機能パリティ](/help/analyze/report-builder/convert-workbooks.md#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。 アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。 新しい Report Builder は、Microsoft Store を通じてアドインとしてのみ使用できます。 多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。 このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) を参照してください。</p> |

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

