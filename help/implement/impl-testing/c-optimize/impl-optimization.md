---
description: Analytics の導入は、主に 3 つの手順にまとめることができます。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 最適化の概要
topic: Developer and implementation
uuid: 8e8ecc5b-d4b1-4d13-8525-39e4924df247
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 最適化の概要

Analytics の導入は、主に 3 つの手順にまとめることができます。

1. HTML コードのスニペットを Web サイトの各ページ（またはページテンプレート）に貼り付けます。この HTML コードスニペットのサイズは非常に小さく（400 ～ 1,000 バイト）、データ収集プロセスを容易に実行するための JavaScript 変数とその他の識別子が含まれています。
1. コードスニペットから、JavaScript ライブラリファイルを呼び出します。このファイルには、指標を収集する際に使用される Analytics 固有の JavaScript 関数が含まれています。Analytics コードが正しく導入された場合、通常は、ブラウザーで JavaScript ライブラリファイルの実行に要する時間は非常に短いです。

1. ライブラリファイルから、アドビのデータ収集サーバーにイメージリクエストが送信されます。サーバーは送信されているデータを収集し、1 x 1 の透過イメージを訪問者のブラウザーに返します。この 3 番目の手順による、ページの合計ダウンロード時間の増加はわずかなものです。

> [!NOTE]お客様は、追加の手順を実行して、Analytics のオーバーヘッドを最小限に抑えることができます。

