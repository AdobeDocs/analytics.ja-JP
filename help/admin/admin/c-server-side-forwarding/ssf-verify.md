---
description: サーバー側転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。そのためには、ブラウザーの開発者ツールを使用するか、Charles Web デバッガーなどのプロキシツールを使用します。サーバー側転送が適切に有効になっていることを示すデータを確認する手順を以下に示します。
solution: Analytics
title: サーバー側転送の実装の確認方法
feature: Server-Side Forwarding
exl-id: 21db4572-da3c-43aa-a774-86a089656695
source-git-commit: aa4550d7012f76571f7623428d3d4ee08f728f64
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 84%

---

# サーバー側転送の実装の確認方法

サーバー側転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。そのためには、ブラウザーの開発者ツールを使用するか、Charles Web デバッガーなどのプロキシツールを使用します。サーバー側転送が適切に有効になっていることを示すデータを確認する手順を以下に示します。

サーバー側転送のステータスを確認するには：

1. 更新された AppMeasurement コードを含むテストページを読み込みます。
1. ブラウザーのデバッグツールまたはプロキシソフトウェアを使用して、Analytics のトラッキングリクエストの HTTP 応答を調べます（「b/ss」を含むすべてのパスを選択することで簡単にフィルタリングできます）。
1. HTTP 応答を確認します。（以下の図に示すように）応答に Audience Manager データが含まれている場合は、サーバー側転送が動作しています。

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>応答に `"status":"SUCCESS"` というキーと値のペアまたは 2 x 2 の画像が含まれている場合、サーバー側転送は適切に設定されていません。ID サービスが適切にデプロイされ、App Measurement モジュールがデプロイされ、該当するレポートスイートが正しい組織 ID にマッピングされ、Analytics Admin Console でサーバー側転送が有効になっていることを確認してください。

>[!MORELIKETHIS]
>
>* [Charles Web デバッガー](https://www.charlesproxy.com/)

