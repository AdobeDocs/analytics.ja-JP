---
title: Adobe Analyticsの訪問者ID
description: 最新のベストプラクティスを使用して、Adobe Analyticsで訪問者を特定する方法について説明します。
exl-id: 8d26a556-84fe-4fb5-98d6-a16b69423e5b
TQID: https://experienceleague.adobe.com/uwEv9cl3234uiWhZEZLqgAVo42b-9L-9YEIGD97Pw-Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567did: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 652
ht-degree: 9%

---

# Adobe Analyticsの訪問者ID

訪問者の特定は、Adobe Analyticsがオンラインユーザーの行動を把握するために提供する価値の中核を成します。 共通の識別子を使用して、同じ人物にヒットを経時的にリンクさせる必要があります。 訪問者を正確に識別することで、信頼できる指標を確保し、健全な導入戦略を実現できます。 Adobeでは、プラットフォーム間での一貫性とデータの整合性を重視した、最新のID サービスを優先することをお勧めします。

Adobe Analyticsの訪問者IDは、次のコンポーネントで構成されています。

* クライアント側の識別子：通常、ファーストパーティ Cookieに保存されます。 サードパーティ Cookieに依存する実装は、最新のブラウザープライバシー標準により、訪問者の識別との一貫性が低くなっています。
* サーバーサイド ID：各Analytics訪問者IDは、Adobe サーバー上のプロファイルに関連付けられます。 これらの訪問者プロファイルは、[eVars](/help/components/dimensions/evar.md)などの変数に対する永続性を許可するものです。 プロファイルは、訪問者ID cookieの有効期限にかかわらず、少なくとも13か月の非アクティブ化後に削除されます。

## Adobe Analyticsの運用手順

Adobeがヒットを受け取ると、次のチェックが順番に行われます。 特定のプロパティが存在する場合、AdobeはそのIDをヒットに使用します。 ヒットに複数の識別子が存在する場合は、最初のメソッドのみが使用されます。 Adobeが訪問者の特定を推奨する順序は、作業手順に反映されないことに注意してください。

| 使用順序 | クエリパラメーター | 以下の場合に表示される |
|---|---|---|
| **1<sup>st</sup>** | `vid` | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 変数が設定されます。 |
| **2<sup>および</sup>** | `aid` | 訪問者には既存の[`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookieがあります。 訪問者ID サービスを実装していない、または実装する前に実装を設定します。 |
| **3<sup>rd</sup>** | `mid` | [訪問者ID サービス ](https://experienceleague.adobe.com/ja/docs/id-service/using/home)を使用するAppMeasurement ベースの実装（Analytics タグ拡張機能を含む）の場合、訪問者には既存の[`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)または`AMCV` Cookieがあります。 Web SDK ベースの実装の場合、訪問者には既存の[`kndctr_<orgId>_identity`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/web-sdk)または`AMCV` Cookieがあります。 Adobeでは、可能な限り、すべての実装でECIDを使用することをお勧めします。 |
| **4<sup>番目</sup>** | `fid` | 訪問者には既存の[`s_fid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) Cookieがあります。 AppMeasurementは、何らかの理由で`aid`と`mid`を設定できない場合、フォールバック IDを自動的に生成します。 |
| **5<sup>番目</sup>** | IP アドレス + ユーザーエージェント | 訪問者のブラウザーがCookieを受け入れない場合に、ユニーク訪問者を識別するための最後の手段として使用されます。 ハッシュ化された訪問者IDは、[IP難読化](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)の前に生成されます。 IP アドレスが使用できない場合は、代わりに他のIPの詳細（ゲートウェイ IPなど）が使用されます。 |

選択した訪問者IDはハッシュ化され、サーバーサイドの識別子になります。 このサーバーサイド IDは、[ データフィード ](/help/export/analytics-data-feed/data-feed-overview.md)の`visid_high` + `visid_low`で利用できます。

## ユニーク訪問者数に影響する動作

ユニーク訪問者識別子は、通常、ブラウザーの Cookie に保存されます。 訪問者が次のいずれかのアクションを実行すると、新しいユニーク訪問者がカウントされます。

* いつでもCookieを消去します。 キャッシュがクリアされるたびに、ヒットに対して1人のユニーク訪問者がカウントされます。
* 訪問者ID Cookieは、ブラウザーのプライバシー設定により期限切れになります。 一部のブラウザーには、Cookieの有効期間を制限するトラッキング防止方法が含まれています。
* 同じコンピューターで別のブラウザーを開く - ブラウザーごとにユニーク訪問者が 1 回カウントされます。
* プライベートブラウジングセッション（「Chromeのシークレットタブ」など）を開きます。 すべてのタブを閉じると、ブラウジングセッションごとに1人のユニーク訪問者がカウントされます。
* 様々なデバイスでサイトを訪問： デバイスごとに1人のユニーク訪問者がカウントされます。
* 非アクティブ状態が13か月以上続いた後にサイトにアクセスした場合。

複数のブラウザーまたは複数のデバイスを使用している同じユーザーを識別するために、Customer Journey Analyticsで[ ステッチ ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/stitching/overview)を使用することを検討してください。

## ユニーク訪問者数に影響しない行動

訪問者識別子が保持されている限り、新しいユニーク訪問者は&#x200B;*not* カウントされます。

* ブラウザーを閉じる（13か月未満）
* ブラウザーを最新バージョンにアップグレードする
* コンピューターを再起動します
