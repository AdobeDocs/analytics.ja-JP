---
title: 最新の Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示します。
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6d2042359e1ee97ebed0077c9faeceb2cb0fe739
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 53%

---

# 現在の Adobe Analytics リリースノート (2023年2月)

**最終更新日**：2023年2月27日（PT）

Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## Adobe Analytics の新機能または更新された機能

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **データプライバシーラベルのユーザーインターフェイスを更新しました** | 更新されたインターフェイスは、レポートスイートコンポーネントのデータプライバシーラベルの作成、管理および編集のプロセスを合理化します。 [詳細情報](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | 該当なし | 2023年2月8日（PT） |
| **モバイルスコアカードでの比較日付範囲の非表示** | モバイルスコアカードでは、 **[!UICONTROL 比較日を含める]** の設定を使用して比較日を表示または非表示にすることができます。 | 該当なし | 2023年2月8日（PT） |
| **Workspace でのカレンダーの更新** | <ul><li>パネルの日付の固定：パネルカレンダーを基準とする相対的な日付範囲コンポーネントにすることができます。[詳細情報](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>カレンダースタイルの更新：UI 全体を通してカレンダースタイルがアップグレードされて、より一貫性のある使いやすいワークフローが提供されるようになりました。</li><li>カレンダー式の更新：相対的な日付を使用する場合は、すべてのカレンダー式にパネルの日付範囲の開始日が反映されます。[詳細情報](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | 該当なし | 2023年2月8日（PT） |
| **パネルの日付範囲の更新** | Workspace で、次の機能強化が追加されました。<ul><li>2 月のリリース以降、コンポーネントとデータのプレビューは、過去 90 日間ではなく、パネルの日付範囲に基づいておこなわれます。 </li><li>左側のパネルに表示されるすべてのコンポーネントは、パネルの日付範囲に基づいて使用できます。</li><li>セグメントおよび計算指標ビルダーのすべての日付プレビューは、パネルの日付範囲に基づきます（関連するパネルがないコンポーネントマネージャーからアクセスしない限り、過去 90 日間の日付が基になります）。</li><li>データプレビューでは、パネルの日付範囲に基づいて、データやコンポーネントが表示されます。</li></ul> | 該当なし | 2023年2月8日（PT） |
| **Adobe Analytics ソースコネクタストリーミングの行／列フィルタリング** | Adobe Experience Platform の Analytics ソースコネクタを使用すると、[リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)におけるプロファイルへの入力に使用される Analytics データをフィルタリングできるようになりました。行レベルのフィルタリングは、プロファイルに関連付けられたイベントの数を減らすのに役立ちます。列レベルのフィルタリングは、イベント自体の豊富さを軽減するのに役立つので、プロファイル使用権限の行使を最適化できます。このフィルタリングは、リアルタイム顧客プロファイルと [ID サービス](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja)に送信されるデータにのみ適用されます。**フィルタリングは、Customer Journey Analytics などのアプリケーションで使用するためにデータレイクに送信されるデータには影響しません**。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja#filtering-for-profile) | 該当なし | 2023 年 3 月 30 日に再スケジュールされました |

{style=&quot;table-layout:auto&quot;}

## Adobe Analytics の修正点

-302282、AN-303127、AN-303541、AN-303550、AN-305282、AN-306504、AN-307351、AN-307496、AN-307530、AN-307947、AN-308497、AN-、AN-308610、AN-308777、AN-308994、AN-309143、AN-309404、AN-309414、AN-309445、AN-309575、AN-309630、AN-309658、AN-309690、AN-309742、AN-309861、AN-309967、AN-309973、AN-310059、AN-310132、AN-310168、AN-310238、AN-310241、AN-310301、AN-310318、AN-310324、AN-310335、AN-310338、AN-310460、AN-310500、AN-310684、AN-310690、AN-311010、AN-311022、AN-311043、AN-311125、AN-311250、AN-311370、AN-311458;

## Adobe Analytics 管理者向けの重要な注意事項

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **Google クライアントヒントによるデバイス検索の更新** | 2023年2月27日（PT） | 2023 年 2 月 16 日に予定されていたクライアントヒントの使用は、ヒントを使用したデバイス検索の品質をより確実にするために延期されました。 2023 年 2 月 27 日に、クライアントヒントのサポートに関するリリースの第 1 段階を進めます。 問題が解決した場合は、2023 年 3 月 2 日（木）のリリースの第 2 段階と最終段階に進みます。 [詳細情報](/help/technotes/client-hints.md) |
| **Analytics Source Connector の可用性** | 2023年2月15日（PT） | 2023 年 2 月 28 日に、カナダにある新しいAdobe Experience Platformデータセンターで Analytics ソースコネクタを利用できるようになります。 |
| **分類セットアーキテクチャへの自動移行** | 2023年2月8日（PT） | 今後数ヶ月の間に、Adobeはすべての組織をまたいですべての分類を最新の分類アーキテクチャに移行する予定です。 最後に移行するお客様は、2023 年 5 月に発生すると推定されます。 顧客のアクションは不要で、ダウンタイムも期待されません。 この新しいアーキテクチャには、次のような多くの利点があります。<ul><li>処理時間が大幅に短縮されました (72 時間→ 24 時間 )</li><li>を使用する機能 [分類セット](/help/components/classifications/sets/overview.md) UI</li><li>将来的に ( [分類データ用のAdobe Analyticsソースコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>組織のワークフローに影響を与える可能性のある、次の変更に注意してください。<ul><li>ブラウザーまたは FTP インポートを使用する場合は、「[!UICONTROL 競合時に上書き]「 」は常に有効になっています。</li><li>ブラウザーまたは FTP インポートを使用する場合、インポート直後にエクスポートするオプションはサポートされなくなりました。</li><li>Analytics 2.0 API `GetDimensions` エンドポイントは、数値識別子ではなく、分類の文字列識別子を返すようになりました。 数値識別子は引き続き使用できますが、Adobeでは可能な限り新しい文字列識別子を使用することをお勧めします。 数値識別子は、 `?expansion=hidden` クエリー文字列パラメーター。</li></ul>Adobeの移行スケジュールをより具体的に設定したい場合や、この移行に関する質問や懸念事項がある場合は、カスタマーケアにお問い合わせください。 [詳細情報](/help/components/classifications/sets/overview.md) |

{style=&quot;table-layout:auto&quot;}

## サポート終了 (EOL) に関するお知らせ

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **一部の Reports &amp; Analytics およびReport Builderスケジュール機能のサポート終了** | 2023年2月9日（PT） | 2023 年 1 月 31 日 (PT) に、次のスケジュール機能が提供終了となりました。<ul><li>Report Builderの時間別タスクの「次の時間後に終了」オプション</li><li>Reports and Analyticsで新しいレポートをスケジュールし、データ抽出をダウンロードする機能</li></ul><p>**注意**:当初は、これらの機能は 2022 年 4 月に廃止されましたが、変更は元に戻されました。 また、これらの機能が一時的に復元され、2023 年 1 月 31 日に再び終了することを示す通知も送信しました。 |
| **[!UICONTROL 発行リスト]機能の提供終了（EOL）** | 2022年9月29日 | Reports &amp; Analytics の提供終了（EOL）の一環として、発行リストは **2023年12月**&#x200B;に提供終了になる予定です。新しいパブリッシュリストを作成するか既存のパブリッシュリストにアクセスして、Analysis Workspace プロジェクトの送信やスケジュールを行うことはできなくなります。 |
| **Data Workbench のサポート終了** | 2022年9月14日 | **2023年12月31日**&#x200B;をもって、アドビは Data Workbench のサポートを終了する予定です。詳しくは、[Data Workbench の提供終了のお知らせ](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=ja)を参照してください。ご不明な点がある場合は、組織のアドビ担当営業または販売店にお問い合わせください。 |
| **[!DNL Reports & Analytics]** のサポート終了 | 2022年1月4日 | **2023年12月31日**&#x200B;をもって、アドビは [!DNL Reports & Analytics] およびそれに付随するレポートと機能を廃止する予定です。[!DNL Reports & Analytics] を構成しているレポート、ビジュアライゼーションおよび基盤技術は、アドビの技術標準に適合しなくなりました。ほとんどの [!DNL Reports & Analytics] 機能は、[Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) 内でご利用いただけます。2015年の Analysis Workspace のリリース以降、[!DNL Reports & Analytics] の機能は Analysis Workspace に移行され、同等のワークフロー機能を提供できるようになりました。[このお知らせ](https://spark.adobe.com/page/6WnF8JK6IRDhf/)では、提供終了プロセスについて説明します。 |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

AppMeasurement リリース（バージョン 2.23.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja) を参照してください。


## 関連リソース

* [2022年の以前のリリースノート](/help/release-notes/2022.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
