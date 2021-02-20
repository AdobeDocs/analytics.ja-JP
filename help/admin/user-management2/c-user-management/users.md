---
description: ユーザー管理ページでレポートのユーザーとグループを管理すると、ユーザーとグループを管理して、レポート、ツールおよびレポートスイートへのアクセスを制御できます。
subtopic: Users and groups
title: ユーザー管理の概要
topic: Admin tools
uuid: 6f1d67cd-e169-461b-9f08-eec2c6b4e6df
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 100%

---


# ユーザー管理の概要

>[!IMPORTANT]
>
>ユーザーおよび製品管理は、[Admin Console](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) に移行されます。ユーザーを移行する時期は、アドビから通知されます。すべての顧客が移行されたら、**[!UICONTROL Analytics]**／**[!UICONTROL 管理ツール]**／**[!UICONTROL ユーザー管理]**&#x200B;のヘルプコンテンツは利用できなくなります。

ユーザー管理ページでレポートのユーザーとグループを管理すると、ユーザーとグループを管理して、レポート、ツールおよびレポートスイートへのアクセスを制御できます。

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL ユーザー管理]**／**[!UICONTROL ユーザーの編集]**

## ユーザーアカウントの説明 {#section_14A7E169514A42A88E06387CC7C2E9AD}

**現在のパスワード**

<table id="table_91D1FD20C4C1411292252364328677AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 機能 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 現在のパスワード </td> 
   <td colname="col2"> <p>ユーザーアカウントを更新または作成する場合は、ログイン中の編集者自身のパスワードをこのフィールドに再入力する必要があります。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**連絡先情報**

| 要素 | 説明 |
|---|---|
| [!UICONTROL 名] | ユーザーの名。 |
| [!UICONTROL 姓] | ユーザーの姓。 |
| [!UICONTROL タイトル] | （オプション）ユーザーの肩書。 |
| [!UICONTROL 電話番号] | （オプション）ユーザーのビジネス用電話番号。 |
| [!UICONTROL 電子メールアドレス] | ユーザーのビジネス用電子メールアドレス。 |

**デフォルトのダッシュボード**

指定したレポートスイート用のデフォルトのダッシュボードを作成します。

**ログイン**

| 要素 | 説明 |
|---|---|
| [!UICONTROL ユーザー名] | ログインに使用するユーザー名。40 文字以内で入力してください。40 文字を超えるユーザー名は切り詰められます。 |
| [!UICONTROL パスワードの設定] | デフォルトのアカウントパスワード。 |
| [!UICONTROL パスワードの確認] | デフォルトのアカウントパスワード。 |
| [!UICONTROL パスワードの変更をユーザーに要求する] | （オプション）選択した場合、ユーザーは次回ログイン時にパスワードを変更する必要があります。 |
| [!UICONTROL ログイン発効日] | （オプション）一時的なアカウントが有効な期間。 |

**アクセス**

<table id="table_5CAF9AAAE7E648B4887CEB7D682292F2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle">管理者</span> </td> 
   <td colname="col2"> Analytics レポートでのすべての社内レポート、サイトおよびページに対するユーザー権限に加え、他のユーザーの追加、編集または削除をおこなうための機能を許可します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">ユーザー</span> </td> 
   <td colname="col2"> <p> ユーザーに選択されたグループの権限のみを許可します。「<span class="uicontrol">利用可能なグループ</span>」フィールド（左側）で目的のグループを選択し、「<span class="uicontrol">追加</span>」をクリックします。割り当てられたグループは「<span class="uicontrol">割り当てられたグループ</span>」フィールド（右側）に表示されます。グループの作成および管理の詳細については、<a href="/help/admin/user-management2/c-user-groups/groups.md">グループ</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**お知らせメール**

| 要素 | 説明 |
|---|---|
| [!UICONTROL ユーザーへお知らせメールを送信する] | ユーザーの電子メールアドレスに新しいアカウントについての情報と共にメッセージを自動的に送信するようにシステムに指定します。 |
| [!UICONTROL 追加メッセージ] | お知らせメールの内容を追加します。「追加メッセージ」フィールドでは HTML がサポートされますが、添付ファイルを含めることはできません。 |
| [!UICONTROL 電子メールのプレビュー] | 独立したブラウザーウィンドウにお知らせメールが表示されます。 |
| [!UICONTROL デフォルトのお知らせメッセージに設定する] | 「追加メッセージ」パネルで指定した追加の内容を含めるようにデフォルトのお知らせメッセージを変更します。 |

