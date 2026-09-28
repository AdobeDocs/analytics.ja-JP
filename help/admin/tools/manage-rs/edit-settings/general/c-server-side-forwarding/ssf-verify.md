---
description: サーバーサイド転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。 これらの手順では、サーバーサイド転送が適切に有効になるように、どの指標を使用する必要があるかを示します。
solution: Analytics
title: サーバーサイド転送の実装を検証する方法
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: 'https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 60%
---
# サーバーサイド転送の実装を検証する方法

サーバーサイド転送が適切に有効になっていることを確認するには、Adobe Analytics のトラッキングリクエストの HTTP 応答を確認する必要があります。 これは、ブラウザーの開発者ツールを使用するか、Charles Web Debuggerなどのプロキシツールを使用することで実行できます。 次の手順では、サーバーサイド転送が適切に有効になるように、どの指標を使用する必要があるかを示します。

サーバーサイド転送のステータスを確認するには、次の手順を実行します。

1. 更新されたAppMeasurement コードを含むテストページを読み込みます。
1. ブラウザーのデバッグツールまたはプロキシソフトウェアを使用して、AnalyticsのトラッキングリクエストからHTTP レスポンスを調べます（「b/ss」を含む任意のパスを選択して、これを簡単にフィルタリングできます）。
1. HTTP応答を調べます。 （以下の図に示すように）応答に Audience Manager データが含まれている場合は、サーバーサイド転送が動作しています。

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>応答に `"status":"SUCCESS"` というキーと値のペアまたは 2 x 2 の画像が含まれている場合、サーバーサイド転送は適切に設定されていません。 ID サービスが適切にデプロイされていること、AppMeasurement モジュールがデプロイされていること、該当するレポートスイートが正しい組織 ID にマッピングされていること、そして Analytics 管理ツールでサーバーサイド転送が有効になっていることを確認してください。

>[!MORELIKETHIS]
>
>* [Charles Web デバッガー](https://www.charlesproxy.com/)
