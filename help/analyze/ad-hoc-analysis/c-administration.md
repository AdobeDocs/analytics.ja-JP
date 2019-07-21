---
description: ユーザーを設定し、データサンプリングを行う方法について説明します。
seo-description: ユーザーの管理方法と、データサンプリングについて説明します。
seo-title: 管理
title: 管理
uuid: 12f90223-139f-4a8d- bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: 99078f95e45821bcee5017b4d480006c85f1c9e4

---


# 管理

ユーザーを設定し、データサンプリングを行う方法について説明します。

[!DNL Admin Console] ヘルプについては [、Analyticsリファレンス](https://marketing.adobe.com/resources/help/en_US/reference/index.html)を参照してください。

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

1. Log in to the [!DNL Experience Cloud].
1. **[!UICONTROL 管理者]** / **[!UICONTROL ユーザー管理]**&#x200B;の順にクリックします。
1. Click **[!UICONTROL Edit Groups]**.

   貴社がユーザーライセンスを購入している場合、「[!UICONTROL グループ名]」列に「[!UICONTROL Ad Hoc Analysis ライセンスユーザー]」グループが表示されます。ユーザーログインに使用できるライセンスの数も表示されます。

1. Click **[!UICONTROL Edit]**.
1. 「[!UICONTROL ユーザーログインの割り当て]**」で、グループに追加するユーザーを選択して、「[!UICONTROL 追加]」をクリックします。**
1. Click **[!UICONTROL Save Group]**.

   ライセンスシステムには、グループに追加できるユーザーの数に制限はありません。同時にアクセスできるユーザーの数は、購入したユーザーライセンスの数に制限されます。

## ユーザーセッションの管理 {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

管理者がユーザーのセッションを終了するための手順を説明します。この機能では、終了されたユーザーの再ログインを防ぐことはできません。

<!-- 

t_managing_users.xml

 -->

1. **[!UICONTROL Adobe Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL ユーザー管理をクリック]**&#x200B;し、「ユーザーを管理」をクリック ****&#x200B;します。
1. ユーザーを探し、「**[!UICONTROL 終了]」をクリックします。**

   [!UICONTROL アクティブな Ad Hoc Analysis セッション]ページで、最もアイドル時間の長いユーザーがリストの先頭に表示されます。

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

1. **[!UICONTROL Experience Cloudにログイン]**&#x200B;します。
1. **[!UICONTROL Adobe Analytics/管理者]** / **[!UICONTROL ユーザー管理]** /グループ **[!UICONTROL の編集をクリック]**&#x200B;します。
1. Click **[!UICONTROL All Report Access]**.
1. 「[!UICONTROL 利用可能なユーザー]**」で、ユーザーを選択し、「[!UICONTROL 追加]」をクリックします。**
1. Click **[!UICONTROL Save Group]**.

## 権限グループの作成 {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

特定のレポートスイート用に、管理者以外のユーザー向けの権限グループを作成します。

<!-- 

t_permission_groups.xml

 -->

1. **[!UICONTROL Experience Cloudにログイン]**&#x200B;します。
1. **[!UICONTROL Adobe Analytics/管理者]** / **[!UICONTROL ユーザー管理]** /グループ **[!UICONTROL の編集をクリック]**&#x200B;します。
1. 管理者以外のユーザー向けの権限グループを作成し、ユーザーからのアクセスを許可する、Ad Hoc Analysis が有効なレポートスイートを含めます。

   ユーザーが使用できるレポートスイートは、新しいプロジェクトを作成するときに[!UICONTROL レポート Cloud] メニューに表示されます。

## Java でのプロキシポリシーの設定 {#task_3B03F58519544025B55CF54FACF8F4F5}

サーバー接続エラーが発生した場合のプロキシポリシーを設定する手順を説明します。

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis では、サーバーとの通信に HTTP を使用します。他の HTTP トラフィックと同じプロキシポリシーが適用されます。

1. In the [!DNL Windows Control Panel], launch the [!UICONTROL Java Control Panel].
1. **[!UICONTROL 「一般»??タブで、??«ネットワーク設定??]******
1. Select **[!UICONTROL Use browser settings]**, or manually configure the proxy settings.
1. Click **[!UICONTROL OK]**, then click **[!UICONTROL OK]** on the [!UICONTROL Java Control Panel].

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

>[!MORE_LIKE_THIS]
>
>* [ユーザー](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=users)
>* [グループ ](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=groups)

