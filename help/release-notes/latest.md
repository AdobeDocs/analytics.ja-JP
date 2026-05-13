---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7c04b33e94152be8826005cb9617cb49dadbdcb9
workflow-type: tm+mt
source-wordcount: 1340
ht-degree: 62%

---

# 最新のAdobe Analytics リリースノート（2026年5月）

**最終更新**: 2026年5月13日（PT）

このリリースノートでは、2026年5月のリリース期間について説明します。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analytics用MCP サーバー** <br/>Analytics MCP （Model Context Protocol）サーバーを使用すると、サポートされているMCP クライアントをAdobe Analyticsに接続できます。 接続が完了すると、MCP クライアントは、製品固有のツールを呼び出して、データの取得、クエリの実行、またはLLMまたはエージェント型ワークフローの一部としてサポートされている操作を実行できます。 詳しくは、[Analytics MCP サーバー](https://developer.adobe.com/analytics-mcp/docs/)を参照してください。<p>ベータ期間中にこれらのMCP サーバーを使用した場合は、ベータ版と実稼動エンドポイントの間に異なるURLがあることに注意してください。 ベータ期間中に作成されたエージェント型ワークフローが、5月31日より前に実稼動エンドポイントを使用するように更新されていることを確認します。</p> | | 2026年5月5日（PT） |
| **Adobe Analyticsのジャーニーキャンバス** <br/> ユーザーキャンバスは、Analysis Workspaceのビジュアライゼーションです。ジャーニーがジャーニーをどのように進んでいるか、離脱するかを分析することで、定義されたユーザージャーニーに関する詳細なインサイトを得ることができます。 ジャーニーに含まれるイベント、ディメンション項目、セグメントの任意の組み合わせを表す、ノードと矢印の柔軟なグラフを作成できます。 ノードをキャンバスにドラッグしたり、ジャーニーのイベントや条件を並べ替えたりすると、データが更新されます。<p>ジャーニーキャンバスは、以前はCustomer Journey Analyticsでのみ使用できました。</p><p>（ドキュメントのリンクは以下を参照。）<!--To learn more about Journey canvas in Adobe Analytics, see Journey canvas overview. To learn how to build a Journey canvas visualization in Adobe Analytics, see Configure Journey canvas.--></p> | 2026年5月18日（PT） | 2026年6月5日（PT） |
| **アトリビューションモデル API レポートガイド** <br/>新しいAdobe Analytics 2.0 API アトリビューションモデルレポートガイドが利用可能です。 このガイドでは、Dimension API レポートにアトリビューションモデルオブジェクトデータを含める方法について説明します。<p>詳しくは、[Dimension API アトリビューションモデル &#x200B;](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/attmodel)を参照してください。</p> | | 2026年5月 |
| **ストリーミングメディアサービス：スケジュールデータのサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュールされたデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |

{style="table-layout:auto"}

## Adobe Analytics の修正点

**Activity Map**:
**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-440599, AN-439797, AN-434855, AN-429777, AN-429048 428892, AN-428189, AN-425215
**分類**: AN-447743, AN-447296, AN-447130, AN-446552, AN-446324, AN-446040, AN-445841, AN-445753, AN-444992, AN-444979, AN-444428, AN-444332, AN-443507, AN-442906, AN-442232, AN-442207, AN-442133, AN-442035, AN-441901, AN-441807, AN-441671, AN-441333 441302 441267 441132 441085 441048 440846 440727 440716 440496 440429 432100, AN – として，AN-, AN-O, AN-O
**データフィードとData Warehouse**: AN-447344、AN-446654、AN-445126、AN-444492、AN-442802、AN-442211、AN-442048、AN-441719、AN-441534、AN-441300、AN-441183、AN-441011、AN-440625
**移行**: AN-442467、AN-440380、AN-440357
**書き出し**:
**Report Builder**: AN-448697、AN-447128、AN-441148、AN-441136、AN-438147、AN-425150
**レポート**: AN-445123, AN-444869, AN-443453, AN-443275, AN-443148, AN-442464, AN-442148, AN-441811, AN-441506, AN-441149, AN-441119, AN-440545, AN-440511, AN-440300, AN-431409, AN-423359, AN-406242
**レポートスイート**:
**スケジュール済みレポート**:
**セグメント化**:
**その他**: AN-449159、AN-444661、AN-439429、AN-439423、AN-430988、AN-397985


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Livestream 処理の機能強化** | 2026年1月14日（PT） | アドビでは、LiveStream ペイロードの形式に対して機能強化と変更を行う予定です。 これらのアップデートにより、LiveStream と Analysis Workspace などの他の Adobe Analytics 機能との間のパリティが向上します。 予定している変更をテストできるプレビューエンドポイントを使用できます。 変更の完全なリストとプレビューエンドポイントについて詳しくは、[LiveStream リリースノート](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)を参照してください。 アドビでは、2026年4月13日（PT）に、更新されたペイロード形式へのハードカットオーバーを予定しています。 |
| **TLS 1.2 暗号スイートの削除** | 2026年2月11日（PT） | 管理者への通知：アドビでは、2026年5月27日（PT）に Adobe データ収集サーバーから次のTLS 1.2 暗号スイートのサポートを削除する予定です。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>ほとんどの実装で、お客様のアクションは必要ありません。 この変更は主に、古い TLS ライブラリを使用するレガシーネイティブアプリケーションから送信される Analytics データと、古いブラウザーやオペレーティングシステム上の少数の web 訪問者に影響します。 これらの暗号スイートのサポートを削除することで、セキュリティが強化され、アドビは最新の暗号化標準に準拠することになります。 現在、これらの暗号スイートに依存するデータ収集トラフィックは 0.1％未満です。</p> |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。 すべてのユーザーは、従来のワークブックから[新しい Report Builder](/help/analyze/report-builder/rb-overview.md) へのアップグレードを開始する必要があります。 新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。 [ほぼ同等の機能パリティ](/help/analyze/report-builder/convert-workbooks.md#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。 アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。 新しい Report Builder は、Microsoft ストアを通じてアドインとしてのみ使用できます。 多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。 このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **レガシードメインまたはレガシー SSO 経由のアクセス** | 2025年4月10日（PT） | アドビでは、セキュリティを強化し、ログインエクスペリエンスを効率化するために、ユーザーの Adobe Analytics へのアクセス方法を更新する予定です。 この取り組みの一環として、`my.omniture.com` を含むレガシードメインまたはレガシー SSO 経由のアクセスは、**2026年1月2日（PT）**&#x200B;に完全に廃止されます。 この日以降、レガシーログイン資格情報とレガシー SSO は機能しなくなります。 すべてのユーザーは、Adobe Experience Cloud ID を使用して `experience.adobe.com` 経由でログインする必要があります。 Experience Cloud ID に関するサポートが必要な場合は、組織の Adobe Analytics 管理者または[アドビカスタマーケア](https://helpx.adobe.com/jp/contact.html)にお問い合わせください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。


## 関連リソース

* [2025年の以前のリリースノート](/help/release-notes/2025.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアサービスのリリースノート](https://experienceleague.adobe.com/ja/docs/media-analytics/using/release-notes/release-notes)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
