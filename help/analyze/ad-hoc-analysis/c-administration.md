---
description: ユーザーを設定し、データサンプリングを行う方法について説明します。
title: 管理
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 管理

ユーザーを設定し、データサンプリングを行う方法について説明します。

[!DNL Admin Console] については、「[解析リファレンス](https://docs.adobe.com/content/help/ja-JP/analytics/landing/home.html)」を参照してください。

## ユーザーライセンス {#concept_C1440741C77C471EB38A243B013EA620}

ユーザーがログインするには、ユーザーライセンスが与えられている必要があります。ユーザーライセンスは同時使用ライセンスです。ユーザーライセンスは共有できますが、一度に使用できるユーザーの数は、購入したユーザーライセンスの数に制限されます。

<!-- 

c_user_license.html

 -->

ログインしているユーザーの数が利用可能なライセンスの数を超えると、利用可能なライセンスはすべて使用中であることを通知するダイアログボックスが表示されます。キュー内でユーザーが何番目かという位置と、このキュー位置を再確認できるリンクが表示されます。ライセンスが使用可能になると、ユーザーに電子メールで通知され、Ad Hoc Analysis がアクセス可能になったことを通知するダイアログボックスが表示されます。ユーザーが 15 分以内にこれに応答しなかった場合は、キュー内の位置が失われます。

## ユーザーライセンスの付与 {#task_22AE669703EC48BA9685414538D8B1FA}

ローカルの Reports and Analytics 管理者が権限設定システムを使用してユーザーライセンスを付与する方法を説明します。

<!-- 

t_user_licenses.xml

 -->

1. [!DNL Experience Cloud] にログインします。
1. クリック **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. クリック **[!UICONTROL Edit Groups]**.

   会社がユーザーライセンスを購入した場合は、 [!UICONTROL Ad Hoc Analysis License Users] そのグループが列に表示さ [!UICONTROL Group Name] れます。 ユーザーログインに使用できるライセンスの数も表示されます。

1. クリック **[!UICONTROL Edit]**.
1. Under [!UICONTROL Assign User Logins], select the users you want to add to the group, then click **[!UICONTROL Add.]**
1. クリック **[!UICONTROL Save Group]**.

   ライセンスシステムには、グループに追加できるユーザーの数に制限はありません。同時にアクセスできるユーザーの数は、購入したユーザーライセンスの数に制限されます。

## ユーザーセッションの管理 {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

管理者がユーザーのセッションを終了するための手順を説明します。この機能では、終了されたユーザーの再ログインを防ぐことはできません。

<!-- 

t_managing_users.xml

 -->

1. //をク **[!UICONTROL Adobe Analytics]** リック **[!UICONTROL Admin]** し、 **[!UICONTROL User Management]**&#x200B;をクリックしま **[!UICONTROL Manage Users]**&#x200B;す。
1. Locate the user, then click **[!UICONTROL Terminate.]**

   On the [!UICONTROL Active Ad Hoc Analysis Sessions] page, the user who has been idle the longest displays at the top of list.

## 権限 {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

[!DNL Administration Console] で、ユーザーを「Ad Hoc Analysis ライセンスユーザー」グループに追加します。さらにレポートスイートのレベルで、権限を設定できます。例えば、有効なレポートスイートが複数あり、一部のユーザーにはすべてのレポートスイートへのアクセス権限を与えたくない場合は、特定のレポートスイートについてグループを作成し、ユーザーを適切なグループに割り当てます。

## ユーザーを「全レポートアクセス」グループに追加する {#task_E821BF3B4FDB434D844A98AAB15487A9}

管理者以外のユーザーにすべてのレポートスイートへのアクセス権限を与える手順を説明します。

<!-- 

t_permissions.xml

 -->

1. **[!UICONTROL Experience Cloud]** にログインします。
1. Click **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. クリック **[!UICONTROL All Report Access]**.
1. で、 [!UICONTROL Available Users]ユーザーを選択し、 **[!UICONTROL Add.]**
1. クリック **[!UICONTROL Save Group]**.

## 権限グループの作成 {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

特定のレポートスイート用に、管理者以外のユーザー向けの権限グループを作成します。

<!-- 

t_permission_groups.xml

 -->

1. **[!UICONTROL Experience Cloud]** にログインします。
1. Click **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. 管理者以外のユーザー向けの権限グループを作成し、ユーザーからのアクセスを許可する、Ad Hoc Analysis が有効なレポートスイートを含めます。

   The report suites available to the user are displayed in the [!UICONTROL Report Cloud] menu when you create a new project.

## Java でのプロキシポリシーの設定 {#task_3B03F58519544025B55CF54FACF8F4F5}

サーバー接続エラーが発生した場合のプロキシポリシーを設定する手順を説明します。

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis では、サーバーとの通信に HTTP を使用します。他の HTTP トラフィックと同じプロキシポリシーが適用されます。

1. で、を起 [!DNL Windows Control Panel]動します [!UICONTROL Java Control Panel]。
1. タブで、をク **[!UICONTROL General]** リックしま **[!UICONTROL Network Settings]**&#x200B;す。
1. プロキシ **[!UICONTROL Use browser settings]**&#x200B;設定を選択するか、手動で設定します。
1. をクリ **[!UICONTROL OK]**&#x200B;ックし、をクリ **[!UICONTROL OK]** ックしま [!UICONTROL Java Control Panel]す。

## データサンプリングの仕組み {#concept_8433CFD38E0243849E92DF4F1E743AC3}

有意義で正確なレポートを作成するために、訪問者データのサンプルを取得します。日付範囲をデータスライスとして、ロードされたプロジェクトに使用します。一般的に、1 つのスライスには現在の月と過去 2 か月が含まれます。

<!-- 

c_overview_data_sampling.xml

 -->

処理を最適化するために、ad hoc analysis ではスライスごとの最大ヒット数を約 7 億 5 千万ヒットに設定しています（ヒット数 = ページビュー数 + イベント数）。

サンプルレートを見積もるために、次のようにデータセットごとの予測ヒット数を算出し、7 億 5 千万で割ります。

* （平均日別ヒット数 x スライス内の日数）/ 7 億 5 千万

例えば、日別ヒット数が 1 千万回で、90 日間のデータスライスを使用する場合は、次のように算出します。

* （10,000,000 x 90）/ 750,000,000 = 1.2

この 90 日間のスライスのヒット数を 750,000,000 ヒット未満に抑えるためには、データを 1.2:1 でサンプリングすることになりますが、サンプリングは整数レートで行われるので、実際のサンプルレートは 2:1 となります。

また、日別ヒット数が 1 千万回で、365 日間のデータスライスを使用する場合は、次のように算出します。

* （10,000,000 x 365）/ 750,000,000 = 4.8

この 365 日間のスライスのヒット数を 750,000,000 ヒット未満に抑えるためには、データを 4.8:1 でサンプリングすることになります。これを整数レートにして、実際のサンプルレートは 5:1 となります。
