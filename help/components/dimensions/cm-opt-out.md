---
title: 同意管理のオプトアウト
description: 訪問者がオプトアウトしたプライバシー設定を確認します。
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 100%

---

# 同意管理のオプトアウト

「同意管理のオプトアウト」ディメンションには、訪問者が明示的にオプトアウトしたプライバシー設定が表示されます。このディメンションを使用して、プライバシー設定に基づいてデータをフィルタリングしたり、最も一般的なプライバシーオプトアウトの理由を確認したりできます。

## このディメンションへのデータ入力

このディメンションは、次の[コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)からデータを収集します。

* `1` に設定されている場合は `contextData.['cm.ssf']`。`cm.ssf` が `0` に等しいか、または空の場合、この変数はなにもしません。
* `N` に設定されている場合は `contextData.['opt.dmp']`。`opt.dmp` が `Y` に等しい場合、代わりに[同意管理のオプトイン](cm-opt-in.md)ディメンションが設定されます。
* `N` に設定されている場合は `contextData.['opt.sell']`。`opt.sell` が `Y` に等しい場合、代わりに[同意管理のオプトイン](cm-opt-in.md)ディメンションが設定されます。

これらのコンテキストデータ変数を実装するためのロジックは、お客様の組織が決定します。これらの変数は、設定されたヒットを超えて存続しないので、各ページでコンテキストデータ変数を設定する必要があります。

## ディメンション項目

ディメンション項目には、次の 3 つの値が含まれます。

* **`SSF`**：訪問者が[サーバーサイド転送](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)をオプトアウトした。このディメンション項目は、コンテキストデータ変数 `cm.ssf` が `1` に等しい場合に存在します。詳しくは、Audience Manager ユーザーガイドの[データプライバシーの概要](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=ja)を参照してください。ヒットは、Adobe Audience Manager に転送されません。
* **`DMP`**：訪問者がデータ管理プラットフォームへの共有をオプトアウトした。このディメンション項目は、コンテキストデータ変数 `opt.dmp` が `N` に等しい場合に存在します。`SSF` と同様に、ヒットは、Adobe Audience Manager に転送されません。
* **`SELL`**：訪問者がサードパーティへのデータの共有や販売をオプトアウトした。このディメンションは、コンテキストデータ変数 `opt.sell` が `N` に等しい場合に存在します。
