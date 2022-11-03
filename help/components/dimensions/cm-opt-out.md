---
title: 同意管理のオプトアウト
description: 訪問者がオプトアウトしたプライバシー設定を確認します。
source-git-commit: c305f74d5047db57509de8ff9ee03b8144009f5a
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 5%

---

# 同意管理のオプトアウト

「同意管理のオプトアウト」ディメンションは、訪問者が明示的にオプトアウトしたプライバシー設定を表示します。 このディメンションを使用して、プライバシー設定に基づいてデータをフィルタリングしたり、最も一般的なプライバシーオプトアウト理由を確認したりできます。

## このディメンションへのデータ入力

このディメンションは、次のデータを収集します [コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` 設定されている場合 `1`. If `cm.ssf` 次と等しい `0` またはが空白の場合、この変数は何もしません。
* `contextData.['opt.dmp']` 設定されている場合 `N`. If `opt.dmp` 次と等しい `Y`、 [同意管理のオプトイン](cm-opt-in.md) ディメンションが代わりに入力されます。
* `contextData.['opt.sell']` 設定されている場合 `N`. If `opt.sell` 次と等しい `Y`、 [同意管理のオプトイン](cm-opt-in.md) ディメンションが代わりに入力されます。

組織は、これらのコンテキストデータ変数を実装するロジックを決定します。 設定されたヒットの後は保持されないので、各ページで各コンテキストデータ変数を設定する必要があります。

## ディメンション項目

Dimension項目には次の 3 つの値が含まれます。

* **`SSF`**:訪問者がオプトアウトしました [サーバー側転送](/help/admin/admin/c-server-side-forwarding/ssf.md). このディメンション項目は、コンテキストデータ変数が存在する場合に存在します `cm.ssf` 次と等しい `1`. 詳しくは、 [データプライバシーの概要](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) (『Audience Managerユーザガイド』) を参照してください。 ヒットはAdobe Audience Managerに転送されません。
* **`DMP`**:訪問者は、データ管理プラットフォームへの共有をオプトアウトしました。 このディメンション項目は、コンテキストデータ変数が存在する場合に存在します `opt.dmp` 次と等しい `N`. 類似 `SSF`の場合、ヒットはAdobe Audience Managerに転送されません。
* **`SELL`**:訪問者は、データをサードパーティへの共有または販売をオプトアウトしました。 このディメンションは、コンテキストデータ変数が存在する場合に使用されます `opt.sell` 次と等しい `N`.
