---
title: IP アドレスで除外
description: 特定の IP アドレスで生成されたデータがレポートに表示されないようにします。
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
TQID: https://experienceleague.adobe.com/OfpXjqwAyn6DDwykgQMbYMIZXNPklUVvDFU1CsuC9CU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 28%

---

# IP アドレスで除外

レポートから、社内の Web サイト活動、サイトのテスト、従業員の使用量など、特定の IP アドレスからのデータを除外できます。 データを除外すると、IP アドレスデータを除外することでレポートの精度が向上します。 さらに、サービス拒否やその他のレポートデータをゆがめる可能性のある悪意のあるイベントからデータを削除することもできます。

IP アドレスでデータを除外するには、以下の説明に従って除外を設定するか、[ ファイアウォールを設定できます](/help/technotes/ip-addresses.md)。

## IP アドレスによる除外の設定

>[!NOTE]
>
>IP アドレスで除外を設定する場合は、次の点を考慮してください。
>
>* IP アドレスによって除外されたヒットは、[サーバーコール](/help/technotes/terms.md)として請求されます。
>* プライベート IP アドレスを除外する必要はありません。 外部 IP アドレスのみがアドビのデータ収集サーバーに到達します。 プライベートアドレスには、`10.*.*.*`、`192.168.*.*`、`172.[16-31].*.*` および `169.254.*.*` が含まれます。
>* ワイルドカード指標（&#42;）を使用して、アドレスの範囲を除外できます。 例えば `[!DNL 0.0.*.0]` と入力すると、`[!DNL 0.0.0.0]` と `[!DNL 0.0.255.0]` の間の IP アドレスがすべて除外されます。 IP アドレスは 50 つまで除外できます。
>* 除外されたIP アドレスからのデータは、除外が設定されてから5分以内にシステムに入ってくる新しいヒットに対して除外されます。
>* IP アドレスに変更が加えられたときより前に取得されたヒットのデータは影響を受けません。 IP除外は、今後のデータにのみ適用されます。
>* 除外されたヒットは、[ データフィード ](/help/export/analytics-data-feed/data-feed-overview.md) （`exclude_hit = 4`としてフラグ付き）に引き続き表示されます。

IP アドレスで除外を設定するには：

1. Adobe Analyticsで、**[!UICONTROL 管理者]** > **[!UICONTROL すべての管理者]**&#x200B;を選択します。

1. 管理ページで、「**[!UICONTROL IPで除外]**」を選択します。

## IP除外でIP難読化を使用した影響

[IP難読化](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)をIP除外と共に使用した場合の影響は、各レポートスイートのIP難読化設定によって異なります。

* **IPの難読化（最後のオクテット）**: IP除外が実行される前に、IPが部分的に難読化されます。 IP除外ルールでは、常に最後のオクテットとして`0`が期待されます（ワイルドカードは`0`が含まれているため有効です）。
* **IPの難読化（IPを削除）**: IP除外の実行後、IPは完全に難読化されます。 IP除外ルールの調整は必要ありません。
