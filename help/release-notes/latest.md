---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 06d1dcf1c6823555f044842a1cc5c10c2bbc12a0
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 37%

---

# 最新のAdobe Analyticsリリースノート（2024 年 3 月）

**最終更新日**：2024年3月20日（PT）

これらのリリースノートでは、2024 年 3 月 12 日から 2024 年 4 月のリリース期間を扱っています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。したがって、これらのリリースノートは月に数回更新されます。リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **AppMeasurementの更新** | [AppMeasurementリリース v2.26.0](/help/implement/appmeasurement-updates.md) が使用可能です。 | | 2024年3月4日（PT） |
| **プロジェクトランディングページで新しい列を使用できます** | The **[!UICONTROL 最後に使用した日時]** 列が、 [Adobe Analyticsランディングページ](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=ja). <p>この情報は、プロジェクトが最後に開かれた日時を示すことで、組織内のユーザーにとってプロジェクトが有用かどうかを判断するのに役立ちます。</p> <p>以前は、 **[!UICONTROL 最後に使用した日時]** 列は、計算指標マネージャー、セグメントマネージャー、アラートマネージャーでのみ使用できました。</p> |  | 2024年3月13日（PT） |
| **Analytics では、DMA にGoogleが必要とする同意フラグをサポートします。** | 新しい欧州のプライバシー規制により、Googleでは、欧州で収集されたデータをそのデータに送信する際に、2 種類の特定の同意が得られたかどうかを示す必要があります。 **3 月 6 日開始**&#x200B;の場合、Googleは、関連する同意が得られたことを示さないイベントデータを受け入れなくなります。 Adobe Analyticsは、新しい adConsent 変数を使用したデータの取得のサポートをリリースしました。 新しい変数は、 [プライバシーレポート UI](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md). この機能をアクティブ化し、以前の同意変数のプライバシーを既に有効にする場合は、プライバシーを再度有効にする必要があります。<p>The [広告プラットフォーム同意ディメンション](/help/components/dimensions/ad-consent.md) は、Googleなどのサードパーティの広告プロバイダーにデータを送信するための同意を収集するかどうかを表示します。 |  | 2024年3月13日（PT） |
| **Report Builder使用状況。計算指標マネージャーおよびセグメントマネージャーの「使用されている場所」列に含まれます。** | 次を表示する場合： **使用場所** 列を使用して、セグメントマネージャーまたはセグメントマネージャーで、使用状況データをReport Builderで利用できるようになりました。<p>セグメントマネージャーの使用状況データは、以前は、アラート、プロジェクト、スケジュール済みプロジェクトおよび計算指標に対してのみ使用でき、計算指標マネージャーの使用状況データは、アラート、プロジェクト、スケジュール済みプロジェクトに対してのみ使用できました。</p> |  | 3 月下旬または 4 月上旬 |
| **データフィード、Data Warehouse、分類セットに同じクラウドアカウントを使用する** | 作成したクラウドアカウントおよび場所を、( データフィードおよびData Warehouseを使用した ) データの書き出しや、（分類セットを使用した）データの読み込みに使用できるようになりました。<p> **アカウント設定時の変更点は次のとおりです。** ユーザーは、クラウドのインポートおよびエクスポートアカウントを設定し、次の目的で使用できるクラウドのインポートおよびエクスポートの場所を設定できます。<ul><li>分類セットを使用したデータのインポート</li><li>データフィードを使用したデータの書き出し</li><li>データを書き出す際にData Warehouse。</li></ul><p>**アカウント管理時の変更**：ユーザーは、（コンポーネント/ロケーションの下にある）ロケーションページを使用して、作成場所に関係なく、作成したすべてのアカウントとロケーションを表示および管理できます。 <p>以前は、ロケーションページは、分類セットを持つデータのインポート用に作成されたアカウントにのみ適用されていました。</p> | | 2024年4月 |
| **管理者は、組織内のすべての場所とアカウントを管理できます** | 管理者は、「ロケーション」タブ（コンポーネント/ロケーションページ）の新しいオプションを使用して、組織内のすべてのロケーションを表示および管理できます。<p>管理者は、「ロケーションアカウント」タブ（コンポーネント/ロケーションページ）の新しいオプションを使用して、組織内のすべてのアカウントを表示および管理できます。</p> <p>以前は、管理者は自分が作成した場所とアカウントのみを表示および管理できました。</p> |  | 2024年4月 |
| **Activity Mapが Web SDK で使用するサーバー呼び出しの数を減らします** | 現在、Activity Mapリンクイベントは独自のイベントとしてカウントされ、追加費用が発生します。 <p>この度の機能強化では、AppMeasurement でのイベントの処理と同様に、一部のリンクイベントを取り上げ、それらを次のヒットにパッケージ化します。</p> |  | 2024年4月3日（PT） |
| **デフォルトの低トラフィックしきい値の増加** | **2024年4月中旬**&#x200B;に、アドビは、次のように、デフォルトのレポートスイートの低トラフィックしきい値を引き上げ始めます。![低トラフィックしきい値](assets/thresholds.png)：これは、現在新しいしきい値を下回って設定されている変数にのみ影響します。この度の変更は段階的に行われ、作業は **5月末**&#x200B;に完了する予定です。この度の増加がロールアウトされると、高基数変数の変更に気付く場合があります。<ul><li>レポートには、より多くのディメンション値を使用できる場合があります。</li><li>セグメントと計算指標に含まれるデータの量が多くなる場合があります。</li><li>セグメントに基づく仮想レポートスイートには、より多くのデータが含まれる場合があります。</li><li>分類の書き出しには、より多くのデータが含まれる場合があります。</li></ul> | | 2024年4月中旬 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* 次の分類の問題を修正しました。AN-335632、AN-337559、AN-340164、AN-340370、AN-341211、AN-341284、AN-341469、AN-341778341481、AN-341760、AN-342144、AN-AN-AN-342400、AN-
* 分類ルールビルダーで発生していた問題を修正しました。AN-340921、AN-341269、AN-341292、AN-341467、AN-341666、AN-342145、AN-342329
* 次のインテリジェントアラートの問題を修正しました。AN-340736
* 次のセグメント化の問題を修正しました。AN-336242
* 次のData Warehouseの問題を修正しました。AN-335354、AN-339446、AN-339774、AN-340221、AN-340599、AN-341277、AN-342009、AN-342088、AN-342592
* 次のデータフィードの問題を修正しました。AN-335508、AN-340887、AN-341050、AN-341208、AN-341403、AN-341479、AN-341524、AN-342000、AN-342125、342256AN-342301;AN-342410;AN-;AN-
* 次のReport Builderの問題を修正しました。 AN-340540
* Analysis Workspaceの次の問題を修正しました。AN-295889、AN-330981、AN-338818、AN-339730、AN-341114、AN-341520;

### Analytics のその他の修正

AN-312198、AN-338009、AN-339549、AN-333970、AN-334790、AN-336572、AN-339549、AN-341119、AN-341246、AN-341268、AN-341272、AN-AN-341558AN-AN-AN 以下

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **保存されたの 13 か月の有効期限`cust_visids`** | 2024年3月20日（PT） | 4 月または 5 月を対象とする、Analytics のヒット処理エンジンの今後のリリースで、保存済みのの 13 か月の有効期限の適用が開始されます `cust_visids`. レポートスイートで「訪問者のステッチを有効にする」が有効になっている場合、この設定を使用して `cust_visid` の `visid_high/visid_low value` いいえ `cust_visid` をヒットに追加します。 現在、 `cust_visid` の `visid_high/visid_low`. このリリースでは、 `visid_high/visid_low` は、 `cust_visid` ヒットの場合、マッピングは期限切れになります。 |
| **AdobeAPI オブジェクトメンバーの追加** | 2024年1月17日（PT） | アドビでは、バージョン管理の通知や変更なしに、オプションのリクエストおよび応答メンバー（名前／値のペア）を既存の API オブジェクトにいつでも追加できます。アドビでは、API と統合するサードパーティツールの API ドキュメントを参照し、理解できない場合は、そのような追加が処理で無視されるようにすることをお勧めします。適切に実装されている場合、そのような追加は実装に対して破壊的な変更ではありません。アドビでは、最初にリリースノートを通じて標準通知を提供することなく、パラメーターを削除したり、必要なパラメーターを追加したりすることはありません。 |
| **`getPageLoadTime`プラグインが廃止されました** | 2024年1月10日（PT） | このプラグインはサポートされなくなりました。そのコードは、（MDN に従って）[廃止](https://developer.mozilla.org/ja/docs/Web/API/PerformanceTiming)となった Performance.timing メソッドを利用しています。更新されたプラグインの動作が開始しました。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについては、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2023年の以前のリリースノート](/help/release-notes/2023.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
