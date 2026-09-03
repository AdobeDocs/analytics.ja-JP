---
title: ページ変数
description: 個々のページに値を設定します。
feature: Appmeasurement Implementation
exl-id: 321d0db2-61a3-478e-ab51-8e06c7b2bb7b
role: Admin, Developer
TQID: https://experienceleague.adobe.com/mWfMumcPTklFPKUiGIOatDbC0WKW5RDYH56rXTFk3ZY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 47%

---

# ページ変数の概要

ページ変数は、レポート内のディメンションおよび指標の値を決定します。

以下のリストは、実装でよく使用される変数を示しています。

* [`pageName`](pagename.md)：ページの名前。
* [`campaign`](campaign.md)：この変数をキャンペーン追跡用のクエリ文字列パラメーターに設定します。
* [`events`](events/events-overview.md)：レポートで使用する指標を入力します。
* [`products`](products.md)：e コマースサイトを持っている場合は、訪問者が製品を閲覧または購入した際にこの変数を設定します。

## 廃止されたページ変数

次のページ変数は廃止されました。 レガシー実装で発生した場合は、参考用にここに文書化されています。

* **`hier`**: レポート用にサイトの構造をキャプチャするために階層変数（`hier1`-`hier5`）を実装しました。 これは廃止され、Analysis Workspaceでは使用できないディメンションです。 代わりに[eVars](evar.md)と分類を使用してください。
* **`state`**：通常は送料または請求フォームを通じて、訪問者が入力した米国の状態をキャプチャしました。 代わりに[[!UICONTROL US States]](/help/components/dimensions/us-states.md) ディメンションを使用します。このディメンションは、訪問者の地理的な場所からAdobeに自動的に入力されます。
