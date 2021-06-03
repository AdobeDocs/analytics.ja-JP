---
description: ユーザー移行の影響を受けるAPIの一覧を示します
title: ユーザー移行の影響を受けるAPI
uuid: 9a5d43be-e146-476b-961e-49ea0a30b500
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 88%

---

# ユーザー移行の影響を受けるAPI{#apis-affected-by-the-migration}

アドビでは、すべての会社が Analytics にログインする方法を [!DNL my.omniture.com] から、Adobe Experience Cloud 経由での認証に移行しています。会社の移行が始まると、Analytics Admin API の v1.3 および v1.4 経由で利用可能な Analytics 固有の権限および `GetLoginKey` メソッドによる、プログラミングを使用したユーザーの作成と管理はサポートされなくなります。これらのアクションは、[!DNL adobe.io] から Experience Cloud 全体で有効化されるようになります。

## 影響を受ける API メソッド {#section-d19051ac26cc49aeb124f767c4760254}

ユーザーの移行を開始すると、Admin API の v1.3 および v1.4 では次の API メソッドがサポートされなくなります。

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authenticate
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

## 実行できるアクション {#section-8b0b89a862614f729ebdbe092ce99027}

会社が現在これらの方法を使用している場合は、2018 年 4 月 1 日から始まった移行前通知を探してください。通知は、会社が Experience Cloud 認証への移行を開始する少なくとも 30 日前に送信されます。その時点で、これらのメソッドのサポートは中止されます。

会社がこれらのメソッドを使用していない場合は、これらのメソッドを使用して開始しないことを確認する以外のアクションは必要ありません。

追加情報については、以下を参照してください。

* [一般ユーザー管理情報](https://helpx.adobe.com/jp/enterprise/help/users.html)
* [adobe.io 経由でのユーザー管理 API](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [ユーザー管理 API フォーラム](https://forums.adobe.com/community/umapi/overview)
* [Analytics ユーザーアクセスおよび管理の Experience Cloud への移行](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html)
