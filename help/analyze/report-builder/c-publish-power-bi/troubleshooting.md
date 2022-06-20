---
description: Report Builder を Power BI で使用する際の一般的な問題。
title: Power BI 統合のトラブルシューティング
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: f6f65f34c4d8caf04eb3ea47108e36e5b9adf24f
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 89%

---

# Power BI 統合のトラブルシューティング

Report Builder を Power BI で使用する際の一般的な問題を調べ、解決します。

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

## Report Builder が組織のリソースにアクセスする権限を持っている必要があります。このアクセス権は管理者のみが付与できます。 管理者に権限の付与を依頼します。

Microsoft 管理者に、**[!UICONTROL Microsoft Azure]**／**[!UICONTROL Azure Active Directory]**／**[!UICONTROL ユーザー設定]**&#x200B;許可オプションの下にある「ユーザーはアプリケーションを登録できる」設定を確認してもらいます。このオプションを「いいえ」に設定すると、管理者がこのタイプのアプリケーションを登録できます。

ユーザーは、次の[リンク](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)を使用してアクセス権を付与できます。

管理者は、次の[リンク](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)を使用して、すべてのユーザーにアクセス権を付与しました。

## API 制限への到達

Power BIのレポートは Analytics レポート API で機能するので、API しきい値の制限が適用されます。 詳しくは、 [Web サービスのエラーコード](https://github.com/AdobeDocs/analytics-1.4-apis/blob/3dda746890743c2098256719d6595109b7748262/docs/getting-started/c_Web_Services_Error_Codes.md).
