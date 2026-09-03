---
title: トランザクション ID データソース
description: オンラインヒットから格納された値を使用して、トランザクション IDを共有するオフラインヒットを強化します。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
TQID: https://experienceleague.adobe.com/EHDN6A0p6kgCmw71I-OVc9xeRxCkKcDyfK-YzB1DI1Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 509
ht-degree: 8%

---

# トランザクション ID データソース

トランザクション ID データ ソースは、オンライン ヒットから保存された値を、同じトランザクション IDを共有するオフライン行に適用できる概要データ ソースのバリエーションです。 この方法は、オンラインでトランザクションをキャプチャし、後で別のシステムから詳細を受け取る場合に便利です。 プライマリの例には、返品、予約のキャンセル、コールセンターとのやり取りからの結果などがあります。

>[!NOTE]
>
>トランザクション ID データ ソースを使用する前に、最初に目的のレポートスイートの[一般アカウント設定](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)でトランザクション IDを有効にする必要があります。

## 仕組み

トランザクション IDの概念には、次の2つの部分が必要です。

* **オンラインヒット**:Analyticsの全ヒットがレポートスイート（AppMeasurement、Web SDK、APIなど）に送信されます。 このヒットでは、[`transactionID`](/help/implement/vars/page-vars/transactionid.md)実装変数を設定します。
* **オフラインヒット**：行がデータソースを通じてアップロードされました。 ファイル内に、オンラインヒットに一致する値を持つ`transactionID`列を含めます。

実装変数`transactionID`を含むオンラインヒットを送信すると、Adobeは、その時点で設定または保持された次のディメンションの「スナップショット」を取ります。

* [カテゴリ](/help/components/dimensions/category.md)
* [初回購入までの日数](/help/components/dimensions/days-before-first-purchase.md)
* [前回購入からの日数](/help/components/dimensions/days-since-last-purchase.md)
* [eVars 1-250](/help/components/dimensions/evar.md)
* eVarと同様に動作する[ レポートスイート設定](/help/admin/tools/manage-rs/report-suites-admin.md)で、機能固有のディメンションが有効になりました。 propと同様に動作する機能固有のディメンションは含まれません。
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
>指標（[注文](/help/components/metrics/orders.md)または[ カスタムイベント ](/help/components/metrics/custom-events.md)など）は「スナップショット」に含まれていません。

一致するトランザクション IDを含むデータソースを介してオフラインヒットをアップロードすると、「スナップショット」内の使用可能なディメンションがデータソース行に自動的に追加されます。 指定されたディメンションがオンラインとオフラインの両方のヒットに存在する場合、オフラインヒット値が使用されます。

>[!IMPORTANT]
>
>トランザクション ID データ ソースの概念は、データ ソース行（オフライン ヒット）を入力するのに役立ちます。 オンラインヒットに影響を与えたり、変更したりすることはありません。

## トランザクション ID データ ソースの考慮事項

トランザクション ID データソースには、次のプロパティがあります。

* オンラインデータは、まず収集して処理する必要があります。 レポートスイートがそのトランザクション IDに一致するヒットを処理する前にトランザクション ID データソースをアップロードすると、そのデータは概要データソースとして扱われます。
* オンラインヒットから収集されたトランザクション IDは、25か月後に有効期限が切れます。
* 期限切れのトランザクション IDでアップロードされたデータソースは、トランザクション IDなしでアップロードされたデータと同様に扱われます。
* 複数のオンラインヒットに同じトランザクション IDを設定した場合、最初に発生した「スナップショット」のみが使用されます。 後続の重複トランザクション ID オンライン ヒットは、トランザクション IDを持たない場合と同様に処理されます。
* 指定された`transactionID`値を入力すると、そのトランザクション IDが期限切れになるまで、関連付けられた「スナップショット」は不変と見なされます。
* 複数のデータソース行に同じトランザクション IDを設定すると、オンラインヒットから使用可能なディメンションが各オフラインヒットに追加されます。 同じトランザクション IDのオフラインヒットは、互いに何も知りません。オフラインヒット間でデータが渡されることはありません。
