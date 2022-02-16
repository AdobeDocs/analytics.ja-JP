---
description: Power BIでReport Builderを使用する際の一般的な問題。
title: Power BI 統合のトラブルシューティング
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 51%

---

# Power BI 統合のトラブルシューティング

Power BIとのReport Builderを使用する際の一般的な問題を調べ、解決します。

## Power BI への発行の失敗

スケジュールされたワークブックの Power BI 発行が成功するには、Power BI サービスが起動して動作している必要があります。発行の失敗には主に次の 2 つの理由があります。

* Power BI サービスがダウンしている。
* ワークブックをスケジュールしたユーザーの Microsoft アカウント資格情報が無効になっている。

Report Builder でスケジュールされた各タスクは、スケジュールされた実行ごとに 3 回試行されます。

* 最初の試行が失敗に終わると、「スケジュールされたこのワークブックを Microsoft Power BI に発行できませんでした。すぐにもう一度実行します」というメッセージが表示されます。
* 2 回目の試行が失敗に終わると、メッセージは表示されません。
* 3 回目の試行が失敗に終わると、「このワークブックを Power BI に発行できませんでした」というメッセージが表示されます。

## Power BI のビジュアライゼーションの破損

Report Builder リクエストを Power BI に発行した後にビジュアライゼーションが壊れる主な理由を以下に示します。

* Report Builder でリクエストを編集した（例えば、指標またはディメンションを変更して Power BI に再発行した）。リクエストを編集すると、ビジュアライゼーションが壊れる可能性があります。
* ビジュアライゼーションで使用されているリクエストを削除した。

## Report Builderは、組織のリソースにアクセスする権限を持っている必要があります。 このアクセス権は管理者のみが付与できます。 管理者に権限の付与を依頼します。

Microsoft管理者に、次の場所にある「ユーザーはアプリケーションを登録できます」設定を確認してもらいます。 **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL 「ユーザー設定」ではオプションを使用できます]**. このオプションを「いいえ」に設定すると、管理者はこの種のアプリケーションを登録できます。

ユーザーは、次の方法を使用してアクセス権を付与できます [リンク](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

管理者は、次の機能を使用して、すべてのユーザーに対してアクセス権を付与しました [リンク](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).
