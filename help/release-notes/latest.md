---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1d98d711c17d3c7ca487b8f5bd4e918a9a399ea7
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 53%

---

# 現在の Adobe Analytics リリースノート (2023年6月)

**最終更新日**：2023年6月1日（PT）

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## リリースのハイライト {#highlights}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **プロジェクトのリンク共有（ログインは不要）** | Adobe Analytics へのアクセス権を持たないユーザーと、Analysis Workspace プロジェクトへの読み取り専用リンクを共有できるようになりました。これには、組織外のユーザーや、組織内で Adobe Analytics 用にプロビジョニングされていないユーザーとの共有が含まれます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja#share-public-link)<p>この機能はデフォルトで有効になっており、システム管理者が無効にできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=ja#company-preferences)</p> | 2023年5月3日（PT） | 2023年6月7日（PT） |
| **分類セット — 統合** | 様々なレポートスイートの分類を組み合わせて、統合されたデータセットにします。 統合されたデータセットは、分類セットで、または CJA でルックアップデータセットとして使用できます。 詳細情報（近日公開） |  | 2023年6月7日（PT） |
| **分類セット — ルールビルダー** | 現在の分類セットアーキテクチャで分類ルールビルダーを使用します。 詳細情報（近日公開） |  | 2023年6月7日（PT） |
| **分類セット — 自動インポート** | クラウドストレージの宛先から分類セットデータを自動的に読み込めるようになりました。 詳細情報（近日公開） |  | 2023年6月7日（PT） |
| **新しい AppMeasurement 変数** | 変数 `doubleEncodeLinkParameters` は、実装がリンクトラッキング変数でマルチバイト文字をエンコードするエッジケースに対応しています。 ほとんどの実装では、この変数を定義する必要はありません。 詳細情報（近日公開） |  | 2023年6月7日（PT） |
| **データフィード書き出しの安全な宛先** | データフィードを次のクラウドストレージの宛先に送信できるようになりました。<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>以前に使用可能だった宛先 (FTP、SFTP、S3、Azure Blob) は、非推奨になりました。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=ja) |  | 2023年6月12日（PT） |
| **Workspace のボットレポート** | ボットレポートがAnalysis Workspaceで使用できるようになりました。 この機能には、次の追加が含まれます。<ul><li>新しいディメンション： [ボット名](/help/components/dimensions/bot-name.md)</li><li>2 つの新しい指標： [ボットページビュー数](/help/components/metrics/bot-page-views.md) および [ボットの発生件数](/help/components/metrics/bot-occurrences.md).</li><li>新しい計算指標テンプレート： [ボットページ表示率](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>新しい Workspace レポート：ボットレポート</li></ul>新しいディメンションと指標には、2023 年 3 月以降にバックフィルされたデータが含まれます。 |  | 7,2023年6月 |

{style="table-layout:auto"}

## その他の新機能や更新された機能 {#other}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **フリーフォームテーブルからの動的ディメンションを含む行の削除** | Analysis Workspace のフリーフォームテーブルで、「x」アイコンを使用して、動的ディメンションを含む特定の行をすばやく削除できるようになりました。その際、「常に項目を除外」フィルタールールが自動的に適用されます。<p>以前は、動的ディメンションを含む行を削除する唯一の方法は、フィルターダイアログでルールを手動で作成することでした。[詳細情報](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 該当なし | 2023年5月17日（PT） |
| **パネル内にビジュアライゼーションを追加する新しいボタン** | Analysis Workspace の各パネルの下部に新しいボタンが表示され、ビジュアライゼーションをすばやく追加できるようになりました。 <p>以前は、パネルにビジュアライゼーションを追加する唯一の方法は、左側のパネルからビジュアライゼーションをドラッグしたり、既存のビジュアライゼーションを複製またはコピーしたり、空のパネルを作成したりすることでした。[詳細情報](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 該当なし | 2023年5月17日（PT） |
| **ディープリンク（モバイルアプリ）** | ユーザーが、アプリ内のスコアカードプロジェクトに直接アクセスできるスコアカードへのリンクを送信できるようにします。これにより、プロジェクトの共有がさらに簡単になり、技術に詳しくないオーディエンスからのエンゲージメントを高めることができます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | 該当なし | 2023年5月17日（PT） |
| **動的ドロップダウンフィルター** | パネルのレポート範囲内のデータと他のドロップダウンフィルターの値に基づいて使用可能な値を決定する、新しいタイプのドロップダウンフィルターが導入されます。 動的ドロップダウンフィルターを使用するには、 [!UICONTROL Shift]. 静的ドロップダウンフィルターは、 [!UICONTROL Shift]. [詳細情報](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 2023年6月14日（PT） |
| **Analytics 学習ページを更新しました** | Adobe Analyticsのランディングページの「学習」タブで、次の機能が強化されました。<ul><li>1 つのページにより多くの学習コンテンツを表示し、ナビゲーションを改善するデザインを改善しました。</li><li>エクスペリエンスレベル（初級、中級、上級）で学習コンテンツをパーソナライズする機能</li></ul>[詳細情報](/help/analyze/landing.md) |  | 30,2023年6月 |
| **Analysis Workspace でのコンポーネントの並べ替え** | 新しい「並べ替え」オプションは、Analysis Workspace の左側のパネルまたはデータ要素でコンポーネントを表示する際に使用できるようになりました。コンポーネントは、推奨（最も一般的に使用されるコンポーネント）、アルファベット順、またはカテゴリ順（タイプ）で並べ替えることができます。<p>以前は、コンポーネントを検索またはフィルタリングすることしかできませんでした。[詳細情報](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | 該当なし | 未定 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

-311878、-313968、AN-314130、AN-315701、AN-315761、AN-316613、AN-317563、AN-318829、AN-319009、AN-319043、AN-319066、AN-、AN-、AN-319166、AN-319245、AN-319271、AN-319381、AN-319391、AN-319482、AN-319621、AN-319637、AN-319676、AN-320176、AN-320221、AN-320225、AN-320286、AN-320312、AN-320316、AN-320449、AN-320477、AN-320492、AN-320538、AN-320556、AN-320569、AN-320679、AN-320684、AN-320786、AN-320802、AN-320811、AN-320812、AN-320815、AN-321032、AN-321033、AN-321070、AN-321096、AN-321105、AN-321122、AN-321337;

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **購入 ID とイベント ID の 37 ヶ月の有効期限（イベントのシリアル化）** | 25,2023年5月 | のリリースを対象とした、Analytics のヒット処理エンジンの今後のリリース **2023 年 6 月下旬または 2023 年 7 月上旬**&#x200B;は、購入 ID とイベント ID（イベントのシリアル化）の 37 ヶ月間の有効期限の適用を開始します。 現在、購入 ID とイベント ID は、Adobe Analyticsで期限切れになることはありません。 購入 ID またはイベント ID が表示/使用されると、今後のヒットでは、いつおこなわれても、その購入またはイベントが重複としてマークされます。 新しい処理エンジンのリリースでは、次のようになります。<ul><li>購入 ID およびイベント ID は、常に 37 ヶ月後に期限切れになります。</li><li>購入 ID またはイベント ID が見つかってから 37 ヶ月が経過した場合、その購入またはイベントは重複しているとは見なされなくなりました。</li><li> 37 ヶ月以上前の購入 ID やイベント ID を「再利用」する場合、重複と見なされなくなりました。</li></ul> |
| **AdobeIO OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | AdobeIO JWT 資格情報を使用しているAdobe Analytics API および Livestream のお客様は、次の手順で AdobeIO OAuth サーバー間資格情報に移行する必要があります。 **2025 年 1 月 2 日**. 詳細とタイムラインについては、以下の表に記載されている提供終了の通知を参照してください。 |
| **ロンドンデータセンターでAdobe AnalyticsデータフィードおよびData Warehouseエグレスで使用される新しい IP** | 2023年4月27日（PT） | これは、ロンドンのデータセンターのお客様が、データフィードリクエストやData Warehouseレポートを FTP/SFTP サービスに配信している場合に関係します。 アクセスを許可するには、次の IP アドレス範囲をファイアウォール設定に追加する必要があります。 <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **AdobeIO OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | AdobeIO JWT 資格情報を使用しているAdobe Analytics API および Livestream のお客様は、次の手順で AdobeIO OAuth サーバー間資格情報に移行する必要があります。 **2025 年 1 月 2 日**. 2024 年 5 月 1 日以降、AdobeIO では新しい JWT 資格情報の作成は許可されません。 JWT を使用するお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要があります。 <ul><li>[サービスアカウント (JWT) 資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023年3月7日（PT） | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 **2023年4月**&#x200B;に、2023年12月31日（PT）以降に有効期限が切れる予定だったレポートはすべて自動的に更新され、2023年12月31日（PT）に有効期限が切れるように戻されます。 また、2023年12月31日（PT）以降は今後のレポートをスケジュールできなくなります。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2022年9月29日 | Reports &amp; Analytics の提供終了（EOL）の一環として、[!UICONTROL パブリッシュリスト]は **2023年12月** に提供終了になる予定です。新しいパブリッシュリストを作成するか既存の[!UICONTROL パブリッシュリスト]にアクセスして、[!UICONTROL Analysis Workspace] プロジェクトを送信したりスケジュールしたりすることはできなくなります。 |
| **Data Workbench のサポート終了** | 2022年9月14日 | **2023年12月31日**&#x200B;をもって、アドビは Data Workbench のサポートを終了する予定です。詳しくは、[Data Workbench の提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.23.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。


## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
