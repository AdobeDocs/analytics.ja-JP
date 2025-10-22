---
title: Adobe Analyticsでの訪問者の ID
description: 最新のベストプラクティスを使用して、Adobe Analyticsで訪問者を特定する方法を説明します。
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 10%

---

# Adobe Analyticsでの訪問者の ID

オンラインユーザーの行動を把握するうえでAdobe Analyticsが提供する価値の中心は、訪問者の特定です。 共通の識別子を使用して、同じ人物に対するヒットを時間の経過と共にリンクします。 訪問者を正確に識別することで、信頼性の高い指標を確保し、健全な実装戦略をサポートします。 Adobeでは、プラットフォーム間の一貫性とデータ整合性を確保するために、最新の ID サービスを優先することをお勧めします。

Adobe Analyticsの訪問者 ID は、次のコンポーネントで構成されます。

* クライアントサイド識別子：通常、ファーストパーティ cookie に保存されます。 最新のブラウザープライバシー標準により、サードパーティ cookie に依存する実装は訪問者の識別との一貫性が低下します。
* サーバーサイド識別情報：各 Analytics 訪問者 ID は、Adobe サーバーのプロファイルに関連付けられています。 これらの訪問者プロファイルにより、[eVars](/help/components/dimensions/evar.md) などの変数に永続性を持たせることができます。 プロファイルは、訪問者 ID cookie の有効期限に関係なく、13 か月以上の無操作状態の後に削除されます。

## Adobe Analytics工程の ID 順序

Adobeがヒットを受け取ると、次のチェックが順番に行われます。 指定されたプロパティが存在する場合、Adobeはヒットにその識別情報を使用します。 ヒットに複数の識別子が存在する場合は、最初のメソッドのみが使用されます。 なお、操作の順序は、Adobeが訪問者を識別するために推奨する順序を反映しません。

| 使用する順序 | クエリパラメーター | 次の場合に存在 |
|---|---|---|
| **1<sup></sup>** | `vid` | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 変数が設定されます。 |
| **2<sup> 目</sup>** | `aid` | 訪問者が既存の [`s_vi`](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/cookies/analytics) Cookie を持っている。 訪問者 ID サービスを実装しない、または実装する前に設定します。 |
| **3<sup></sup>** | `mid` | 訪問者が既存の [`s_ecid`](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/cookies/analytics) Cookie を持っている。 [Adobe Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja) を使用した実装に設定します。 Adobeでは、可能な限り、すべての実装に ID サービスを使用することをお勧めします。 |
| **4<sup> 目</sup>** | `fid` | 訪問者が既存の [`s_fid`](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/cookies/analytics) Cookie を持っている。 何らかの理由で `aid` および `mid` を設定できない場合、AppMeasurementはフォールバック ID を自動生成します。 |
| **5<sup> 目</sup>** | IP アドレス + ユーザーエージェント | 訪問者のブラウザーが Cookie を受け入れない場合に、ユニーク訪問者を識別するための最後の手段として使用されます。 ハッシュ化された訪問者 ID は、[IP の不明化 &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) の前に生成されます。 IP アドレスが使用できない場合は、他の IP 詳細（ゲートウェイ IP など）が代わりに使用されます。 |

選択された訪問者 ID はハッシュ化され、サーバーサイドの識別子になります。 このサーバーサイド識別子は、`visid_high` データフィード `visid_low` で [&#x200B; + &#x200B;](/help/export/analytics-data-feed/data-feed-overview.md) として使用できます。

## ユニーク訪問者数に影響する動作

ユニーク訪問者識別子は、通常、ブラウザーの Cookie に保存されます。訪問者が次のいずれかのアクションを実行すると、新規ユニーク訪問者がカウントされます。

* Cookie を常にクリアします。 キャッシュがクリアされるたびに、ヒットに対して 1 人のユニーク訪問者がカウントされます。
* 訪問者 ID cookie は、ブラウザーのプライバシー設定が原因で期限切れになります。 一部のブラウザーには、cookie の有効期間を制限するトラッキング防止方法が含まれています。
* 同じコンピューターで別のブラウザーを開く -ブラウザーごとにユニーク訪問者が 1 回カウントされます。
* プライベート参照セッションを開きます（Chromeの「匿名」タブなど）。 すべてのタブが閉じられると、閲覧セッションごとに 1 人のユニーク訪問者がカウントされます。
* 様々なデバイスでサイトを訪問します。 ユニーク訪問者は、デバイスごとに 1 人とカウントされます。
* 13 か月以上無操作状態が続いた後にサイトを訪問します。

Customer Journey Analyticsで [&#x200B; ステッチ &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/stitching/overview) を使用し、複数のブラウザーまたは複数のデバイスを使用して同じ人物を識別することを検討してください。

## ユニーク訪問者数に影響を与えない動作

訪問者識別子が保持されている限り、新しいユニーク訪問者はカウント *されません*。

* ブラウザーを閉じる（13 か月未満）
* ブラウザーを最新バージョンにアップグレードする
* コンピューターを再起動します
