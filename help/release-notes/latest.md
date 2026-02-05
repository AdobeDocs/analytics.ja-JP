---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 611dedca3782ac0381a85230d72c2cfe0e4f67b8
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 99%

---

# 現在の Adobe Analytics リリースノート（2026年1月）

**最終更新日**：2026年1月14日（PT）

このリリースノートは、2026年1月のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **分類セットルールビルダー** | [ルールビルダー](/help/components/classifications/sets/manage/rules.md)機能が分類セットで使用できるようになりました。ルールは、分類セットのコンテキスト内で定義します。ルールは、（アクティブ化した場合）分類セットに登録されているすべてのレポートスイートとキーディメンションの組み合わせに適用されます。</p> |  | 2026年1月23日（PT） |
| **データフィードの機能強化** | データフィードに対して次の機能強化が行われています。<ul><li>ユーザーエクスペリエンスの向上。</li><li>列テンプレートの作成と管理に関する新しいエクスペリエンス。</li><li>今後のデータフィードで再利用するために、列テンプレートを作成するタイミングを選択できるようになりました。また、テンプレートを削除、編集、コピーすることもできます。<br/>以前は、データフィードを作成するたびに新しい列テンプレートが作成されていたので、未使用の列テンプレートが大量に発生し、削除または管理する方法がありませんでした。</li><li>タグ別に追加とフィルタリング。</li><li>データフィードジョブの履歴の表示。（リクエスト期間の開始日時、開始日、終了日など）。</li><li>データフィードの再送信または再処理。（ジョブ履歴ページから）。</li><li>遅れて到着したヒットの許可。設定したレポート頻度内でデータフィードジョブがデータ処理を完了した後に到着したデータも含めることができるようになりました。</li><li>データフィードの終了日を選択する際、選択した終了日がデータフィードの最終日として含まれます。<br/>以前は、終了日はデータフィードから除外されていました。</li><li>15 分の書き出し頻度が可能になりましたが、デフォルトでは使用できません。このオプションをお使いの環境で使用できるようにするには、まずアドビカスタマーケアに問い合わせて、15 分の書き出しをサポートするようにレポートスイートが設定されていることをリクエストする必要があります。</li></ul><p>**メモ：**&#x200B;これらの機能強化により、Adobe Analytics のデータフィードページへの URL も更新されています。既存のブックマークは、2026年4月30日（PT）までに新しいデータフィードページを参照するように更新してください。</p>詳しくは、[ データフィードの作成 ](/help/export/analytics-data-feed/create-feed.md) および [ データフィードの管理 ](/help/export/analytics-data-feed/df-manage-feeds.md) を参照してください。</p> | 2026年1月20日（PT） | 2026年2月24日（PT）<p>（当初は 2026年2月10日（PT）にリリースされる予定でした）</p> |
| **複数の列でのテーブルの並べ替え** | Analysis Workspace で、ディメンションまたは指標のいずれの列でも、フリーフォームテーブルのデータを複数の列で並べ替えることができるようになりました。<p>複数の列でデータを並べ替える際、各列に割り当てた優先度に従ってデータが並べ替えられます。優先度の番号は、並べ替えアイコンの横に表示されます。</p><p>詳しくは、[フリーフォームテーブルのフィルタリングと並べ替え](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)を参照してください。</p> | 2026年1月28日（PT） | 2026年2月18日（PT） |
| **ストリーミングメディア：スケジュールデータのサポート** | 過去のライブストリーミングメディアコンテンツのスケジュールデータをアップロードして、閲覧者数をより簡単かつ正確に追跡できるようになりました。<p>以下は、スケジュールデータのアップロードでサポートされるライブコンテンツの例です。</p><ul><li>FAST（無料広告サポート TV）プラットフォーム</li><li>ローカルストリーム</li><li>ライブスポーツ</li></ul><p>スケジュールデータをアップロードすると、アップロードファイルで指定した時間帯に放送された個々の番組の閲覧者数データを追跡できます。 特定のトピックやプログラムセグメントの閲覧者数データを収集することもできます。</p><p>これらの機能は、ストリーミングメディアコレクションの実装方法に関係なく使用できます。</p><p>以前は、ライブコンテンツを分析する際に、特定のセッションを特定のプログラムに正確に紐付けることが難しく、特定のセッションを個々のトピックやプログラムセグメントに紐付けることはできませんでした。</p><p>詳しくは、[スケジュールデータをアップロードしてライブコンテンツを追跡する](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-use-cases/track-schedule-data)を参照してください。</p> | 2025年10月29日（PT） | 2026年上半期<p>（当初は 2025年10月29日（PT）にリリースされる予定でした）</p> |

## Adobe Analytics の修正点

**Activity Map**：
**Analysis Workspace**：AN-423389、AN-422636、AN-422482、AN-422027、AN-421134、AN-420187、AN-406271、AN-406188、AN-405997、AN-405983、AN-405796、AN-405033、AN-404893、AN-404871、AN-404842、AN-404713、AN-404502、AN-404353、AN-404352、AN-404048、AN-402523、AN-396149、AN-390990、AN-390728、AN-390646、AN-383484、AN-376980、AN-371729、AN-347570
**分類**：AN-423985、AN-423092、AN-423067、AN-422913、AN-422908、AN-422793、AN-422785、AN-422745、AN-422705、AN-422422、AN-422126、AN-422098、AN-422077、AN-422058、AN-421999、AN-421698、AN-421351、AN-406583、AN-406295、AN-406123、AN-406052、AN-404743、AN-404372
**データ収集**：AN-422488
**データフィードとデータウェアハウス**：AN-423186、AN-422789、AN-422239、AN-421552、AN-421393、AN-421339、AN-421231、AN-420149、AN-406345、AN-406217、AN-405073、AN-404822、AN-404774、AN-389691
**プライバシー**：
**Report Builder**：AN-422120、AN-421937、AN-406296、AN-402951、AN-399748
**レポート**：
**予定レポート**：AN-423087、AN-422686
**セグメント比較**：
**その他**：AN-423401、AN-422819、AN-422775、AN-422626、AN-422238、AN-422160、AN-422071、AN-421687、AN-420045、AN-404891、AN-404608、AN-390912


## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Livestream 処理の機能強化** | 2026年1月14日（PT） | アドビでは、LiveStream ペイロードの形式に対して機能強化と変更を行う予定です。これらのアップデートにより、LiveStream と Analysis Workspace などの他の Adobe Analytics 機能との間のパリティが向上します。予定している変更をテストできるプレビューエンドポイントを使用できます。変更の完全なリストとプレビューエンドポイントについて詳しくは、[LiveStream リリースノート]を参照してください。アドビでは、2026年4月13日（PT）に、更新されたペイロード形式へのハードカットオーバーを予定しています。 |
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
