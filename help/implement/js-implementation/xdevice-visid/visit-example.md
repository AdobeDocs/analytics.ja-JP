---
description: 一般的な顧客インタラクションで送信されるサーバーコールのサンプルを含む例です。
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: 訪問の例
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 訪問の例

>[!IMPORTANT]
>
>デバイスをまたいで訪問者を識別するこの方法は、非推奨になりました。詳しくは、 [Adobe Experience Cloud Device Co-opのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

一般的な顧客インタラクションで送信されるサーバーコールのサンプルを含む例です。

| サーバーコール | アクション | 訪問者 ID Cookie | 訪問者 ID 変数 | 有効な訪問者 ID | 訪問ページ番号 | 訪問回数 |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | 訪問者がマーケティング用の電子メールにあるリンクをクリックして、家のコンピューターからサイトを訪問します。この訪問者は過去 7 回このサイトを訪問しています。 | 1 | - | 1 | 1 | 8 |
| 2 ～ 8 | サイトの別の 7 つのページに訪問します。 | 1 | - | 1 | 2 ～ 8 | 8 |
| 9 | 家のコンピューターを認証します。 | 1 | CID1 | CID1 | 9 <br>これは CID1 の初回ヒットです。そのため、訪問者 ID 1 の訪問者プロファイルを引き継ぎ、継続します。</br> | 8 |
| 10 | 別の 1 つのページを訪問します。 | 1 | CID1 | CID1 | 10 | 8 |
| 11 | オフィスのノートブックパソコンからサイトを開きます。この訪問者は過去にこのデバイスを使用してこのサイトを訪問したことがありません。 | 2 | - | 2 | 1 | 1 |
| 12 | ノートブックパソコンを認証します。 | 2 | CID1 | CID1 | 1 | 9 |
| 13 | 別の 1 つのページを表示します。 | 2 | CID1 | CID1 | 2 | 9 |
