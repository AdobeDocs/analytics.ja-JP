---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: cf020d4d2b873668a17c978ed69a311db37e7cd0
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 52%
---
# 最新のAdobe Analytics リリースノート（2026年10月）

**最終更新**: 2026年10月7日

これらのリリースノートは、2026年10月のリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analytics MCP サーバーの読み取り専用アクセス許可**<br/>&#x200B;管理者は、ユーザーにAdobe Analytics MCP サーバーへの読み取り専用アクセス権を付与できるようになりました。 新しい[!UICONTROL MCP読み取り専用アクセス ]権限アイテムでは、プロジェクト、セグメント、計算指標を作成せずに、すべての読み取り専用ツールにアクセスできます。<p>既存の[!UICONTROL MCP アクセス ]権限項目の名前が[!UICONTROL MCP フルアクセス ]に変更されました。 この権限を持つユーザーは、コンポーネントの作成、変更、削除を行うツールを含む、すべてのツールにアクセスできます。</p><p>詳しくは、Adobe Analytics MCP サーバーのドキュメントの[権限の設定](https://developer.adobe.com/analytics-mcp/docs/guides/permissions)を参照してください。</p> | | 2026年10月6日（PT） |
| **コンポーネントの説明を自動生成** <br/> ディメンション、指標、計算指標、セグメント、日付範囲の説明を自動的に生成できるようになりました。 これにより、Workspace ユーザーは、特に大規模なコンポーネントライブラリを持つ組織で、使用するコンポーネントを理解できます。 <p>1つのコンポーネントに対して説明を生成したり、同時に多くのコンポーネントに対して説明を生成したりできます。</p> <p>（ドキュメントのリンクは以下を参照。）<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026年10月28日（PT） |
| **Adobe Brand Visibilityとの統合**<br/> Adobe Adobe Brand Visibilityを組織のAdobe Analyticsデータと連携させて、AIを活用した発見が、web サイトの実際のエンゲージメントとビジネスの成果にどのように結びつくのかを測定できます。<p>（ドキュメントのリンクは以下を参照。）</p> | | 2026年10月 |
| **CX Enterprise Coworker: Coworker ChatでのAdobe Analytics データの分析** <br/>Adobe CX Enterprise Coworker Chatでは、以前はAnalysis Workspaceでのみ可能だった高度なデータ分析を実行できるようになりました。 Coworker Chatは、Adobe Adobe Analyticsレポートスイートのデータにアクセスし、そのデータを検索して、自然言語プロンプトへの回答を得ることができます。<p>（ドキュメントのリンクは以下を参照。）</p> | 2026年10月2日（PT） | 未定<p>（当初は2026年9月25日に予定）</p> |

### Adobe Analytics の修正点

**Activity Map**:AN-494609、AN-493182
**Analysis Workspace**: AN-495340、AN-494789、AN-493307、AN-468900
**分類**: AN-498043, AN-496619, AN-496468, AN-496217, AN-496133, AN-495567, AN-494651, AN-494345, AN-494312, AN-494261, AN-493645, AN-493507, AN-493336, AN-492869, AN-492812, AN-492751, AN-492750, AN-492741, AN-491032, AN-490802, AN-490796 467849, AN-
**データフィードとData Warehouse**:AN-494937、AN-493065、AN-489796、AN-479109
**移行**: AN-489850、AN-468014
**書き出し**: AN-494337、AN-486563
**Report Builder**: AN-496602、AN-494224、AN-493737、AN-493508、AN-493505、AN-492806、AN-468981、AN-454376
**レポート**:AN-493637、AN-461260
**レポートスイート**: AN-496773、AN-495227、AN-494981、AN-494372、AN-494370、AN-493629
**スケジュール済みレポート**: AN-491103
**セグメント化**：
**その他**: AN-496398、AN-494453、AN-492494

### 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日付または更新日付 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | 従来のReport Builder アドインは、2026年6月に廃止されました。 すべてのユーザーは、従来のワークブックから[新しい Report Builder](/help/analyze/report-builder/rb-overview.md) へのアップグレードを開始する必要があります。 新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。 [ほぼ同等の機能パリティ](/help/analyze/report-builder/convert-workbooks.md#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。 アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。 新しい Report Builder は、Microsoft Store を通じてアドインとしてのみ使用できます。 多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。 このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026**&#x200B;年8月31日（PT）に、次のAnalytics Legacy API サービスが提供終了し、シャットダウンされました。これらのサービスを使用して構築された統合は機能しなくなります。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) を参照してください。</p> |

## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。

## 延期された機能

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| -----------|-----------|-----------|
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールされたデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（広告付き無料テレビ）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、「[ ライブコンテンツを追跡するためのスケジュールデータのアップロード ](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)」を参照してください。</p> | 2025年10月29日（PT） | 未定<p>（当初は2025年10月29日に予定）</p> |


>[!MORELIKETHIS]
>
>* [2026年の以前のリリースノート ](/help/release-notes/2026.md)
>* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
>* [ストリーミングメディアサービスのリリースノート](https://experienceleague.adobe.com/ja/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新

