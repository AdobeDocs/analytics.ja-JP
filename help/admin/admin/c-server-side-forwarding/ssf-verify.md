---
description: サーバー側転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。そのためには、ブラウザーの開発者ツールを使用するか、Charles Web デバッガーなどのプロキシツールを使用します。サーバー側転送が適切に有効になっていることを示すデータを確認する手順を以下に示します。
seo-description: サーバー側転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。そのためには、ブラウザーの開発者ツールを使用するか、Charles Web デバッガーなどのプロキシツールを使用します。サーバー側転送が適切に有効になっていることを示すデータを確認する手順を以下に示します。
seo-title: サーバー側転送の実装を検証する方法
solution: Audience Manager
title: サーバー側転送の実装を検証する方法
uuid: e37296cc-0120-486a- a4ca-78d648cf6a11
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# サーバー側転送の実装を検証する方法

サーバー側転送が適切に有効になっていることを確認するには、Analytics トラッキングリクエストの HTTP 応答を調べる必要があります。そのためには、ブラウザーの開発者ツールを使用するか、Charles Web デバッガーなどのプロキシツールを使用します。サーバー側転送が適切に有効になっていることを示すデータを確認する手順を以下に示します。

サーバー側転送のステータスを確認するには：

1. 更新された AppMeasurement コードを含むテストページを読み込みます。
1. ブラウザーのデバッグツールまたはプロキシソフトウェアを使用して、Analytics のトラッキングリクエストの HTTP 応答を調べます（「b/ss」を含むすべてのパスを選択することで簡単にフィルタリングできます）。
1. HTTP 応答を確認します。（以下の図に示すように）応答に Audience Manager データが含まれている場合は、サーバー側転送が動作しています。

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>If the response contains the key value pair `"status":"SUCCESS"` or a 2 x 2 image, then server-side forwarding * is not* configured correctly. IDサービスが正しくデプロイされていること、App Measurementモジュールをデプロイしたこと、適切なレポートスイートが正しいIMS組織にマッピングされていること、およびAnalytics管理コンソールでサーバー側転送が有効になっていることを確認してください。

>[!MORE_LIKE_THIS]
>
>* [Charles Web デバッガー](https://www.charlesproxy.com/)

