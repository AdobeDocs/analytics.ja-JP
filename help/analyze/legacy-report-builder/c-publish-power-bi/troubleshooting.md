---
description: Report Builder を Power BI で使用する際の一般的な問題。
title: Power BI 統合のトラブルシューティング
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
TQID: https://experienceleague.adobe.com/Q4n08pGcqBwhUl5q3VnWhuVcW9E-tdvv3LoHSLoGleA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 382
ht-degree: 27%

---

# Power BI 統合のトラブルシューティング

{{legacy-arb}}

Report Builder を Power BI で使用する際の一般的な問題を調べ、解決します。

## Power BI への発行の失敗

Power BIの公開を必要とするスケジュール済みワークブックは、Power BI サービスの稼働開始に依存します。 公開できない主な理由は次の2つです。

* Power BIのサービスが停止している可能性があります。
* ワークブックをスケジュールしたユーザーには、有効なMicrosoft アカウントの資格情報がなくなりました。

Report Builderのスケジュールされた各タスクは、スケジュールされた実行ごとに3回の試行を取得します。

* 最初の試行が失敗すると、次のメッセージが表示されます。「このスケジュールされたワークブックをMicrosoft Power BIに公開できませんでした。 近いうちにもう一度試してみよう」と言った。
* 2回目の失敗の後、メッセージは表示されません。
* 3回目の試行が失敗すると、「このブックをPower BIに公開できませんでした」というメッセージが表示されます。

## Power BI のビジュアライゼーションの破損

Report Builder リクエストをPower BIに公開した後、ビジュアライゼーションが破損する主な理由は次のとおりです。

* 指標やディメンションの変更など、Report Builderでリクエストを編集した後、Power BIに再公開しました。 リクエストを編集すると、ビジュアライゼーションが破損する可能性があります。
* ビジュアライゼーションで使用されたリクエストを削除しました。

>[!IMPORTANT]
>
>Report Builderでは、組織のリソースへのアクセスを許可する管理者が必要です。 アクセス権が必要な場合は、管理者にアクセス権の付与を依頼してください。
> Microsoft管理者は、**[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**&#x200B;の下にある&#x200B;*Users can register application*&#x200B;設定を確認できます。 このオプションが&#x200B;**No**&#x200B;に設定されている場合、管理者はこれらの種類のアプリケーションを登録できます。

ユーザーは、[Microsoft Power BI アカウント ](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US)にログインしてアクセス権を付与できます。

管理者は、[管理者のMicrosoft Power BI アカウント ](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US)にログインして、各管理者にアクセス権を付与できます。

## APIの制限に達する

Power BIのレポート機能はAnalytics レポート APIで動作するため、APIしきい値の制限が適用されます。
