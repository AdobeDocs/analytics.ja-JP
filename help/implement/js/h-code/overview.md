---
title: H コード JavaScript 実装の概要
description: サイトで H コードを実装するためのワークフローについて説明します。
feature: Implementation Basics
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
role: Developer
TQID: https://experienceleague.adobe.com/tcREdTxSH3L5XcCcu3W1aEQySJSDyAzrlQgyrutcUds
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 388
ht-degree: 79%

---

# H コード JavaScript 実装の概要

>[!IMPORTANT]
>
>このバージョンのデータ収集はサポートされなくなりました。 [Adobe Experience Platform のタグ](../../launch/overview.md)または [JavaScript 版 AppMeasurement](../overview.md) にアップグレードします。

データを収集するコードを含むページを正しく実装するには、ホストサーバーにアクセスできる必要があります。 以下の手順で、Analytics の基本的な H コード実装方法を説明します。

>[!NOTE]
>
>これらの手順に従うには、`s_code.js` のコピーが既存する必要があります。 アドビでは、Code Manager で H コードをダウンロードするオプションを提供しなくなりました。

1. **コア JS ファイル変数の更新**：`s_code.js` ファイルを編集し、次の変数が更新されていることを確認します。
   * `s_account` には、データの送信先のレポートスイート ID が含まれます。 詳しくは、
   * `s.trackingServer` には、Cookie が保存されている場所が含まれます。 [trackingServer](../../vars/config-vars/trackingserver.md) を参照してください。
1. **サイトで `s_code.js` ファイルをホストします**：このファイルは、通常、Web サーバー上で他のスクリプトと共に存在します。
1. **すべてのページで `s_code.js` を参照します**：すべての個々のページでコア JavaScript ファイルが呼び出されていることを確認します。呼び出しは、HTML `<body>` タグ内（`<head>` タグではなく）で実行します。

   >[!TIP]
   >
   >H コードでは、`s_code.js` スクリプトを `<body>` タグ内で呼び出す必要があります。 他のほとんどの実装方法ではスクリプト参照は `<head>` タグ内に必要となりますが、この実装方法は異なります。
1. **各ページでページ固有の変数を定義します**：各ページには、ページ名や eVar など、個々の変数を定義する必要があります。 個々の変数は、通常、各ページのインライン `<script>` タグで定義されます。
1. **デバッガーを使用してデータ収集を検証する**: [CX Enterprise debugger](../../validate/debugger.md)をダウンロードしてインストールし、データがAdobeに送信され、ページ変数が正しく定義されていることを確認します。

## キャッシュ

JavaScript ファイルは訪問者のブラウザーでの初回の読み込み後にキャッシュされます。通常、JavaScript ファイルは 1 回のセッションで 2 回以上ダウンロードされることはありません。 このファイルは、サイト上のすべてのページで使用されているにもかかわらず、各ページでダウンロードされるわけではありません。 ほとんどのweb サイトでは、ユーザーは1回のセッションで平均して数ページビューを超えるので、このファイルに複数回使用されるJavaScriptを転送すると、ダウンロードされるデータが全体的に少なくなります。

## H コード圧縮

`s_code.js` ファイルのダウンロードサイズが問題となる場合は、GZIP を使用して `s_code.js` ファイルを圧縮することをお勧めします。 GZIP はすべての主要ブラウザーでサポートされ、JavaScript 圧縮よりも高いパフォーマンスを提供します。 Apache ドキュメントで [Apache Module mod_deflate](https://httpd.apache.org/docs/current/ja/mod/mod_deflate.html) を参照してください。
