---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f4cf651e07da27c416fc02b184b80bc07756eb33
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 75%

---

# 現在の Adobe Analytics リリースノート (2023年4月)

**最終更新日**：2023年4月12日

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## Adobe Analytics の新機能または更新された機能 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analytics ソースコネクタストリーミングの行／列フィルタリング** | Adobe Experience Platform の Analytics ソースコネクタを使用すると、[リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)におけるプロファイルへの入力に使用される Analytics データをフィルタリングできるようになりました。行レベルのフィルタリングは、プロファイルに関連付けられたイベントの数を減らすのに役立ちます。列レベルのフィルタリングは、イベント自体の豊富さを軽減するのに役立つので、プロファイル使用権限の行使を最適化できます。このフィルタリングは、リアルタイム顧客プロファイルと [ID サービス](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja)に送信されるデータにのみ適用されます。**フィルタリングは、Customer Journey Analytics などのアプリケーションで使用するためにデータレイクに送信されるデータには影響しません**。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja#filtering-for-profile) | 該当なし | 2023年3月29日（PT） |
| **Web SDK を使用したActivity Mapの部分的なサポート** | Web SDK バージョン2.15.0以降、リンクトラッキングが有効な場合に、Activity Mapデータの生成を開始しました。 これにより、Web SDK および Analytics で設定された Web SDK とActivity Mapでリンクトラッキングが有効になっている場合に、Web SDK ユーザーがActivity Mapレポートを取得できます。<p>現在、顧客がページ間を移動すると、Web SDK でのリンクトラッキングがリンクイベントを送信しています。 これは、AppMeasurement の動作方法とは異なり、追加の課金対象ヒットがAdobeに送信される可能性があります。 詳細情報 [ここ](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja) および [ここ](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) | 該当なし | 2023年31月3日（PT） |
| **Experience Edge の IP 難読化** | Experience Edge は、Adobe Experience Platformに直接送信されるデータの IP 難読化をサポートします。 これにより、CJA や他の Platform ソリューションで使用するために Platform に直接データを送信するお客様にメリットがあります。 IP の不明化は、データストリームレベルで設定します。 最後のオクテットまたは IP アドレス全体の削除をサポートします。<p>**注意**:難読化は、Adobe Analyticsに送信されるデータには適用されません。 Analytics は引き続き完全な IP を取得します。 IP 処理は、引き続き Analytics で個別におこなわれます。 今後、Analytics データは Edge で不明化される予定です。 | 該当なし | AEP リリース（2023 年 4 月 27 日） |
| **Analysis Workspace でのデータ要素** | データ要素は、ユーザーと管理者の両方が Analytics 環境のコンポーネント（ディメンション、指標）を追跡、管理、そしてよりよく理解するのに役立ちます。[詳細情報](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023年3月15日（PT） | 2023年3月29日（PT） |
| **プロジェクトのリンク共有（ログインは不要）** - プライベートベータ版へのアクセスのみ | <p>Adobe Analytics へのアクセス権を持たないユーザーと、Analysis Workspace プロジェクトへの読み取り専用リンクを共有できるようになりました。 プロジェクトのリンクは、組織外のユーザーや、組織内で Adobe Analytics 用にプロビジョニングされていないユーザーと共有できます。 [詳細情報](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>プライベートベータ版に参加するには、アドビアカウントチームにお問い合わせください。</p> | 2023 年 4 月 27 日 | 2023年6月 |
| Adobe Analytics 2.0 API 向けの 2 つの新しいエンドポイントガイド | <ul><li>[AnalyticsDimensionAPI](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)</li><li>[Analytics 指標 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/metrics/)</li></ul> | 該当なし | 2023 年 4 月 11 日 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* データフィードの Operating System.tsv 参照ファイルの問題を修正しました。
* Reports &amp; Analytics と Workspace で指標の値が異なる問題を修正しました。(AN-315965)
* 部分分類をインポートできない問題を修正しました。 (AN-315854)
* Analytics API 1.4 の問題を修正しました。 (AN-316475)
* 一部のお客様が「Report Builder」および「Report &amp; Analytics」を使用してページディメンションの分類を取得できない問題を修正しました。 (AN-314445)
* アラートを転送できない問題を修正しました。 (AN-306457)

### その他の修正点

AN-288373;AN-305144;AN-309023;AN-310466;AN-311686;AN-311705;AN-312018;AN-312105;AN-312116;AN-312191;AN-312502;AN-312737;AN-312854;AN-312991;AN-313253;AN-313275;AN-313278;AN-313282;AN-313365;AN-313390;AN-313547;AN-313549;AN-313818;AN-313986;AN-314080;AN-314248;AN-314251;AN-314262;AN-314300;AN-314309;AN-314448;AN-314643;AN-314564;AN-314645;AN-314705;AN-314761;AN-314831;AN-314919;AN-314948;AN-315032;AN-315115;AN-315154;AN-315158;AN-315321;AN-315375;AN-315379;AN-315392;AN-315407;AN-315427;AN-315582;AN-315591;AN-315699;AN-315700;AN-315704;AN-315705;AN-315777;AN-315923;AN-316237;AN-316243;AN-316324;AN-316415;AN-316474;AN-316493;AN-316596;AN-316864;

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **デバイス検索プロセスでは、すべてのデバイス検索にサードパーティを使用するようになりました** | 2023年3月3日（PT） | 2023年3月2日（PT）に、クライアントヒントのサポートロールアウトの一環として、すべてのデバイス検索にサードパーティを使用するようにデバイス検索プロセスを更新しました。以前は、モバイルデバイスの検索にのみサードパーティを使用していました。そのロールアウトの一環として、一部のデスクトップオペレーティングシステムは、「Mobile」というテキストで誤ってラベル付けされていました（例えば、「OS X 10.15.7」ではなく「Mobile OS X 10.15.7」）。<p>アドビの 4月のリリース時に、これらの名前を修正する予定です。Analytics と CJA のレポートは、イベントデータの一部として記録された ID に基づいてオペレーティングシステム名を検索するので、遡及的に更新されます。ID に対応する検索値を更新すると、履歴データを含むすべてのレポートが修正されます。[!UICONTROL データフィード]のお客様の場合は、レポート時に同様の検索プロセスを使用している場合、変更は遡及的に適用されます。ただし、オペレーティングシステムの値をイベントデータに保存した場合、レポートはそれ以降にのみ更新されます。詳しくは、[オペレーティングシステム](/help/components/dimensions/operating-systems.md)を参照してください。 |
| **Google クライアントヒントによるデバイス検索の更新** | 2023年2月27日（PT） | 2023年2月16日（PT）に予定されていたクライアントヒントの使用は、ヒントを使用したデバイス検索の品質を向上させるために延期されました。2023年2月27日（PT）に、クライアントヒントのサポートに関するリリースの第 1 段階が完了しました。 2023年3月2日（木）（PT）に、リリースの第 2 期と最終段階が完了しました。 [詳細情報](/help/technotes/client-hints.md) |
| **分類セットアーキテクチャへの自動移行** | 2023年2月8日（PT） | アドビは今後数か月で、すべての組織をまたいですべての分類を最新の分類アーキテクチャに移行する予定です。移行する最後のお客様は、2023年5月に発生すると推定されています。お客様のアクションは必要なく、ダウンタイムも予想されません。この新しいアーキテクチャには、次のように多くの利点があります。<ul><li>処理時間が大幅に短縮されました（72 時間 → 24 時間）</li><li>[分類セット](/help/components/classifications/sets/overview.md) UI を使用する機能</li><li>[分類データ用の Adobe Analytics ソース コネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=ja)を介して、今後 Adobe Experience Platform で分類データを使用するオプション</li></ul>組織のワークフローに影響を与える可能性がある次の変更に注意してください。<ul><li>ブラウザーまたは FTP 読み込みを使用する場合、「[!UICONTROL 競合時に上書き]」は常に有効になっています。</li><li>ブラウザーまたは FTP 読み込みを使用する場合、読み込み直後に書き出すオプションはサポートされなくなりました。</li><li>Analytics 2.0 API `GetDimensions` エンドポイントは、数値識別子ではなく、分類の文字列識別子を返すようになりました。数値識別子は引き続き使用できますが、アドビでは可能な限り新しい文字列識別子を使用することをお勧めします。数値識別子は、`?expansion=hidden` クエリ文字列パラメーターを使用して取得できます。</li></ul>組織のより具体的な移行スケジュールが必要な場合、またはこの移行に関して質問や懸念がある場合は、アドビカスタマーケアにお問い合わせください。[詳細情報](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **日本のガラケー計測 (mod_ktrack) サービスのサポート終了** | 2023年3月21日（PT） | 日本のお客様のみ：次の場合： **2023 年 5 月末**&#x200B;に設定しない場合、日本語機能電話トラッキングサービス (mod_ktrack) は廃止されます。 ご利用中のお客様にはお手数をおかけして誠に申し訳ございませんが、Apache サーバーに組み込んでいただいているモジュールをアンインストールしていただきますようお願い申し上げます。アンインストール方法につきましては添付資料の 27ページ、28ページをご参照ください。[添付資料](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) 。本件に関してご不明な点がございましたら、所定のサポート窓口、または担当のカスタマーサクセスマネージャーへお問い合わせお願いいたします。 |
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
