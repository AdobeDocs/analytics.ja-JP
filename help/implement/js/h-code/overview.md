---
title: H コード JavaScript 実装の概要
description: サイトで H コードを実装するためのワークフローについて説明します。
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 100%

---


# H コード JavaScript 実装の概要

>[!IMPORTANT]
>
> このバージョンのデータ収集はサポートされなくなりました。[Adobe Experience Platform Launch](../../launch/overview.md) または [JavaScript 版 AppMeasurement](../overview.md) にアップグレードします。

データを収集するコードを含むページを正しく実装するには、ホストサーバーにアクセスできる必要があります。以下の手順で、Analytics の基本的な H コード実装方法を説明します。

>[!NOTE]
>
> これらの手順に従うには、`s_code.js` のコピーが既存する必要があります。アドビでは、Code Manager で H コードをダウンロードするオプションを提供しなくなりました。

1. **コア JS ファイル変数の更新**：`s_code.js` ファイルを編集し、次の変数が更新されていることを確認します。
   * `s_account` には、データの送信先のレポートスイート ID が含まれます。詳しくは、
   * `s.trackingServer` には、Cookie が保存されている場所が含まれます。[trackingServer](../../vars/config-vars/trackingserver.md) を参照してください。
1. **サイトで `s_code.js` ファイルをホストします**：このファイルは、通常、Web サーバー上で他のスクリプトと共に存在します。
1. **すべてのページで `s_code.js` を参照します**：すべての個々のページでコア JavaScript ファイルが呼び出されていることを確認します。呼び出しは、HTML `<body>` タグ内（`<head>` タグではなく）で実行します。

   >[!TIP]
   >
   > H コードでは、`s_code.js` スクリプトを `<body>` タグ内で呼び出す必要があります。他のほとんどの実装方法ではスクリプト参照は `<head>` タグ内に必要となりますが、この実装方法は異なります。
1. **各ページでページ固有の変数を定義します**：各ページには、ページ名や eVar など、個々の変数を定義する必要があります。個々の変数は、通常、各ページのインライン `<script>` タグで定義されます。
1. **デバッガーを使用して、データ収集を検証します**：[Experience Cloud デバッガー](../../validate/debugger.md)をダウンロードしてインストールし、データがアドビに送信され、ページ変数が正しく定義されていることを確認します。

## キャッシュ

JavaScript ファイルは訪問者のブラウザーでの初回の読み込み後にキャッシュされます。通常、JavaScript ファイルは 1 回のセッションで 2 回以上ダウンロードされることはありません。このファイルがサイトの各ページで使用されている場合でも、ページごとにダウンロードされることはありません。ほとんどの Web サイトでは、ユーザーは通常 1 回のセッションで複数のページを表示するので、何度も使用される JavaScript コードをこのファイルに記述しておくと、全体でダウンロードされるデータ量を削減できます。

## H コード圧縮

`s_code.js` ファイルのダウンロードサイズが問題となる場合は、GZIP を使用して `s_code.js` ファイルを圧縮することをお勧めします。GZIP はすべての主要ブラウザーでサポートされ、JavaScript 圧縮よりも高いパフォーマンスを提供します。Apache ドキュメントで [Apache Module mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) を参照してください。
