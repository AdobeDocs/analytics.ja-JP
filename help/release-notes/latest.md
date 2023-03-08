---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ccb40e45ea559db815f4252d85baa61b9e109024
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 55%

---

# 現在の Adobe Analytics リリースノート (2023年3月)

**最終更新日**：2023年3月7日（PT）

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## Adobe Analytics の新機能または更新された機能 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspaceのデータ辞書** | データディクショナリは、ユーザーと管理者の両方が、Analytics 環境のコンポーネント（ディメンション、指標）を追跡、管理し、より深く理解するのに役立ちます。 [詳細情報](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 16 日 | 2023 年 3 月 23 日 |
| **モバイルダッシュボードのデータストーリー** | データストーリーを使用すると、カスタマイズ可能な複数の詳細ビューをモバイルスコアカードプロジェクトのタイルに追加できます。 データストーリーを使用して、カスタマージャーニーにおける主な推進要因、関連指標、様々な手順を詳しく調べます。 これらのビューを簡単にスワイプして、主要指標の背後にある全体像を把握できます。 詳細情報（フォロー） | 該当なし | 2023 年 3 月 9 日 |
| **スケジュールされたプロジェクトの有効期限** | スケジュールの頻度に関係なく、スケジュールされたプロジェクトの最大有効期限日は最大 1 年に設定できます。 | 該当なし | 2023 年 3 月 9 日 |
| **プロジェクトのリンク共有（ログインは不要）**  — プライベートベータアクセスのみ | <p>Adobe Analyticsへのアクセス権を持たないユーザーと、Analysis Workspaceプロジェクトへの読み取り専用リンクを共有できるようになりました。 プロジェクトのリンクは、組織外の人や、組織内でAdobe Analytics用にプロビジョニングされていない人と共有できます。 [詳細情報](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>プライベートベータ版に参加するには、Adobeアカウントチームにお問い合わせください。</p> | 2023 年 3 月 16 日（プライベートベータ版） | 2023 年 4 月 |

## Adobe Analytics の修正点

AN-308177;AN-308727;AN-308846;AN-309591;AN-310614;AN-311544;AN-311570;AN-311665;AN-311948;AN-312108;AN-312114;AN-312142;AN-312143;AN-312389;AN-312391;AN-312431;AN-312453;AN-312454;AN-312458;AN-312503;AN-312533;AN-312682;AN-312698;AN-312714;AN-312738;AN-312807;AN-312829;AN-312849;AN-312875;AN-312980;AN-312997;AN-313059;AN-313077;AN-313110;AN-313195;AN-313196;AN-313258;AN-313554;AN-313580;AN-313702;AN-313820;AN-313844;AN-313859;AN-313879;AN-314273

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **Google クライアントヒントによるデバイス検索の更新** | 2023年2月27日（PT） | 2023 年 2 月 16 日に予定されていたクライアントヒントの使用は、ヒントを使用したデバイス検索の品質をより確実にするために延期されました。 2023 年 2 月 27 日に、Client Hints のサポートに関するリリースの第 1 段階を完了しました。 リリースの第 2 期と最終段階は 2023 年 3 月 2 日（木）に完了しました。 [詳細情報](/help/technotes/client-hints.md) |
| **Analytics Source Connector の可用性** | 2023年2月15日（PT） | 2023 年 2 月 28 日に、カナダにある新しいAdobe Experience Platformデータセンターで Analytics ソースコネクタの利用が可能になりました。 |
| **分類セットアーキテクチャへの自動移行** | 2023年2月8日（PT） | アドビは今後数か月で、すべての組織をまたいですべての分類を最新の分類アーキテクチャに移行する予定です。移行する最後のお客様は、2023年5月に発生すると推定されています。お客様のアクションは必要なく、ダウンタイムも予想されません。この新しいアーキテクチャには、次のように多くの利点があります。<ul><li>処理時間が大幅に短縮されました（72 時間 → 24 時間）</li><li>[分類セット](/help/components/classifications/sets/overview.md) UI を使用する機能</li><li>[分類データ用の Adobe Analytics ソース コネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=ja)を介して、今後 Adobe Experience Platform で分類データを使用するオプション</li></ul>組織のワークフローに影響を与える可能性がある次の変更に注意してください。<ul><li>ブラウザーまたは FTP 読み込みを使用する場合、「[!UICONTROL 競合時に上書き]」は常に有効になっています。</li><li>ブラウザーまたは FTP 読み込みを使用する場合、読み込み直後に書き出すオプションはサポートされなくなりました。</li><li>Analytics 2.0 API `GetDimensions` エンドポイントは、数値識別子ではなく、分類の文字列識別子を返すようになりました。数値識別子は引き続き使用できますが、アドビでは可能な限り新しい文字列識別子を使用することをお勧めします。数値識別子は、`?expansion=hidden` クエリ文字列パラメーターを使用して取得できます。</li></ul>組織のより具体的な移行スケジュールが必要な場合、またはこの移行に関して質問や懸念がある場合は、アドビカスタマーケアにお問い合わせください。[詳細情報](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **[!DNL Reports & Analytics]** のサポート終了 | 2023 年 3 月 8 日 | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。<p>2023 年 12 月 31 日に、次の機能を含む、（ただし、これらに限定されない）関連する Reports &amp; Analytics の機能の多くを終了します。予定レポート、データ抽出、DL レポート 2023 年 12 月 31 日以降、予定レポートは送信されなくなります。 In **2023 年 4 月**&#x200B;に設定されている場合、2023 年 12 月 31 日以降に期限が切れる予定のレポートは自動的に更新され、2023 年 12 月 31 日に期限切れに戻されます。 また、2023 年 12 月 31 日以降、今後のレポートのスケジュールを設定することはできなくなります。 |
| **の EOL [!UICONTROL 人] 指標** | 2023年2月28日（PT） | 廃止された [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html)に値を入力しない場合、 Device Co-op 関連の人物指標は関連性がなくなりました。 近い将来（TBD 日）、これを削除します [!UICONTROL 人] 指標。 その時点で、データをにリダイレクトします。 [!UICONTROL 個別訪問者] 指標を使用して、プロジェクト、セグメントおよび計算指標が壊れないようにします。<p>**注意**:この [[!UICONTROL 人] 指標をクロスデバイス分析に結び付け](/help/components/metrics/people.md) はこのお知らせの影響を受けません。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2022年9月29日 | Reports &amp; Analytics のサポート終了の一環として、 [!UICONTROL 発行リスト] は、 **2023 年 12 月**. 新規を作成したり、既存のにアクセスすることはできません [!UICONTROL 発行リスト] 送信する、またはスケジュールする [!UICONTROL Analysis Workspace] プロジェクト。 |
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
