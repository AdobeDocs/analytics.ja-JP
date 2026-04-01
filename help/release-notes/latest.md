---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 89cc33528d3907d955a543f3e43774a1065e149a
workflow-type: tm+mt
source-wordcount: '1468'
ht-degree: 46%

---

# 現在の Adobe Analytics リリースノート（2026年3月）

**最終更新日**：2026年3月11日（PT）

これらのリリースノートは、2026年3月のリリース期間をカバーしています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 そのため、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能と説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ---- |
| **パネルの分類**<br/> パネルのドロップゾーンでは、ディメンションに基づいてパネルを（セグメントではなく）分類[するための追加機能が提供されるようになりました。](/help/analyze/analysis-workspace/c-panels/panels.md#break-down-a-panel) | 2026年3月31日（PT） | 2026年3月31日（PT） |
| **複数の列でテーブルを並べ替える** <br/>自由形式テーブルのデータを、ディメンションまたは指標のいずれであっても、Analysis Workspaceの複数の列で並べ替えることができるようになりました。<p>複数の列でデータを並べ替える際、各列に割り当てた優先度に従ってデータが並べ替えられます。優先度の番号は、並べ替えアイコンの横に表示されます。</p><p>詳しくは、[フリーフォームテーブルのフィルタリングと並べ替え](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)を参照してください。</p> | 2026年1月28日（PT） | 2026年3月4日（PT） <p>（当初は2026年2月18日予定）</p> |
| **Report Builder：すべてのスケジュール済みワークブックに対する管理者の表示**<br/> Report Builder Excel アドインには、管理者がスケジュール済みワークブックの担当者に関係なく、特定の組織のすべてのスケジュール済みワークブックを表示できる新しいフィルターオプションが含まれています。 このフィルターオプションは、Analytics管理者のみが使用できます。 スケジュールされたワークブックを表示する場合は、「ワークブック」タブと「レガシー」タブの両方で使用できます。<p>スケジュールされたすべてのワークブックを表示できる機能は、分散したチーム間でワークブックを移行する場合に特に便利です。この機能を使用すると、管理者は移行前にすべてのレガシーワークブックを簡単に見つけることができます。</p><p>以前は、管理者は自分がスケジュールしたワークブックのみを表示でき、他のユーザーがスケジュールしたワークブックは表示できませんでした。</p><p>詳しくは、[管理済みのスケジュール済みワークブック &#x200B;](/help/analyze/report-builder/manage-schedules-reportbuilder.md)を参照してください。</p> | | 2026年3月10日（PT） |
| **近似区別関数の更新**<br/>&#x200B;近似区別関数で使用されているHLL確率論的アルゴリズムは、近日中に更新されます。 この関数を使用した数値の結果の出力は、次のように過去の数値からわずかに変化する場合があります。</p><ul><li>微量の一意の値をカウントする場合、推定値を使用するのではなく、正確なカウントを使用するように結果が改善されます。</li><li>より大きな値をカウントする場合、カウントの見積もりは、このアップデートの前と同じ精度を保持します（見積もりは、正確な数の5% （95%）以内に正確です）。</li></ul><p>個別関数の概算の詳細については、[詳細関数](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct)の[個別関数の概算](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)を参照してください</p> | | 2026年3月10日（PT） |
| **Analysis Workspaceの実践チュートリアル**<br/>&#x200B;新しい実践チュートリアルが利用可能になり、Analysis Workspaceでのパネル、ビジュアライゼーション、コンポーネントの基本的な使用方法を新しいユーザーにガイドできるようになりました。 <p>詳しくは、[Adobe Analytics ランディングページ &#x200B;](/help/analyze/landing.md)を参照してください。</p> | | 2026年3月18日（PT） |
| **フォールアウトビジュアライゼーションの機能強化**<br/> フォールアウトビジュアライゼーションには、次の機能強化が含まれます。<ul><li>ドラッグ&amp;ドロップ操作のエクスペリエンスが強化されました。<br/> タッチポイントにカーソルを合わせて、ビジュアライゼーション内の新しい場所にドラッグするだけです。<br/>以前は、ドラッグする前にタッチポイントの編集アイコンをクリックする必要がありました。</li><li>ドラッグ&amp;ドロップで顧客接点を組み合わせる場合の文言の明確化：<br/> タッチポイントを別のタッチポイントにドラッグすると、「結合」テキストが表示され、2つのタッチポイントが結合されていることを示します。<br/>以前は、タッチポイントをビジュアライゼーション内の新しい場所に移動するか、別のタッチポイントと組み合わせるかにかかわらず、「追加」テキストが表示されていました。</li><li>ツールヒントの再設計：<br/> タッチポイントにカーソルを合わせると表示されるツールヒントは、より直感的で読みやすいものです。</li><li>見つけやすいコンテキストメニュー。<br/> ツールヒントには、タッチポイントのコンテキストメニューへの便利なアクセスを提供する新しい「分析するクリック」オプションが含まれています。<br/>以前は、タッチポイントを右クリックしたときにのみコンテキストメニューを使用していました。</li></ul><p>詳しくは、[&#x200B; フォールアウトビジュアライゼーションの設定](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md)を参照してください。</p> | | 2026年3月25日（PT） |
| **パネルに分類を適用**<br/>&#x200B;分類をパネルに適用できるようになりました。 パネルレベルで分類を適用すると、分類はパネル内のすべてのフリーフォームテーブルのすべての列に適用されます。 | 2026年3月 | 2026年5月 |
| **ストリーミングメディアサービス：スケジュールのデータをサポート** <br/>過去のライブストリーミングメディアコンテンツのスケジュール済みデータをアップロードして、視聴者をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |

## Adobe Analytics の修正点

**Activity Map**:
**Analysis Workspace**: AN-440336, AN-440216, AN-440121, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883, AN-424359
**分類**: AN-440143, AN-439891, AN-439844, AN-438994, AN-438057, AN-438052, AN-437986, AN-437896, AN-435387, AN-435335, AN-435150, AN-433050, AN-432062, AN-431873, AN-429642
**データフィードとData Warehouse**: AN-439441、AN-437086、AN-433064、AN-432121、AN-431755、AN-428239、AN-427049、AN-425036、AN-424972、AN-423509、AN-335417、AN-283958、AN-256948
**移行**:
**書き出し**: AN-432030
**Report Builder**: AN-437895、AN-437083、AN-434288、AN-434209、AN-433224、AN-430622
**レポート**: AN-434545、AN-431206、AN-428043
**スケジュール済みレポート**:
**セグメント化**:
**その他**: AN-440076、AN-434783、AN-434542、AN-434233、AN-433368、AN-432138、AN-431322、AN-431012、AN-429067、AN-423285


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
