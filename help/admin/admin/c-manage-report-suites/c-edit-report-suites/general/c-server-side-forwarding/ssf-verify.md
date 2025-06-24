---
description: サーバーサイド転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。これらの手順では、サーバーサイド転送が適切に有効になっていることを示す指標を示しています。
solution: Analytics
title: サーバーサイド転送の実装の確認方法
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 86%

---

# サーバーサイド転送の実装の確認方法

サーバーサイド転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。そのためには、ブラウザーの開発者ツールを使用するか、Charles Web デバッガーなどのプロキシツールを使用します。サーバーサイド転送が適切に有効になっていることを示す指標の例を以下に示します。

サーバーサイド転送のステータスを確認するには：

1. 更新された AppMeasurement コードを含むテストページを読み込みます。
1. ブラウザーのデバッグツールまたはプロキシソフトウェアを使用して、Analytics のトラッキングリクエストの HTTP 応答を調べます（「b/ss」を含むすべてのパスを選択することで簡単にフィルタリングできます）。
1. HTTP 応答を確認します。（以下の図に示すように）応答に Audience Manager データが含まれている場合は、サーバーサイド転送が動作しています。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>応答に `"status":"SUCCESS"` というキーと値のペアまたは 2 x 2 の画像が含まれている場合、サーバーサイド転送は適切に設定されていません。ID サービスが適切にデプロイされていること、アプリ測定モジュールがデプロイされていること、適用可能なレポートスイートが正しい組織 ID マップされていること、Analytics 管理ツールでサーバーサイド転送が有効になっていることを確認してください。

>[!MORELIKETHIS]
>
>* [Charles Web デバッガー](https://www.charlesproxy.com/)
