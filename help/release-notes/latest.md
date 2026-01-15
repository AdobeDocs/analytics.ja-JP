---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 69aa42b1949944b59740222073635be72c4bd6ab
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 49%

---

# 現在の Adobe Analytics リリースノート（2026年1月）

**最終更新日**：2026年1月14日（PT）

これらのリリースノートは、2026 年 1 月のリリース期間を対象としています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **分類セットルールビルダー** | ルールビルダー機能を分類セットで使用できるようになりました。 ルールは分類セットのコンテキスト内で定義します。 ルールは（アクティブ化されると）、分類セットを購読しているすべてのレポートスイートとキーディメンションの組み合わせに適用されます。<p>（ドキュメントのリンクは以下を参照。）</p> |  | 2026年1月30日（PT） |
| **データフィードの改善** | データフィードが次のように改善されました。<ul><li>ユーザーエクスペリエンスが向上しました。</li><li>列テンプレートの作成と管理に関する新しいエクスペリエンス。</li><li>今後のデータフィードで再利用するために、列テンプレートを作成するタイミングを選択できるようになりました。 また、テンプレートを削除、編集、コピーすることもできます。<br/> 以前は、作成された各データフィードが新しい列テンプレートとなり、多数の未使用の列テンプレートが発生し、それらを削除または管理する方法がありませんでした。</li><li>タグで追加およびフィルタリングします。</li><li>データフィードジョブの履歴の表示。 （リクエスト期間の開始日、開始日、終了日など）。</li><li>データフィードを再送信または再処理します。 （ジョブ履歴ページから）</li><li>到着が遅れたヒットを許可します。 データフィードジョブがデータの処理を完了した後に到着したデータを、設定されたレポート頻度内に含めることができるようになりました。</li><li>データフィードの終了日を選択する場合、選択した終了日はデータフィードの最終日として含まれます。<br/> 以前は、終了日はデータフィードから除外されていました。</li><li>15 分の書き出し頻度が可能になりましたが、デフォルトでは使用できません。 お使いの環境でこのオプションを使用できるようにするには、まずAdobe カスタマーケアに問い合わせて、15 分の書き出しをサポートするようにレポートスイートが設定されていることをリクエストする必要があります。</li></ul><p>**メモ：** これらの機能強化により、Adobe Analyticsのデータフィードページの URL も更新されています。 2026 年 4 月 30 日（PT）までに、新しいデータフィードページを指すように既存のブックマークを更新してください。</p>（ドキュメントのリンクは以下を参照。）</p> | 2026年1月20日（PT） | 2026年2月10日（PT） |
| **複数の列でテーブルを並べ替える** | ディメンションか指標かに関わらず、Analysis Workspaceで複数の列でフリーフォームテーブルのデータを並べ替えることができるようになりました。<p>複数の列のデータを並べ替える場合、各列に割り当てた優先度に従ってデータが並べ替えられます。 優先度番号は、並べ替えアイコンの横に表示されます。</p><p>（ドキュメントへのリンクを添付）<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | 2026年1月28日（PT） | 2026年2月18日（PT） |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |

## Adobe Analytics の修正点

**Activity Map**:
**Analysis Workspace**: AN-423389、AN-422636、AN-422482、AN-422027、AN-421134、AN-420187、AN-406271、AN-406188、AN-405997、AN-405983 405796、AN-405033、AN-404893、AN-404871、AN-404842、AN-404713、AN-404502、AN-404353、AN-404352 404048 402523 396149 390990 390728 390646 383484 376980 371729 347570、AN-COUNTERN、AN-COUNTERN、AN-COUNTERN、AN-AN-AN AN-AN-AN-AN-AN, AN-AN-AN, AN-AN, AN-AN, AN-AN-AN
**分類**:AN-423985、AN-423092、AN-423067、AN-422913、AN-422908、AN-422793、AN-422785、AN-422745、AN-422705 422422、AN-422126、AN-422098、AN-422077、AN-422058、AN-421999、AN-421698、AN-421351、AN-406583 406295 406123 406052 404743 404372、AN-COUNTRIES、AN-COUNTRIES、AN-COUNTRIES、AN-AN-AN
**データ収集**: AN-422488
**データフィードおよびData Warehouse**:AN-423186、AN-422789、AN-422239、AN-421552、AN-421393、AN-421339、AN-421231、AN-420149、AN-406345 406217、AN-405073、AN-404822、AN-404774、AN-389691
**プライバシー**:
**Report Builder**: AN-422120、AN-421937、AN-406296、AN-402951、AN-399748
**レポート**:
**予定レポート**:AN-423087、AN-422686
**セグメント比較**:
**その他**: AN-423401、AN-422819、AN-422775、AN-422626、AN-422238、AN-422160、AN-422071、AN-421687、AN-420045、AN-404891、AN-404608、AN-390912


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **ライブストリーム処理の改善** | 2026年1月14日（PT） | Adobeでは、LiveStream ペイロードの形式を改善および変更する予定です。 これらのアップデートにより、LiveStream と他のAdobe Analytics機能（Analysis Workspaceなど）とのパリティが向上します。 プレビューエンドポイントを使用して、計画された変更をテストできます。 変更の完全なリストとプレビューエンドポイントの詳細については、[LiveStream リリースノート ] を参照してください。 Adobeは、2026 年 4 月 13 日（PT）に、更新されたペイロードフォーマットへのハードカットオーバーを計画します。 |
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
