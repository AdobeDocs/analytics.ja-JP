---
title: トランザクション ID データソース
description: オンラインヒットから保存された値を使用して、トランザクション ID を共有するオフラインヒットを強化します。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 8%

---

# トランザクション ID データソース

トランザクション ID データソースは、オンラインヒットから保存された値を、同じトランザクション ID を共有するオフライン行に適用できる、概要データソースのバリエーションです。 この方法は、トランザクションをオンラインでキャプチャし、後で別のシステムから詳細を受け取る場合に役立ちます。 プライマリの例としては、商品の返品、予約のキャンセル、コールセンターとのやり取りからの成果などがあります。

>[!NOTE]
>
>トランザクション ID データソースを使用する前に、まず目的のレポートスイートの [ 一般的なアカウント設定 ](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) で有効にする必要があります。

## 仕組み

トランザクション ID の概念には、次の 2 つの部分が必要です。

* **オンラインヒット**：レポートスイート（AppMeasurement、Web SDK、API など）に送信される完全な Analytics ヒット。 このヒットでは、[`transactionID`](/help/implement/vars/page-vars/transactionid.md) 実装変数を設定します。
* **オフラインヒット**：データソースからアップロードされた行。 ファイル内に、オンラインヒットに一致する値を持つ `transactionID` 列を含めます。

`transactionID` 実装変数を含むオンラインヒットを送信すると、Adobeは、その時点で設定または持続された次のディメンションの「スナップショット」を取得します。

* [カテゴリ](/help/components/dimensions/category.md)
* [初回購入までの日数](/help/components/dimensions/days-before-first-purchase.md)
* [前回購入からの日数](/help/components/dimensions/days-since-last-purchase.md)
* [eVars 1-250](/help/components/dimensions/evar.md)
* eVar と同様に動作する [ レポートスイートの設定 ](/help/admin/tools/manage-rs/report-suites-admin.md) で有効になっている機能固有のディメンション。 プロパティと同様に動作するフィーチャ固有の寸法は含まれません。
* [リスト変数](/help/implement/vars/page-vars/list.md)
* [マーケティングチャネル](/help/components/dimensions/marketing-channel.md)
* [マーケティングチャネルの詳細](/help/components/dimensions/marketing-detail.md)
* [モバイルディメンション](/help/components/dimensions/mobile-dimensions.md)
* [オリジナルの参照ドメイン](/help/components/dimensions/original-referring-domain.md)
* [製品](/help/components/dimensions/product.md)
* [参照ドメイン](/help/components/dimensions/referring-domain.md)
* [検索エンジン](/help/components/dimensions/search-engine.md)
* [検索キーワード](/help/components/dimensions/search-keyword.md)
* [トラッキングコード](/help/components/dimensions/tracking-code.md)
* [通算訪問回数](/help/components/dimensions/visit-number.md)

>[!NOTE]
>
>指標（[ 注文 ](/help/components/metrics/orders.md) または [ カスタムイベント ](/help/components/metrics/custom-events.md) など）は「スナップショット」には含まれません。

一致するトランザクション ID を含むデータソースを介してオフラインヒットをアップロードすると、「スナップショット」内で使用可能なすべてのディメンションがデータソース行に自動的に追加されます。 特定のディメンションがオンラインヒットとオフラインヒットの両方に存在する場合は、オフラインヒットの値が使用されます。

>[!IMPORTANT]
>
>トランザクション ID データソースの概念は、データソース行（オフラインヒット）の入力にのみ役立ちます。 オンラインヒットに影響を与えたり、変更したりすることはありません。

## トランザクション ID データソースの考慮事項

トランザクション ID データソースには、次のプロパティがあります。

* 最初にオンラインデータを収集して処理する必要があります。 トランザクション ID データソースがアップロードされた後に、そのトランザクション ID に一致するヒットがレポートスイートによって処理される場合、そのデータは概要データソースと同様に扱われます。
* オンラインヒットから収集されたトランザクション ID は 25 か月後に有効期限が切れます。
* 有効期限切れのトランザクション ID でアップロードされたデータソースは、トランザクション ID のないアップロードされたデータと同様に扱われます。
* 複数のオンラインヒットに同じトランザクション ID を設定した場合は、最初の発生の「スナップショット」のみが使用されます。 後続の重複トランザクション ID オンラインヒットは、トランザクション ID がないかのように処理されます。
* 指定の `transactionID` 値を入力すると、関連する「スナップショット」は、そのトランザクション ID の有効期限が切れるまで不変と見なされます。
* 複数のデータソース行に同じトランザクション ID を設定すると、オンラインヒットで使用可能なすべてのディメンションが各オフラインヒットに追加されます。 同じトランザクション ID のオフラインヒットは、互いに何も認識しません。オフラインヒットの間でデータが渡されることはありません。
