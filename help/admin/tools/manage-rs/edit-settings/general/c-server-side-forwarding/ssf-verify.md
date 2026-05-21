---
description: サーバーサイド転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。 これらの手順では、サーバーサイド転送が適切に有効になるように、どの指標を使用する必要があるかを示します。
solution: Analytics
title: サーバーサイド転送の実装の確認方法
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 60%

---

# サーバーサイド転送の実装の確認方法

サーバーサイド転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。 これは、ブラウザーの開発者ツールを使用するか、Charles Web Debuggerなどのプロキシツールを使用することで実行できます。 次の手順では、サーバーサイド転送が適切に有効になるように、どの指標を使用する必要があるかを示します。

サーバーサイド転送のステータスを確認するには：

1. 更新されたAppMeasurement コードを含むテストページを読み込みます。
1. ブラウザーのデバッグツールまたはプロキシソフトウェアを使用して、AnalyticsのトラッキングリクエストからHTTP レスポンスを調べます（「b/ss」を含む任意のパスを選択して、これを簡単にフィルタリングできます）。
1. HTTP応答を調べます。 （以下の図に示すように）応答に Audience Manager データが含まれている場合は、サーバーサイド転送が動作しています。

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>応答に `"status":"SUCCESS"` というキーと値のペアまたは 2 x 2 の画像が含まれている場合、サーバーサイド転送は適切に設定されていません。 ID サービスが適切にデプロイされていること、アプリ測定モジュールがデプロイされていること、適用可能なレポートスイートが正しい組織 ID マップされていること、Analytics 管理ツールでサーバーサイド転送が有効になっていることを確認してください。

>[!MORELIKETHIS]
>
>* [Charles Web デバッガー](https://www.charlesproxy.com/)
