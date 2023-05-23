---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 8856293e4f0114245e32db16809a964ccac5430f
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 86%

---

# 現在の Adobe Analytics リリースノート（2023年5月）

**最終更新日**：2023年5月17日（PT）

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## Adobe Analytics の新機能または更新された機能 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **非実稼動用サンドボックスのバックフィル** | 非実稼動用サンドボックスで Analytics ソースコネクタのデータフローを作成する場合、非実稼動用サンドボックスでのバックフィルは 3 か月に制限されます。実稼動用サンドボックスの場合、13 か月間の状態が保たれます。 | 該当なし | 2023年4月26日（PT） |
| **プロジェクトのリンク共有（ログインは不要）** | Adobe Analytics へのアクセス権を持たないユーザーと、Analysis Workspace プロジェクトへの読み取り専用リンクを共有できるようになりました。これには、組織外のユーザーや、組織内で Adobe Analytics 用にプロビジョニングされていないユーザーとの共有が含まれます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=ja#share-public-link)<p>この機能はデフォルトで有効になっており、システム管理者が無効にできます。[詳細情報](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=ja#company-preferences)</p> | 2023年5月3日（PT） | 2023年6月 |
| **Analytics ダッシュボードアプリ（モバイルアプリ）の更新されたホーム画面** | 新しく更新されたホーム画面では、すべてのスコアカードを 1 つの統合されたスコアカードリストで表示できます。1 回のログインで複数の組織にアクセスできる場合、組織のすべてのスコアカードが 1 つのリストで使用できるようになります。 | 該当なし | 2023年5月10日（PT） |
| **Analysis Workspace でのコンポーネントの並べ替え** | 新しい「並べ替え」オプションは、Analysis Workspace の左側のパネルまたはデータ要素でコンポーネントを表示する際に使用できるようになりました。コンポーネントは、推奨（最も一般的に使用されるコンポーネント）、アルファベット順、またはカテゴリ順（タイプ）で並べ替えることができます。<p>以前は、コンポーネントを検索またはフィルタリングすることしかできませんでした。[詳細情報](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | 該当なし | 未定 |
| **フリーフォームテーブルからの動的ディメンションを含む行の削除** | Analysis Workspace のフリーフォームテーブルで、「x」アイコンを使用して、動的ディメンションを含む特定の行をすばやく削除できるようになりました。その際、「常に項目を除外」フィルタールールが自動的に適用されます。<p>以前は、動的ディメンションを含む行を削除する唯一の方法は、フィルターダイアログでルールを手動で作成することでした。[詳細情報](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 該当なし | 2023年5月17日（PT） |
| **パネル内にビジュアライゼーションを追加する新しいボタン** | Analysis Workspace の各パネルの下部に新しいボタンが表示され、ビジュアライゼーションをすばやく追加できるようになりました。 <p>以前は、パネルにビジュアライゼーションを追加する唯一の方法は、左側のパネルからビジュアライゼーションをドラッグしたり、既存のビジュアライゼーションを複製またはコピーしたり、空のパネルを作成したりすることでした。[詳細情報](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 該当なし | 2023年5月17日（PT） |
| **ディープリンク（モバイルアプリ）** | ユーザーが、アプリ内のスコアカードプロジェクトに直接アクセスできるスコアカードへのリンクを送信できるようにします。これにより、プロジェクトの共有がさらに簡単になり、技術に詳しくないオーディエンスからのエンゲージメントを高めることができます。 | 該当なし | 2023年5月17日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

AN-312098、AN-318309、AN-316675、AN-318173、AN-310359、AN-317613、AN-318836、AN-315744、AN-311772、AN-318719、AN-314074、AN-316651<!--"Verified" status-->、AN-318602、AN-315961、AN-317534、AN-318607、AN-316498、AN-316648、AN-318244、AN-317747、AN-318432、AN-318231、AN-317590、AN-318415、AN-318154、AN-316647、N-314417、AN-317614、AN-317725、AN-318114、AN-317876、AN-318052、AN-317966、AN-316477、AN-318036、AN-317931、AN-318045、AN-316246、AN-317281、AN-317879、AN-308077、AN-317708、AN-316115、AN-315963

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **AdobeIO OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | AdobeIO JWT 資格情報を使用しているAdobe Analytics API および Livestream のお客様は、次の手順で AdobeIO OAuth サーバー間資格情報に移行する必要があります。 **2025 年 1 月 2 日**. 詳細とタイムラインについては、以下の表に記載されている提供終了の通知を参照してください。 |
| **通知：ロンドンデータセンターの Adobe Analytics データフィードおよび Data Warehouse エグレスで新しい IP が使用されます** | 2023年4月27日（PT） | ロンドンデータセンターのお客様で、データフィードリクエストや Data Warehouse レポートを FTP/SFTP サービスに配信している場合、アクセスを許可するために、次の IP アドレス範囲をファイアウォール設定に追加する必要があります。 <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
| **デバイス検索プロセスでは、すべてのデバイス検索にサードパーティを使用するようになりました** | 2023年3月3日（PT） | 2023年3月2日（PT）に、クライアントヒントのサポートロールアウトの一環として、すべてのデバイス検索にサードパーティを使用するようにデバイス検索プロセスを更新しました。以前は、モバイルデバイスの検索にのみサードパーティを使用していました。そのロールアウトの一環として、一部のデスクトップオペレーティングシステムは、「Mobile」というテキストで誤ってラベル付けされていました（例えば、「OS X 10.15.7」ではなく「Mobile OS X 10.15.7」）。<p>アドビの 4月のリリース時に、これらの名前を修正する予定です。Analytics と CJA のレポートは、イベントデータの一部として記録された ID に基づいてオペレーティングシステム名を検索するので、遡及的に更新されます。ID に対応する検索値を更新すると、履歴データを含むすべてのレポートが修正されます。の場合 [!UICONTROL データフィード] のお客様は、レポート時に同様のルックアッププロセスを使用している場合、変更が遡及されます。 ただし、オペレーティングシステムの値をイベントデータに保存した場合、レポートはそれ以降にのみ更新されます。詳しくは、[オペレーティングシステム](/help/components/dimensions/operating-systems.md)を参照してください。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **AdobeIO OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | AdobeIO JWT 資格情報を使用しているAdobe Analytics API および Livestream のお客様は、次の手順で AdobeIO OAuth サーバー間資格情報に移行する必要があります。 **2025 年 1 月 2 日**. 2024 年 5 月 1 日以降、AdobeIO では新しい JWT 資格情報の作成は許可されません。 JWT を使用するお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要があります。 <ul><li>[サービスアカウント (JWT) 資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |
| **日本のガラケー計測 (mod_ktrack) サービスのサポート終了** | 2023年3月21日（PT） | 日本のお客様へ：**2023年5月末日**&#x200B;をもちまして、日本製フィーチャーフォントラッキングサービス（mod_ktrack）のサービスを終了させていただくこととなりました。ご利用中のお客様にはお手数をおかけして誠に申し訳ございませんが、Apache サーバーに組み込んでいただいているモジュールをアンインストールしていただきますようお願い申し上げます。アンインストール方法につきましては添付資料の 27ページ、28ページをご参照ください。[添付資料](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf)。本件に関してご不明な点がございましたら、所定のサポート窓口、または担当のカスタマーサクセスマネージャーへお問い合わせお願いいたします。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023年3月7日（PT） | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 **2023年4月**&#x200B;に、2023年12月31日（PT）以降に有効期限が切れる予定だったレポートはすべて自動的に更新され、2023年12月31日（PT）に有効期限が切れるように戻されます。 また、2023年12月31日（PT）以降は今後のレポートをスケジュールできなくなります。 |
| **[!UICONTROL 人物]指標の提供終了（EOL）** | 2023年3月9日（PT） | [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=ja) の廃止に伴い、Device Co-op 関連の人物指標は関係がなくなりました。2023 年 5 月 8 日に、 [!UICONTROL People] 指標を削除します。その時点で、そのデータを[!UICONTROL ユニーク訪問者]指標にリダイレクトして、プロジェクト、セグメントおよび計算指標が壊れないようにします。<p>**メモ**：クロスデバイス分析に関連付けられている[[!UICONTROL 人物]指標](/help/components/metrics/people.md)は、この発表の影響を受けません。 |
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
