---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5ed1ff0ecee4843f866b1a911e2cb5f14310c58a
workflow-type: tm+mt
source-wordcount: '1444'
ht-degree: 87%

---

# 現在の Adobe Analytics リリースノート (2023年3月)

**最終更新日**：2023年4月3日

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## Adobe Analytics の新機能または更新された機能 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace でのデータ要素** | データ要素は、ユーザーと管理者の両方が Analytics 環境のコンポーネント（ディメンション、指標）を追跡、管理、そしてよりよく理解するのに役立ちます。[詳細情報](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023年3月15日（PT） | 2023年3月29日（PT） |
| **モバイルダッシュボードのデータストーリー** | データストーリーを使用すると、カスタマイズ可能な複数の詳細ビューをモバイルスコアカードプロジェクトのタイルに追加できます。 データストーリーを使用すると、カスタマージャーニーにおける主な推進要因、関連指標、様々な手順をより詳しく確認できます。これらのビューを簡単にスワイプすると、主要指標の背後にある全体像を把握できます。 [詳細情報](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | 該当なし | 2023年3月8日（PT） |
| **スケジュールされたプロジェクトの有効期限** | スケジュールの頻度に関係なく、スケジュールされたプロジェクトの最大有効期限を 1 年まで設定できます。 | 該当なし | 2023年3月8日（PT） |
| **プロジェクトのリンク共有（ログインは不要）** - プライベートベータ版へのアクセスのみ | <p>Adobe Analytics へのアクセス権を持たないユーザーと、Analysis Workspace プロジェクトへの読み取り専用リンクを共有できるようになりました。 プロジェクトのリンクは、組織外のユーザーや、組織内で Adobe Analytics 用にプロビジョニングされていないユーザーと共有できます。 [詳細情報](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>プライベートベータ版に参加するには、アドビアカウントチームにお問い合わせください。</p> | 2023年3月15日（PT）（プライベートベータ版） | 2023年4月 |
| **パネルの日付範囲の更新** | ワークスペースに、次の機能強化が追加されました。<ul><li>2 月のリリース以降、ディメンションとデータのプレビューは、過去 90 日間ではなく、パネルの日付範囲に基づきます。 </li><li>表示されるすべてのディメンション項目は、パネルの日付範囲内のデータに基づきます。ディメンション項目に日付範囲外のデータが含まれる場合は、リストの下部に、日付範囲外の追加データを表示できます。</li><li> データのないディメンションは、左側のパネルに表示できます。「その他のオプションを表示」をクリックすると、パネルの日付範囲外のデータを含むディメンション項目が表示されます。</li><li>グメントおよび計算指標ビルダーのすべての日付プレビューは、パネルの日付範囲に基づきます（関連付けられたパネルがないコンポーネントマネージャーからアクセスしない限り、過去 90 日間に基づきます）。</li><li>データプレビューでは、パネルの日付範囲に基づいて、データやコンポーネントが表示されます。</li></ul> | 該当なし | 2023年2月8日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

AN-308177、AN-308727、AN-308846、AN-309591、AN-310614、AN-311544、AN-311570、AN-311665、AN-311948、AN-312108、AN-312114、AN-312142、AN-312143、AN-312389、AN-312391、AN-312431、AN-312453、AN-312454、AN-312458、AN-312503、AN-312533、AN-312682、AN-312698、AN-312714、AN-312738、AN-312807、AN-312829、AN-312849、AN-312875、AN-312980、AN-312997、AN-313059、AN-313077、AN-313110、AN-313195、AN-313196、AN-313258、AN-313554、AN-313580、AN-313702、AN-313820、AN-313844、AN-313859、AN-313879、AN-314273

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **デバイス検索プロセスでは、すべてのデバイス検索でサードパーティが使用されるようになりました。** | 2023年3月3日（PT） | 2023 年 3 月 2 日に、クライアントヒントのサポート展開の一環として、すべてのデバイス検索にサードパーティを使用するようにデバイス検索プロセスを更新しました。 以前は、モバイルデバイスの検索にのみサードパーティを使用していました。 このロールアウトの一環で、一部のデスクトップオペレーティングシステムには、「モバイル」という誤ったラベルが付けられていました ( 例：&quot;OS X 10.15.7&quot;ではなく&quot;Mobile OS X 10.15.7&quot;)<p>Adobeの 4 月のリリースで、これらの名前を修正します。 Analytics と CJA のレポートは、イベントデータの一部として記録された ID に基づいてオペレーティングシステム名を検索するので、過去に遡って更新されます。 ID に対応するルックアップ値が更新されると、履歴データを含め、すべてのレポートが修正されます。 の場合 [!UICONTROL データフィード] のお客様は、レポート時に同様の検索プロセスを使用している場合、変更が遡及されます。 ただし、オペレーティングシステムの値をイベントデータに保存した場合、レポートは今後のみ更新されます。 詳しくは、 [オペレーティングシステム](/help/components/dimensions/operating-systems.md) を参照してください。 |
| **Google クライアントヒントによるデバイス検索の更新** | 2023年2月27日（PT） | 2023年2月16日（PT）に予定されていたクライアントヒントの使用は、ヒントを使用したデバイス検索の品質を向上させるために延期されました。2023年2月27日（PT）に、クライアントヒントのサポートに関するリリースの第 1 段階が完了しました。 2023年3月2日（木）（PT）に、リリースの第 2 期と最終段階が完了しました。 [詳細情報](/help/technotes/client-hints.md) |
| **Analytics ソースコネクタの可用性** | 2023年2月15日（PT） | 2023年2月28日（PT）に、カナダにある Adobe Experience Platform 新規データセンターで Analytics ソースコネクタの利用が可能になりました。 |
| **分類セットアーキテクチャへの自動移行** | 2023年2月8日（PT） | アドビは今後数か月で、すべての組織をまたいですべての分類を最新の分類アーキテクチャに移行する予定です。移行する最後のお客様は、2023年5月に発生すると推定されています。お客様のアクションは必要なく、ダウンタイムも予想されません。この新しいアーキテクチャには、次のように多くの利点があります。<ul><li>処理時間が大幅に短縮されました（72 時間 → 24 時間）</li><li>[分類セット](/help/components/classifications/sets/overview.md) UI を使用する機能</li><li>[分類データ用の Adobe Analytics ソース コネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=ja)を介して、今後 Adobe Experience Platform で分類データを使用するオプション</li></ul>組織のワークフローに影響を与える可能性がある次の変更に注意してください。<ul><li>ブラウザーまたは FTP 読み込みを使用する場合、「[!UICONTROL 競合時に上書き]」は常に有効になっています。</li><li>ブラウザーまたは FTP 読み込みを使用する場合、読み込み直後に書き出すオプションはサポートされなくなりました。</li><li>Analytics 2.0 API `GetDimensions` エンドポイントは、数値識別子ではなく、分類の文字列識別子を返すようになりました。数値識別子は引き続き使用できますが、アドビでは可能な限り新しい文字列識別子を使用することをお勧めします。数値識別子は、`?expansion=hidden` クエリ文字列パラメーターを使用して取得できます。</li></ul>組織のより具体的な移行スケジュールが必要な場合、またはこの移行に関して質問や懸念がある場合は、アドビカスタマーケアにお問い合わせください。[詳細情報](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **日本のガラケー計測 (mod_ktrack) サービスのサポート終了** | 2023年3月21日（PT） | 長らくご利用いただいておりましたガラケー計測 (mod_ktrack) につきまして、2023年5月末日をもちましてサービスを終了させていただくこととなりました。ご利用中のお客様にはお手数をおかけして誠に申し訳ございませんが、Apache サーバーに組み込んでいただいているモジュールをアンインストールしていただきますようお願い申し上げます。アンインストール方法につきましては添付資料の 27ページ、28ページをご参照ください。[添付資料](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) 。本件に関してご不明な点がございましたら、所定のサポート窓口、または担当のカスタマーサクセスマネージャーへお問い合わせお願いいたします。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023年3月7日（PT） | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023年12月31日（PT）に、関連する Reports &amp; Analytics 機能の多くを終了します。これには、予定レポート、データ抽出、DL レポートが含まれますが、これらに限定されるものではありません。2023年12月31日（PT）以降、予定レポートは送信されなくなります。 **2023年4月**&#x200B;に、2023年12月31日（PT）以降に有効期限が切れる予定だったレポートはすべて自動的に更新され、2023年12月31日（PT）に有効期限が切れるように戻されます。 また、2023年12月31日（PT）以降は今後のレポートをスケジュールできなくなります。 |
| **[!UICONTROL 人物]指標の提供終了（EOL）** | 2023年3月9日（PT） | [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=ja) の廃止に伴い、Device Co-op 関連の人物指標は関係がなくなりました。2023 年 5 月 8 日に、 [!UICONTROL People] 指標を削除します。その時点で、そのデータを[!UICONTROL ユニーク訪問者]指標にリダイレクトして、プロジェクト、セグメントおよび計算指標が壊れないようにします。<p>**メモ**：クロスデバイス分析に関連付けられている[[!UICONTROL 人物]指標](/help/components/metrics/people.md)は、この発表の影響を受けません。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2022年9月29日 | Reports &amp; Analytics の提供終了（EOL）の一環として、[!UICONTROL パブリッシュリスト]は **2023年12月** に提供終了になる予定です。新しいパブリッシュリストを作成するか既存の[!UICONTROL パブリッシュリスト]にアクセスして、[!UICONTROL Analysis Workspace] プロジェクトを送信したりスケジュールしたりすることはできなくなります。 |
| **Data Workbench のサポート終了** | 2022年9月14日 | **2023年12月31日**&#x200B;をもって、アドビは Data Workbench のサポートを終了する予定です。詳しくは、[Data Workbench の提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日 | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.23.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。


## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
