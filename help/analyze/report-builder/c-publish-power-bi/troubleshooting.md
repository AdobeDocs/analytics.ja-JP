---
description: Report Builder を Power BI で使用する際の一般的な問題。
title: Power BI 統合のトラブルシューティング
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: b98fbf52ab9fefef9c19e82f440ca9f5a81f933f
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 66%

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

Power BIのレポートは Analytics レポート API で機能するので、API しきい値の制限が適用されます。 Analytics 2.0 API の場合、スロットル制限は、レポートスイートや会社に関係なく、ユーザーごとに 1 分あたり 120 回に設定されています。 スロットル制限を超えると、サーバーは次のメッセージコンテンツと共に HTTP 429 ステータスをユーザーに返します。

```
too many requests
{"error_code":"429050","message":"Too many requests"}
```

Adobeが推奨する *～に従う* 次のガイドラインに従います。

* 大きな 1 つのリクエストではなく、複数の小さなリクエストを作成します。
* データを 1 回リクエストし、キャッシュします。
* 30 分間隔を超える速さで新しいデータをポーリングしないでください。
* 履歴データを取り込み、データセット全体をリクエストする代わりに、定期的に増分します。

Adobeが推奨する *避ける* 以下をおこないます。

* 単一のリクエストで可能な限り多くのデータをリクエスト
* 1 日の精度で毎日 1 年分のデータをリクエストし、12 ヶ月間の周期的な期間を取得します。 Adobeでは、代わりに新しい日のデータをリクエストし、前日の既存のデータと結合することをお勧めします。
* Web ページが読み込まれるたびに API リクエストを実行することで、サイトパフォーマンスウィジェットで Web ページを起動します
* 1.4 からの移行
