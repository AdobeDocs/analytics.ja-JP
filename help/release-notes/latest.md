---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e975b544144a26cd5db2b77d4dba6a72d7f116a3
workflow-type: tm+mt
source-wordcount: '1278'
ht-degree: 93%

---

# 現在の Adobe Analytics リリースノート（2025年9月リリース）

**最終更新日**：2025年9月11日（PT）

このリリースノートは、2025年9月～10月上旬（PT）のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **プロジェクトとコンポーネントを Customer Journey Analytics に移行する際の改善点** | プロジェクトとコンポーネントを Adobe Analytics から Customer Journey Analytics に移行する際に、次の改善が利用できるようになりました。<ul><li>複数のプロジェクトを一度に移行します。<p>一度に 20 件までプロジェクトを移行できます。</p><p>以前は、一度に 1 つのプロジェクトしか移行できませんでした。</p></li><li>以前のプロジェクト移行で既にマッピングされているディメンションと指標のマッピングを更新します。<p>以前の移行で同じディメンションと指標がマッピングされていた場合でも、プロジェクトを移行するたびに、これらのマッピングを更新できるようになりました。</p><p>以前は、選択したマッピングは、今後のすべてのプロジェクト移行に対して永続的に適用されていました。</p></li><li>プロジェクト数が多い組織のパフォーマンスが向上しました。</li></ul><p>詳しくは、[Adobe Analytics から Customer Journey Analytics へのコンポーネントとプロジェクトの移行](/help/admin/tools/component-migration/component-migration.md)を参照してください。</p> | 2025年9月15日（PT） | 2025年9月18日（PT） |
| **新しいリファラータイプのディメンション項目を使用した AI トラフィックの分析** | 新しいリファラータイプディメンション項目は、AI ツールからのトラフィックを分析するのに役立ちます。 <p>この新しいリファラータイプのディメンション項目（会話型 AI ツールと呼ばれます）では、主要な AI ツールの参照ドメインをグループ化して、グループ全体のトレンドを調べることができます。この新しいカテゴリ内の参照ドメインの初期リストには、以下が含まれます（ただし、これに限定されるものではありません）。</p><ul><li>chatgpt.com</li><li>claude.ai</li><li>m365.cloud.microsoft</li><li>grok.com</li><li>gemini.google.com</li><li>perplexity.ai</li></ul><p>新しいディメンション項目は、Analysis Workspace、Report Builder、Data Warehouse、データフィードなど、すべての Adobe Analytics 関連ツールで使用できるようになります。</p><p>この新しいディメンション項目を使用する場合は、次の点に注意してください。</p><ul><li>検索エンジンの「AI モード」で表示される検索結果から来るリファラートラフィックと、従来の検索結果からのクリックスルーから来るリファラートラフィックを区別できない場合があります。</li><li>新しい会話型 AI ツール ディメンション項目は、トラフィックが最も多い大手プロバイダーに焦点を当てています。新たな傾向として、大手 AI ツールプロバイダーのドメインに類似したドメインを持つ、偽装サイトの数が増加していることが明らかになっています。増加の背景にあるのは、個人やグループが独自の AI ツールを簡単に作成し、インターネット上でホストできるようになったことです。これは急速に進化しているスペースであるため、人気のサイトが含まれていない場合は、アドビサポートチームにお問い合わせください。</li><li>新しい会話型 AI ツールディメンション項目を含むリファラータイプのディメンションは、Adobe Analytics で処理されるデータでのみ使用できます。 </li></ul><p>（ドキュメントへのリンクを添付。）</p> |   | 2025年10月15日（PT） |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツの予定データをアップロードして、より簡単かつ正確に視聴者を追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li><ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。特定のトピックやプログラムセグメントの視聴者データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に関連付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに関連付けることはできませんでした。</p><p>（ドキュメントへのリンクを添付。）<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025年10月29日（PT） |
| **ストリーミングメディアサービス：Adobe Experience Platform にストリーミングメディアデータを収集する XDM フィールドを更新しました** | ストリーミングメディアデータを Adobe Experience Platform に収集する際は、ストリーミングメディアパラメーターに関するドキュメントの「XDM フィールドパス」の見出しの下に表示されている XDM フィールドパスは使用しないでください。2025年5月9日（PT）より前に Analytics ソースコネクタを実装し、ストリーミングメディアデータを Platform に収集しているお客様は、ストリーミングメディアパラメーターに関するドキュメントの「XDM フィールドパスのレポート」の見出しの下に示されているように、既存の設定を mediaReporting フィールドパスに移行する必要があります。<p> これらのフィールドパスは、[オーディオおよびビデオパラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[広告パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/ad-parameters)、[チャプターパラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/chapter-parameters)、[プレーヤー状態パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/player-state-parameters)および[品質パラメーター](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/variables/quality-parameters)のページに表示されますが、「廃止」としてマークされています。（2025年5月9日（PT）以降に Analytics ソースコネクターを実装し、既に mediaReporting XDM パスのみを使用しているお客様は、アクションは必要ありません。）</p><p>廃止された XDM フィールドパスでのデータ取り込みは、2025年10月末まで継続されます。その後、廃止されたフィールドは完全に廃止され、Adobe Experience Platform スキーマ UI に表示されなくなります。データは mediaReporting フィールドを使用してのみ送信されるようになります。</p><p>詳しくは、[更新された XDM ストリーミングメディアフィールドへの Analytics ソースコネクタの実装の移行](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)を参照してください。</p><p>移行のサポートについては、Adobe Consulting サービスまたはアカウントチームにお問い合わせください。 </p> |  | 2025年10月 |

## Adobe Analytics の修正点

**Activity Map**：
**Analysis Workspace**：AN-386791、AN-380838、AN-389373、AN-390851、AN-391593、AN-391404、AN-393064、AN-379337
**分類**：AN-391364、AN-393014、AN-393882、AN-394346、AN-394333、AN-390201
**データ収集**：AN-388127
**データフィードとデータウェアハウス**：AN-391243
**プライバシー**：
**Report Builder**：AN-387741、AN-386777、AN-388720、AN-389343
**レポート**：AN-392863、AN-371871、AN-393640、AN-391334
**スケジュールされたレポート**：AN-391150、AN-390474
**セグメント比較**：
**その他**：AN-387858, AN-393985, AN-393287


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **レガシー Report Builder** | 2025年6月18日（PT） | レガシー Report Builder アドインは、2026年6月に廃止されます。すべてのユーザーは、従来のワークブックから[新しい Report Builder](/help/analyze/report-builder/rb-overview.md) へのアップグレードを開始する必要があります。新しい Report Builder は、Adobe Analytics と Customer Journey Analytics の両方のお客様が利用できます。[ほぼ同等の機能パリティ](/help/analyze/report-builder/convert-workbooks.md#unsupported)に加えて、多くの新しい便利な機能を利用でき、UI が強化されています。アップグレードプロセスを容易にするために、新しい Report Builder には、ワークブックの簡単なコンバージョン機能が含まれています。新しい Report Builder は、Microsoft ストアを通じてアドインとしてのみ使用できます。多くの組織では、ユーザーにアドインを提供できるようにするために、内部の承認プロセスが必要です。このプロセスに時間を割いて、今すぐ組織との連携を開始し、EOL までにワークブックをアップグレードできるように十分な時間を確保してください。 |
| **レガシードメインまたはレガシー SSO 経由のアクセス** | 2025年4月10日（PT） | アドビでは、セキュリティを強化し、ログインエクスペリエンスを効率化するために、ユーザーの Adobe Analytics へのアクセス方法を更新する予定です。この取り組みの一環として、`my.omniture.com` を含むレガシードメインまたはレガシー SSO 経由のアクセスは、**2026年1月2日（PT）**&#x200B;に完全に廃止されます。この日以降、レガシーログイン資格情報とレガシー SSO は機能しなくなります。すべてのユーザーは、Adobe Experience Cloud ID を使用して `experience.adobe.com` 経由でログインする必要があります。Experience Cloud ID に関するサポートが必要な場合は、組織の Adobe Analytics 管理者または[アドビカスタマーケア](https://helpx.adobe.com/jp/contact.html)にお問い合わせください。 |
| **Adobe Analytics API（バージョン 1.4）** | 2024年7月17日（PT） | **2026年8月12日（PT）**&#x200B;に、次の Analytics Legacy API サービスはサポート終了となり、シャットダウンされ、これらのサービスを使用して作成された現在の統合は機能を停止します。<ul><li>Adobe Analytics API（バージョン 1.4）</li><li>Adobe Analytics WSSE 認証</li></ul><p>Adobe Analytics API（バージョン 1.4）を使用する統合は [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) に移行する必要があり、WSSE 統合は [Adobe Developer Console](https://developer.adobe.com/console) の OAuth ベースの認証プロトコルに移行する必要があります。</p><p>よくある質問への回答と詳細なガイダンスについては、[Adobe Analytics 1.4 API EOL FAQ](/help/admin/c-admin-api/c-admin-14-api-eol.md) を参照してください。</p> |


## AppMeasurement

AppMeasurement リリースの最新のアップデートについて詳しくは、[AppMeasurement リリースノート](https://github.com/adobe/appmeasurement/releases)を参照してください。


## 関連リソース

* [2025年の以前のリリースノート](/help/release-notes/2025.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [ストリーミングメディアサービスのリリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
