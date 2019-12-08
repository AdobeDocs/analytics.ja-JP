---
description: 「データ層」とは、開発者がページに挿入する JavaScript オブジェクトのフレームワークのことを指します。
keywords: Analytics Implementation;data layer;digitalData
title: データ層
topic: Developer and implementation
uuid: dedb2a50-06f3-4354-8993-a25d4952ce1e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# データ層

「_データ層_」とは、開発者がページに挿入する JavaScript オブジェクトのフレームワークのことを指します。データ層は、トラッキングツール（Adobe Experience Platform Launch や Dynamic Tag Management といったタグ管理システムなど）でレポートへの情報入力に使用できます。

サイトにデータ層を導入することで、導入を詳細かつ柔軟に制御し、以降の管理を簡略化できます。これらの JavaScript オブジェクトの名前は、理論上はどのようなものでも構いませんが、一貫性のあるわかりやすい名前にすることをお勧めします。開発者が既にデータ層を用意していたり、好みのフォーマットがある場合もあります。トラッキング関連のコミュニティでは、ベースとなる標準規格がいくつか作成されています。[Analytics の導入用のデータ層](assets/datalayer-documentation.pdf)の仕様ドキュメントでは、この DTM による導入以外にもデータ層を使用する必要があるケースに備え、様々なトラッキング技術で使用できる W3C 標準規格の「digitalData」オブジェクトを使用しています。
