---
title: Adobe Analytics のデータを除外
description: データ収集前と収集後のデータを除外する方法について、様々な方法を説明します。
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
feature: Data Configuration and Collection
role: Admin
TQID: https://experienceleague.adobe.com/EVXvZGgeAPTcUUd035DgBAyU38hKNh8xU7nX3g7aY7o
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 356
ht-degree: 96%

---

# Adobe Analytics のデータを除外

データの除外は、通常、組織のテスト作業で実稼動データが入力されたり、または不要なデータで誤ってレポートを水増しされたりするのを防ぐために使用されます。 使用例に応じて、次のいずれかの方法を使用して、 Adobe Analytics からデータを除外します。

## データ収集後のデータの除外

次の方法では、Adobe データ収集サーバーが画像リクエストを受信した後に、Analytics レポートのデータを除外します。 これらの方法を使用して除外されたデータは、引き続き請求対象のサーバー呼び出しにカウントされます。

* **IP による除外**：Adobe Analytics は、レポートスイート内の IP アドレスまたは範囲のデータを除外する基本機能を提供しています。 管理者ユーザガイドの [IP による除外](/help/admin/tools/exclude-ip.md)を参照してください。
* **ボットルール**：ボットルールは、既知のボットユーザーエージェント文字列からトラフィックを取得し、Analytics レポートから除外します。 ボットルールによって除外したデータは、ボットレポートに配置されます。 カスタムボットルールを作成して、追加のデータを除外できます。 管理者ユーザガイドの[ボットルール](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)を参照してください。
* **VISTA ルール**：組織のニーズに応じて、要件に一致するヒットが、除外されたデータ受信専用の別のレポートスイートに送信されます。 VISTA ルールは一般的に IP アドレスに対して使用されますが、これらに限定されません。 任意のディメンションを使用して、レポートスイートにデータを含めたり、除外したりできます。 VISTA ルールには追加費用が発生する場合があります。詳しくは、Adobe アカウントチームにお問い合わせください。
* **オプトアウト Cookie**：すべてのサイト訪問者は、トラッキングサーバーに固有のページにアクセスすることにより、任意に Adobe Analytics でのトラッキングをオプトアウトできます。 実装ユーザガイドの[オプトアウトリンクの実装](/help/implement/js/opt-out.md)を参照してください。

>[!TIP]
>
>処理ルールでは、データを除外したり、別のレポートスイートにデータを送信したりできません。 ただし、特定の変数を条件付きで設定したり、セグメントを使用してそのデータをレポートから除外したりできます。

## 事前データ収集の除外

特定のヒットが Analytics データ収集サーバーに到達するのを防ぐには、[`abort`](/help/implement/vars/config-vars/abort.md) 変数を使用します。 このフラグは、イメージリクエストが送信されるのを防ぎます。 請求対象となるサーバー呼び出しは、アドビのデータ収集サーバーに到達しないため、中止したイメージクエストに対して増分されません。
