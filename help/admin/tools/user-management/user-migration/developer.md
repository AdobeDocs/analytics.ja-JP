---
description: ユーザー移行の影響を受ける API の一覧を示します
title: ユーザー移行の影響を受ける API
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 31%

---

# ユーザー移行の影響を受ける API{#apis-affected-by-the-migration}

Adobeは、すべてのAnalytics ログイン企業を[!DNL my.omniture.com]からAdobe CX Enterprise経由の認証に移行しています。 会社の移行が始まると、Analytics Admin API の v1.3 および v1.4 経由で利用可能な Analytics 固有の権限および `GetLoginKey` メソッドによる、プログラミングを使用したユーザーの作成と管理はサポートされなくなります。 このようなアクションは、`adobe.io`を介してCX エンタープライズ全体で有効になります。

## 影響を受ける API メソッド {#methods}

Admin APIのv1.3およびv1.4の以下のAPI メソッドは、ユーザー移行の開始後はサポートされなくなります。

* Company.GetLoginKey
* Permissions.AddLogin
* 権限。認証
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## 実行できるアクション {#actions}

現在これらの方法を使用している場合は、2018年3月31日から移行前の通知を探してください。 通知は、企業がCX Enterprise認証への移行を開始する少なくとも30日前に送信され、その時点で、これらの方法はサポートされなくなります。

これらの方法のいずれかを使用しない場合は、これらの方法を使用しないように保証する以外に、アクションは必要ありません。

追加情報：

* [一般的なユーザー管理情報](https://helpx.adobe.com/jp/enterprise/help/users.html)
* [User Management API フォーラム](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Analytics ユーザーアクセスと管理のCX Enterpriseへの移行](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
