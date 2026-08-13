---
title: 同意管理のオプトアウト
description: 訪問者がオプトアウトしたプライバシー設定を確認します。
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
TQID: https://experienceleague.adobe.com/tsMhHR84qhEUZIZjPTluCJOHMPc37-JRwLsipAycgJI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 265
ht-degree: 93%

---

# 同意管理のオプトアウト

「同意管理オプトアウト」 [ ディメンション ](overview.md)には、訪問者が明示的にオプトアウトしたプライバシー設定が表示されます。 このディメンションを使用して、プライバシー設定に基づいてデータをフィルタリングしたり、最も一般的なプライバシーオプトアウトの理由を確認したりできます。

## このディメンションへのデータ入力

このディメンションは、次の[コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)からデータを収集します。

* `1` に設定されている場合は `contextData.['cm.ssf']`。 `cm.ssf` が `0` に等しいか、または空の場合、この変数はなにもしません。
* `N` に設定されている場合は `contextData.['opt.dmp']`。 `opt.dmp` が `Y` に等しい場合、代わりに[同意管理のオプトイン](cm-opt-in.md)ディメンションが設定されます。
* `N` に設定されている場合は `contextData.['opt.sell']`。 `opt.sell` が `Y` に等しい場合、代わりに[同意管理のオプトイン](cm-opt-in.md)ディメンションが設定されます。

これらのコンテキストデータ変数を実装するためのロジックは、お客様の組織が決定します。 これらの変数は、設定されたヒットを超えて存続しないので、各ページでコンテキストデータ変数を設定する必要があります。

## ディメンション項目

ディメンション項目には、次の 3 つの値が含まれます。

* **`SSF`**：訪問者が[サーバーサイド転送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)をオプトアウトした。 このディメンション項目は、コンテキストデータ変数 `cm.ssf` が `1` に等しい場合に存在します。 詳しくは、Audience Manager ユーザーガイドの[データプライバシーの概要](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=ja)を参照してください。 ヒットは、Adobe Audience Manager に転送されません。
* **`DMP`**：訪問者がデータ管理プラットフォームへの共有をオプトアウトした。 このディメンション項目は、コンテキストデータ変数 `opt.dmp` が `N` に等しい場合に存在します。 `SSF` と同様に、ヒットは、Adobe Audience Manager に転送されません。
* **`SELL`**：訪問者がサードパーティへのデータの共有や販売をオプトアウトした。 このディメンションは、コンテキストデータ変数 `opt.sell` が `N` に等しい場合に存在します。
