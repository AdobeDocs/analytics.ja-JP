---
description: 一般的な顧客インタラクションで送信されるサーバーコールのサンプルを含む例です。
keywords: Analytics の導入
seo-description: 一般的な顧客インタラクションで送信されるサーバーコールのサンプルを含む例です。
seo-title: 訪問の例
solution: Analytics
subtopic: 訪問者数
title: 訪問の例
topic: 開発者と導入
uuid: bc5f8f56-52e3-42d8- af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 訪問の例

>[!IMPORTANT]
>
>デバイス間で訪問者を識別する方法は推奨されなくなりました。[Adobe Experience Cloud Device Co- opのドキュメント](https://marketing.adobe.com/resources/help/en_US/mcdc/)を参照してください。

一般的な顧客インタラクションで送信されるサーバーコールのサンプルを含む例です。

| サーバーコール | アクション | 訪問者 ID Cookie | 訪問者 ID 変数 | 有効な訪問者 ID | 訪問ページ番号 | 訪問回数 |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | 訪問者がマーケティング用の電子メールにあるリンクをクリックして、家のコンピューターからサイトを訪問します。この訪問者は過去 7 回このサイトを訪問しています。 | 1 | - | 1 | 1 | 8 |
| 2 ～ 8 | サイトの別の 7 つのページに訪問します。 | 1 | - | 1 | 2 ～ 8 | 8 |
| 9 | 家のコンピューターを認証します。 | 1 | CID1 | CID1 | 9 <br>This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.</br> | 1 |
| 10 | 別の 1 つのページを訪問します。 | 1 | CID1 | CID1 | 10 | 8 |
| 11 | オフィスのノートブックパソコンからサイトを開きます。この訪問者は過去にこのデバイスを使用してこのサイトを訪問したことがありません。 | 2 | - | 2 | 1 | 1 |
| 12 | ノートブックパソコンを認証します。 | 2 | CID1 | CID1 | 1 | 9 |
| 13 | 別の 1 つのページを表示します。 | 2 | CID1 | CID1 | 2 | 9 |