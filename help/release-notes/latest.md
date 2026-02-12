---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d1d08ded701ad68628179874aa6ac21e59ad08dc
workflow-type: tm+mt
source-wordcount: '1440'
ht-degree: 66%

---

# 現在の Adobe Analytics リリースノート（2026年2月）

**最終更新日**：2026年2月11日（PT）

これらのリリースノートは、2026 年 2 月のリリース期間を対象としています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **データフィードの機能強化** <p>データフィードに対して次の機能強化が行われています。</p><ul><li>ユーザーエクスペリエンスの向上。</li><li>列テンプレートの作成と管理に関する新しいエクスペリエンス。</li><li>今後のデータフィードで再利用するために、列テンプレートを作成するタイミングを選択できるようになりました。 また、テンプレートを削除、編集、コピーすることもできます。<br/>以前は、データフィードを作成するたびに新しい列テンプレートが作成されていたので、未使用の列テンプレートが大量に発生し、削除または管理する方法がありませんでした。</li><li>タグ別に追加とフィルタリング。</li><li>データフィードジョブの履歴の表示。（リクエスト期間の開始日時、開始日、終了日など）。</li><li>データフィードの再送信または再処理。（ジョブ履歴ページから）。</li><li>遅れて到着したヒットの許可。設定したレポート頻度内でデータフィードジョブがデータ処理を完了した後に到着したデータも含めることができるようになりました。</li><li>データフィードの終了日を選択する際、選択した終了日がデータフィードの最終日として含まれます。<br/>以前は、終了日はデータフィードから除外されていました。</li><li>15 分の書き出し頻度が可能になりましたが、デフォルトでは使用できません。このオプションをお使いの環境で使用できるようにするには、まずアドビカスタマーケアに問い合わせて、15 分の書き出しをサポートするようにレポートスイートが設定されていることをリクエストする必要があります。</li></ul><p>**メモ：**&#x200B;これらの機能強化により、Adobe Analytics のデータフィードページへの URL も更新されています。既存のブックマークは、2026年4月30日（PT）までに新しいデータフィードページを参照するように更新してください。</p><p>詳しくは、[ データフィードの作成 ](/help/export/analytics-data-feed/create-feed.md) および [ データフィードの管理 ](/help/export/analytics-data-feed/df-manage-feeds.md) を参照してください。</p> | 2026年1月20日（PT） | 2026年2月24日（PT）<p>（当初は 2026年2月10日（PT）にリリースされる予定でした）</p> |
| **複数の列でのテーブルの並べ替え** <p>Analysis Workspace で、ディメンションまたは指標のいずれの列でも、フリーフォームテーブルのデータを複数の列で並べ替えることができるようになりました。</p><p>複数の列でデータを並べ替える際、各列に割り当てた優先度に従ってデータが並べ替えられます。優先度の番号は、並べ替えアイコンの横に表示されます。</p><p>詳しくは、[フリーフォームテーブルのフィルタリングと並べ替え](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)を参照してください。</p> | 2026年1月28日（PT） | 3月 <p>（当初は 2026 年 2 月 18 日に予定）</p> |
| **個別概算カウント関数の更新**<p>Approximate Count Distinct 関数で使用される HLL 確率的アルゴリズムは、間もなく更新される予定です。 この関数を利用する数値の結果の出力は、次のように、過去の数値とは少し異なる場合があります。</p><ul><li>非常に少量の一意の値をカウントする場合、予測値を使用するのではなく、正確なカウントを使用するように結果が改善されます。</li><li>それより大きい数をカウントする場合、カウントの予測では、この更新の前と同じ精度が保持されます（予測は正確な数の 5% 以内、つまり 95% の確率で正確です）。</li></ul><p>個別概算カウント関数について詳しくは、「[ 高度な関数 ](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) の個別概算カウント [ を参照してください ](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> |  | 2026年3月 |
| **ストリーミングメディア：スケジュールデータのサポート** <p>過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。</p><p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |
| **新しいAdobe Analytics 2.0 レポートスイート API ガイド** <p>レポートスイート API を作成、取得、更新、削除します。 詳しくは、[Adobe Analytics 2.0 レポートスイート API リファレンスガイド ](https://developer.adobe.com/analytics-apis/docs/2.0/apis/report-suites/) および [Adobe Analytics 2.0 レポートスイート API エンドポイントガイド ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/report-suites/) を参照してください。</p> | | 今すぐ利用可能 |
| **新しいAdobe Analytics 2.0 API 異常値検出レポートガイド** <p>自動 API 異常値検出レポートを作成します。 詳しくは、[ 異常値検出 API レポートエンドポイントガイド ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/anomaly/) を参照してください。</p> | | 今すぐ利用可能 |
| **新しいAdobe Analytics 2.0 API の基本的な日付トレンドレポートガイド** <p>自動 API の基本日付トレンド KPI レポートの作成詳しくは、[ 異常値検出 API レポートエンドポイントガイド ](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi/) を参照してください。</p> | | 今すぐ利用可能 |

## Adobe Analytics の修正点

**Activity Map**:
**Analysis Workspace**: AN-424997、AN-424194、AN-425515、AN-423174、AN-425207、AN-428834、AN-306540、AN-426014、AN-427801
**分類**:AN-422723、AN-424467、AN-423724、AN-424003、AN-425217、AN-396062、AN-422744、AN-425456、AN-425271、AN-425655、AN-424894、AN-429236
**データフィードおよびData Warehouse**:AN-427082、AN-405154、AN-406512、AN-423594、AN-425283、AN-425208、AN-422510、AN-421189、AN-428986 426724、AN-401525、AN-426884、AN-425146
**移行**: AN-421192, AN-423443
**プライバシー**:
**Report Builder**: AN-391415、AN-425125
**レポート**:AN-422123、AN-425817、AN-421097、AN-422249、AN-403446、AN-424727、AN-426791、AN-427985
**予定レポート**:AN-425484、AN-425137
**セグメント化**:AN-428905, AN-428232
**その他**: AN-425054, AN-420190, AN-422248


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Livestream 処理の機能強化** | 2026年1月14日（PT） | アドビでは、LiveStream ペイロードの形式に対して機能強化と変更を行う予定です。これらのアップデートにより、LiveStream と Analysis Workspace などの他の Adobe Analytics 機能との間のパリティが向上します。予定している変更をテストできるプレビューエンドポイントを使用できます。変更の完全なリストとプレビューエンドポイントについて詳しくは、[LiveStream リリースノート](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/)を参照してください。アドビでは、2026年4月13日（PT）に、更新されたペイロード形式へのハードカットオーバーを予定しています。 |
| **TLS 1.2 暗号スイートの削除** | 2026年2月11日（PT） | 管理者向けの注意：Adobeは、2026 年 5 月 27 日（PT）にAdobe データ収集サーバーから次の TLS 1.2 暗号スイートのサポートを削除する予定です。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>ほとんどの実装において、顧客側での対応は必要ありません。 この変更は、主に、古い TLS ライブラリを使用する従来のネイティブアプリケーションから送信される Analytics データと、古いブラウザーやオペレーティングシステムを使用する少数の web 訪問者に影響を与えます。 これらの暗号スイートのサポートを削除すると、セキュリティが強化され、Adobeが最新の暗号化標準に合わせて調整されます。 現在、これらの暗号スイートに依存しているデータ収集トラフィックは 0.1% 未満です。</p> |
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
