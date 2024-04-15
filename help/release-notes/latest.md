---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: aac32bdda365ce4534f1d4c04e816eb6f03b991c
workflow-type: ht
source-wordcount: '1351'
ht-degree: 100%

---

# 現在の Adobe Analytics リリースノート（2024年3月）

**最終更新日**：2024年4月3日（PT）

このリリースノートは、2024年3月12日（PT）～2024年4月（PT）のリリース期間を対象としています。 Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Workspace プロジェクトの削除プロトコルの変更** | 以前は、削除したプロジェクトはシステムからパージされませんでした。 180日後に、削除したプロジェクトのパージを開始します。 削除後 180日間は、プロジェクトへの URL を持っているユーザーは、web インターフェイス経由で削除したプロジェクトに引き続きアクセスできます。 | | 2024年3月14日（PT） |
| **AppMeasurement のアップデート** | [AppMeasurement リリース v2.26.0](/help/implement/appmeasurement-updates.md) が使用可能です。 | | 2024年3月4日（PT） |
| **プロジェクトランディングページで使用可能な新しい列** | [Adobe Analytics ランディングページ](https://experienceleague.adobe.com/docs/analytics/analyze/landing.html?lang=ja)の「プロジェクト」タブを表示すると、**[!UICONTROL 前回の使用]**&#x200B;列が使用できるようになりました。 <p>この情報は、プロジェクトが前回開かれた日時を示し、プロジェクトが組織内のユーザーにとって有用かどうかを判断するのに役立ちます。</p> <p>以前は、**[!UICONTROL 前回の使用]**&#x200B;列は、計算指標マネージャー、セグメントマネージャー、アラートマネージャーでのみ使用できました。</p> |  | 2024年3月13日（PT） |
| **Google による DMA に必要な同意フラグの Analytics サポート** | 新しい欧州プライバシー規制により、Google では、欧州で収集され、Google に送信されたデータには、2 つの特定の種類の同意が付与されたかどうかを示す必要があります。**3月6日（PT）以降**、Google では、関連する同意が付与されたことを示さないイベントデータを承認しなくなります。 Adobe Analytics では、新しい adConsent 変数を通じてこのデータをキャプチャするサポートをリリースしました。 新しい変数が[プライバシーレポート UI](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) にリストされていることを参照できます。 これをアクティブ化する場合、および以前の同意変数に対してプライバシーが既に有効である場合は、プライバシーを再度有効にする必要があります。<p>[広告プラットフォームの同意ディメンション](/help/components/dimensions/ad-consent.md)は、Google などのサードパーティの広告プロバイダーにデータを送信するための同意を収集するかどうかを表示します。 |  | 2024年3月13日（PT） |
| **Report Builder の使用状況が、計算指標マネージャーおよびセグメントマネージャーの「使用場所」列に含まれる** | 計算指標マネージャーまたはセグメントマネージャーで&#x200B;**使用場所**&#x200B;列を表示する際、Report Builder で使用状況データを使用できるようになりました。<p>以前は、セグメントマネージャーの使用状況データは、アラート、プロジェクト、スケジュール済みプロジェクトおよび計算指標に対してのみ使用できました。一方、計算指標マネージャーの使用状況データは、アラート、プロジェクト、スケジュール済みプロジェクトでのみ使用できました。</p> |  | 7月 |
| **データフィード、データウェアハウス、分類セットに同じクラウドアカウントを使用** | 作成したクラウドアカウントと場所は、データの書き出し（データフィードおよびデータウェアハウスを使用）およびデータの読み込み（分類セットを使用）に使用できるようになりました。<p> **アカウント設定時の変更点：**&#x200B;ユーザーは、次のいずれかの目的に使用できるクラウドの読み込みおよび書き出しのアカウントを設定することや、クラウドの読み込みおよび書き出しの場所を設定することができます。<ul><li>分類セットを使用したデータの読み込み</li><li>データフィードを使用したデータの書き出し</li><li>データウェアハウスを使用したデータの書き出し。</li></ul><p>**アカウント管理時の変更点**：ユーザーは、場所ページ（コンポーネント／場所の下）を使用して、作成場所に関係なく、作成したすべてのアカウントと場所を表示および管理できます。 <p>以前は、場所ページは、分類セットを使用してデータを読み込むために作成されたアカウントにのみ適用されていました。</p> | | 2024年4月 |
| **管理者は組織内のすべての場所とアカウントを管理できる** | 「場所」タブ（コンポーネント／場所ページ）の新しいオプションを使用すれば、管理者は組織内のすべての場所を表示および管理できます。<p>「場所アカウント」タブ（コンポーネント／場所ページ）の新しいオプションを使用すれば、管理者は組織内のすべてのアカウントを表示および管理できます。</p> <p>以前は、管理者は自分が作成した場所とアカウントのみを表示および管理できました。</p> |  | 2024年4月 |
| **Activity Map が使用する Web SDK のサーバー呼び出しの数が低減します** | 現在、Activity Map リンクイベントは独自のイベントとしてカウントされ、追加費用が発生します。 <p>この機能強化では、AppMeasurement でのイベントの処理と同様に、一部のリンクイベントを取り上げ、それらを次のヒットにパッケージ化します。</p> |  | 2024年4月31日（PT） |
| **デフォルトの低トラフィックしきい値の増加** | **2024年4月中旬**&#x200B;に、アドビは、次のように、デフォルトのレポートスイートの低トラフィックしきい値を引き上げ始めます。![低トラフィックしきい値](assets/thresholds.png)：これは、現在新しいしきい値を下回って設定されている変数にのみ影響します。 この度の変更は段階的に行われ、作業は **5月末**&#x200B;に完了する予定です。 この度の増加がロールアウトされると、高基数変数の変更に気付く場合があります。<ul><li>レポートには、より多くのディメンション値を使用できる場合があります。</li><li>セグメントと計算指標に含まれるデータの量が多くなる場合があります。</li><li>セグメントに基づく仮想レポートスイートには、より多くのデータが含まれる場合があります。</li><li>分類の書き出しには、より多くのデータが含まれる場合があります。</li></ul> | | 2024年4月中旬 |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* 次の分類の問題を修正しました。AN-335632、AN-337559、AN-340164、AN-340370、AN-341089、AN-341211、AN-341284、AN-341469、AN-341481、AN-341760、AN-341778、AN-342144、AN-342258、AN-342338、AN-342400
* 次の分類ルールビルダーでの問題を修正しました。AN-340921、AN-341269、AN-341292、AN-341467、AN-341666、AN-342145、AN-342329
* 次のインテリジェントアラートの問題を修正しました。AN-340736
* 次のセグメント化の問題を修正しました。AN-336242
* 次のデータウェアハウスの問題を修正しました。AN-335354、AN-339446、AN-339774、AN-340221、AN-340599、AN-341277、AN-342009、AN-342088、AN-342592
* 次のデータフィードの問題を修正しました。AN-335508、AN-340887、AN-341050、AN-341208、AN-341403、AN-341479、AN-341524、AN-341661、AN-342000、AN-342125、AN-342256、AN-342301、AN-342410、AN-342502、AN-342525
* 次の Report Builder の問題を修正しました。AN-340540
* 次の Analysis Workspace の問題を修正しました。AN-295889、AN-330981、AN-338818、AN-339730、AN-341114、AN-341520、

### Analytics のその他の修正

AN-312198、AN-338009、AN-339549、AN-333970、AN-334790、AN-336461、AN-336572、AN-339549、AN-341119、AN-341246、AN-341268、AN-341272、AN-341475、AN-341547、AN-341558、AN-341680、AN-342017

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **保存された`cust_visids`** の有効期限は 13 か月 | 2024年3月20日（PT） | Analytics のヒット処理エンジンの次回リリース（4月または 5月を予定）では、保存された `cust_visids` に 13 か月の有効期限が適用されます。 レポートスイートで「訪問者のステッチを有効にする」が有効になっている場合、この設定は、ヒット時の `cust_visid` がない `visid_high/visid_low value` で、`cust_visid` を見つける際に使用します。 現在、`visid_high/visid_low` に対する `cust_visid` のマッピングに有効期限はありません。 このリリースでは、`visid_high/visid_low` にヒット時の `cust_visid` が設定されてから 13 か月以上が経過すると、マッピングが期限切れになります。 |
| **Adobe API オブジェクトメンバーの追加** | 2024年1月17日（PT） | アドビでは、バージョン管理の通知や変更なしに、オプションのリクエストおよび応答メンバー（名前／値のペア）を既存の API オブジェクトにいつでも追加できます。 アドビでは、API と統合するサードパーティツールの API ドキュメントを参照し、理解できない場合は、そのような追加が処理で無視されるようにすることをお勧めします。 適切に実装されている場合、そのような追加は実装に対して破壊的な変更ではありません。 アドビでは、最初にリリースノートを通じて標準通知を提供することなく、パラメーターを削除したり、必要なパラメーターを追加したりすることはありません。 |
| **`getPageLoadTime`プラグインの廃止** | 2024年1月10日（PT） | このプラグインはサポートされなくなりました。 そのコードは、（MDN に従って）[廃止](https://developer.mozilla.org/ja/docs/Web/API/PerformanceTiming)となった Performance.timing メソッドを利用しています。 更新されたプラグインの動作が開始しました。 |

{style="table-layout:auto"}

## 提供終了（EOL）に関する注意事項 {#eol}

| EOL 対象の製品または機能 | 追加日または更新日 | 説明 |
| --- | --- | --- |
| **Adobe I/O OAuth サーバー間資格情報への移行** | 2023年5月11日（PT） | Adobe I/O JWT 資格情報を使用している Adobe Analytics API および Livestream のお客様は、**2025年1月1日（PT）**&#x200B;までに Adobe I/O OAuth サーバー間資格情報に移行する必要があります。 Adobe I/O では、2024年5月1日（PT）以降、新しい JWT 資格情報を作成できなくなります。 JWT を使用しているお客様は、新しい OAuth サーバー間資格情報を作成するか、既存の JWT 資格情報を OAuth サーバー間資格情報に移行する必要があります。 また、お客様が新しい OAuth サーバー間資格情報を使用するには、クライアントアプリケーションを更新する必要もあります。 <ul><li>[サービスアカウント（JWT）資格情報からの移行](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[OAuth を使用した新旧のアプリケーションの実装ガイド](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[新しい OAuth サーバー間資格情報の使用](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[よくある質問（FAQ）](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

AppMeasurement リリース（バージョン 2.26.0）の最新のアップデートについて詳しくは、[JavaScript 版 AppMeasurement リリースノート](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=ja)を参照してください。


## 関連リソース

* [2023年の以前のリリースノート](/help/release-notes/2023.md)
* [Customer Journey Analytics リリースノート](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ja)
* [Media Analytics リリースノート](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=ja)
* [Adobe Experience Cloud 製品](https://business.adobe.com/jp/products/adobe-experience-cloud-products.html)の最新のリリース更新
