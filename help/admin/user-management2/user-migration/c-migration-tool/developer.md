---
description: 'null'
seo-description: 'null'
seo-title: 移行の影響を受ける API
title: 移行の影響を受ける API
uuid: 9a5d43be- e146-476b-961e-49ea0a30b500
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# 移行の影響を受ける API{#apis-affected-by-the-migration}

## 移行の影響を受ける API {#topic-8d34296a67d74b1081c3f7e8f650f3ce}

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

* [一般ユーザー管理情報](https://helpx.adobe.com/enterprise/help/users.html)
* [adobe.io 経由でのユーザー管理 API](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [ユーザー管理 API フォーラム](https://forums.adobe.com/community/umapi/overview)
* [Analytics ユーザーアクセスおよび管理の Experience Cloud への移行](https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/)

