---
title: 現在の Adobe Analytics リリースノート
description: 現在の Adobe Analytics リリースノートを表示
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7468463e2fe1de16221b4528919b6abd6c8aedcb
workflow-type: ht
source-wordcount: '1445'
ht-degree: 100%

---

# 現在の Adobe Analytics リリースノート（2024年4月）

**最終更新日**：2024年4月17日（PT）

このリリースノートは、2024年4月17日（PT）～5月のリリース期間を対象としています。Adobe Analytics リリースは、[継続的な配信モデル](releases.md)に基づいて動作します。このモデルにより、機能のデプロイメントに対する、よりスケーラブルかつ段階的なアプローチが可能になります。 したがって、これらのリリースノートは月に数回更新されます。 リリースノートを定期的に確認してください。

## 新機能または機能強化 {#features}

| 機能 | 説明 | [ロールアウト開始](releases.md) | [一般公開](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **ストリーミングメディア：Adobe Experience Platform Edge Network への Roku データの送信** | [Experience Platform Edge を使用して Media Analytics をインストール](https://experienceleague.adobe.com/ja/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)する際、Adobe Experience Platform Roku SDK を使用してストリーミングメディアデータを Adobe Experience Platform に送信できるようになりました。 |  | 2024年4月12日（PT） |
| **Web SDK 移行ワークフローの改善** | データストリームは、Web SDK データオブジェクトのフィールドを Adobe Analytics に直接、自動的にマッピングするようになりました。[データオブジェクトのマッピング](/help/implement/aep-edge/data-var-mapping.md)は、[XDM オブジェクトマッピング](/help/implement/aep-edge/xdm-var-mapping.md)に類似していますが、XDM スキーマは必要ありません。この改善されたワークフローによるメリットは次のとおりです。<ul><li>Adobe Experience Platform にデータを送信する準備が整うまで、スキーマを使用する必要性が遅れます。実装移行のこの段階でスキーマが必要な場合は、Adobe Analytics フィールドに基づくスキーマを使用する必要があります。Customer Journey Analytics などの Adobe Experience Platform サービスには、prop や eVar という概念はありません。Analytics に焦点を当てたスキーマでは、組織が今後独自のスキーマを使用する場合に問題が発生する可能性があります。</li><li>Web SDK の実装を変更した後は、組織は Adobe Analytics から Customer Journey Analytics への移行がより容易になります。Web SDK を使用して Adobe Analytics にデータを送信する場合は、Adobe Experience Platform にデータを送信するために追加の実装変更を行う必要はありません。代わりに、データ準備を使用して、データオブジェクトフィールドを XDM スキーマにマッピングできます。</li></ul>詳しくは、[Adobe Analytics のタグ拡張機能から Web SDK のタグ拡張機能への移行](/help/implement/aep-edge/web-sdk/analytics-extension-to-web-sdk.md)および [AppMeasurement から Web SDK への移行](../implement/aep-edge/web-sdk/appmeasurement-to-web-sdk.md)を参照してください。 |  | 2024年4月 |
| **プロジェクト専用の[!UICONTROL ワークスペース]コンポーネントの権限の強化** | 以前は、あるユーザー（ユーザー A）が別のユーザー（ユーザー B）とプロジェクトを共有し、ユーザー B にプロジェクトへの編集アクセス権を付与した場合、ユーザー B はプロジェクトを編集できました。ただし、ユーザー B はプロジェクトに埋め込まれた[!UICONTROL クイックセグメント]を編集できませんでした。この制限は現在削除され、ユーザー B は共有プロジェクトに埋め込まれている[!UICONTROL クイックセグメント]や他のプロジェクト専用コンポーネントを編集できるようになりました。 |  | 2024年4月17日（PT） |
| **[!UICONTROL データフィード]、[!UICONTROL データウェアハウス]、[!UICONTROL 分類セット]**&#x200B;に同じクラウドアカウントを使用 | 作成したクラウドアカウントと場所は、データの書き出し（[!UICONTROL データフィード]および[!UICONTROL データウェアハウス]を使用）およびデータの読み込み（[!UICONTROL 分類セット]を使用）に使用できるようになりました。<p> **アカウント設定時の変更点：**&#x200B;ユーザーは、次のいずれかの目的に使用できる[クラウドの読み込みおよび書き出しのアカウントを設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-accounts)することや、[クラウドの読み込みおよび書き出しの場所を設定](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/configure-import-locations)することができます。<ul><li>[!UICONTROL 分類セット]を使用したデータの読み込み</li><li>[!UICONTROL データフィード]を使用したデータの書き出し</li><li>[!UICONTROL データウェアハウス]を使用したデータの書き出し</li></ul><p>**[!UICONTROL 場所]ページからのアカウントと場所の管理時の変更点**：ユーザーは、[場所](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/locations-manager)ページ（[!UICONTROL コンポーネント]／場所の下）を使用して、作成場所に関係なく、作成したすべてのアカウントと場所を表示および管理できます。 <p>以前は、[!UICONTROL 場所]ページは、[!UICONTROL 分類セット]を使用してデータを読み込むために作成されたアカウントにのみ適用されていました。</p>**[!UICONTROL データウェアハウス]または[!UICONTROL 分類セット]**&#x200B;からの場所の管理時の変更点<p>特定のアプリケーション領域（[!UICONTROL データウェアハウス]または[!UICONTROL 分類セット]）内の場所を管理する際、その特定のアプリケーション領域で作成した場所のみが使用可能です。例えば、[!UICONTROL データウェアハウス]のアプリケーション領域を表示する場合、[!UICONTROL データウェアハウス]の場所のみが使用可能です。すべてのアカウントは、アカウントを作成したアプリケーション領域に関係なく、各アプリケーション領域で引き続き使用できます。以前は、アカウントと場所を作成したアプリケーション領域に関係なく、すべてのアカウントと場所が各アプリケーション領域で使用可能でした。これは、[!UICONTROL データフィード]アプリケーション領域を表示する場合にも当てはまります。 | | 2024年4月17日（PT） |
| **管理者は組織内のすべての場所とアカウントを管理できる** | 「場所」タブ（コンポーネント／場所ページ）の新しいオプションを使用すれば、管理者は組織内のすべての場所を表示および管理できます。<p>「[場所](https://experienceleague.adobe.com/ja/docs/analytics/components/locations/locations-manager)」アカウントタブ（コンポーネント／場所ページ）の新しいオプションを使用すれば、管理者は組織内のすべてのアカウントを表示および管理できます。</p> <p>以前は、管理者は自分が作成した場所とアカウントのみを表示および管理できました。</p> |  | 2024年4月17日（PT） |
| **デフォルトの低トラフィックしきい値の増加** | **2024年4月中旬**&#x200B;に、アドビは、次のように、デフォルトのレポートスイートの低トラフィックしきい値を引き上げ始めます。![低トラフィックしきい値](assets/thresholds.png)：これは、現在新しいしきい値を下回って設定されている変数にのみ影響します。 この度の変更は段階的に行われ、作業は **5月末**&#x200B;に完了する予定です。 この度の増加がロールアウトされると、高基数変数の変更に気付く場合があります。<ul><li>レポートには、より多くのディメンション値を使用できる場合があります。</li><li>セグメントと計算指標に含まれるデータの量が多くなる場合があります。</li><li>セグメントに基づく仮想レポートスイートには、より多くのデータが含まれる場合があります。</li><li>分類の書き出しには、より多くのデータが含まれる場合があります。</li></ul> | 2024年4月中旬 | 2024年5月31日（PT） |
| **Activity Map が使用する Web SDK のサーバー呼び出しの数が低減します** | 現在、Activity Map リンクイベントは独自のイベントとしてカウントされ、追加費用が発生します。 <p>この機能強化では、AppMeasurement でのイベントの処理と同様に、一部のリンクイベントを取り上げ、それらを次のヒットにパッケージ化します。</p> |  | 2024年5月31日（PT） |

{style="table-layout:auto"}

## Adobe Analytics の修正点

* 次の分類の問題を修正しました。AN-343439、AN-343503、AN-343504、AN-343986、AN-344262、AN-344564、AN-345204、AN-345234
* 次の分類ルールビルダーの問題を修正しました。AN-341488、AN-342501、AN-345751
* 次のインテリジェントアラートの問題を修正しました。AN-343466、
* 次のセグメント化の問題を修正しました。AN-342313
* 次のデータウェアハウスの問題を修正しました。AN-344292
* 次のデータフィードの問題を修正しました。AN-339545、AN-340092、AN-342124、AN-342862、AN-343737、AN-344035、AN-344329、AN-344703、AN-344721、AN-344940、AN-345180、AN-345196、AN-345225、AN-345236、AN-345326、AN-345631、AN-345659
* 次のデータソースの問題を修正しました。AN-343541
* 次の Analysis Workspace の問題を修正しました。AN-336303、AN-336472、AN-338422、AN-338556、AN-339718、AN-340147、AN-340301、AN-340421、AN-340951、AN-341172、AN-342905、AN-342909、AN-343448、AN-343570、AN-344050、AN-344182、AN-344763、AN-344768、
* 次の Analytics 管理者の問題を修正しました。AN-342519、AN-342523、AN-343623、AN-343882、AN-344237、AN-344829、AN-345235、
* 次の A4T の問題を修正しました。AN-341619、AN-344402
* 次のモバイルアプリの問題を修正しました。AN-342010

### Analytics のその他の修正

AN-336099、AN-337474、AN-337993、AN-339718、AN-339901、AN-340014、AN-341356、AN-343021、AN-343102、AN-343353、AN-343416、AN-340014、AN-344037、AN-344525、AN-345737

## Adobe Analytics 管理者向けの重要な注意事項 {#admin}

| 通知 | 追加日または更新日 | 説明 |
| ----------- | ---------- | ---------- |
| **保存された`cust_visids`** の有効期限は 13 か月 | 2024年3月20日（PT） | Analytics のヒット処理エンジンの次回リリース（4月または 5月を予定）では、保存された `cust_visids` に 13 か月の有効期限が適用されます。 レポートスイートで「訪問者のステッチを有効にする」が有効になっている場合、この設定は、ヒット時の `cust_visid` がない `visid_high/visid_low value` で、`cust_visid` を見つける際に使用します。 現在、`visid_high/visid_low` に対する `cust_visid` のマッピングに有効期限はありません。 このリリースでは、`visid_high/visid_low` にヒット時の `cust_visid` が設定されてから 13 か月以上が経過すると、マッピングが期限切れになります。 |
| **Adobe API オブジェクトメンバーの追加** | 2024年1月17日（PT） | アドビでは、バージョン管理の通知や変更なしに、オプションのリクエストおよび応答メンバー（名前／値のペア）を既存の API オブジェクトにいつでも追加できます。 アドビでは、API と統合するサードパーティツールの API ドキュメントを参照し、理解できない場合は、そのような追加が処理で無視されるようにすることをお勧めします。 適切に実装されている場合、そのような追加は実装に対して破壊的な変更ではありません。 アドビでは、最初にリリースノートを通じて標準通知を提供することなく、パラメーターを削除したり、必要なパラメーターを追加したりすることはありません。 |

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
