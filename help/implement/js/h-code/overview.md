---
title: HコードJavaScript実装の概要
description: サイトにHコードを導入するためのワークフローについて説明します。
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# HコードJavaScript実装の概要

> [!IMPORTANT] このバージョンのデータ収集はサポートされなくなりました。 Adobe Experience Platform Launchまたは [AppMeasurement for javaScript](../../launch/overview.md) にア [ップグレードします](../overview.md)。

データを収集するコードを含むページを正しく実装するには、ホストサーバーにアクセスできる必要があります。 以下の手順で、Analytics hコードの基本的な実装を説明します。

> [!NOTE] これらの手順に従うには、の既存のコピーが既に `s_code.js` 存在する必要があります。 アドビでは、コードマネージャーでHコードをダウンロードするオプションを提供しなくなりました。

1. **コアJSファイル変数の更新**:ファイルを編 `s_code.js` 集し、次の変数が更新されていることを確認します。
   * `s_account` データの送信先のレポートスイートIDが含まれます。 詳しくは、     
   * `s.trackingServer` には、cookieが保存されている場所が含まれます。 [trackingServer](../../vars/config-vars/trackingserver.md) を参照してください。
2. **サイトで`s_code.js`ファイルをホスト**:このファイルは、通常、Webサーバー上の他のスクリプトと共に存在します。
3. **すべての`s_code.js`ページの参照**:すべての個々のページでコアJavaScriptファイルが呼び出されていることを確認し、（タグではなく）HTML `<body>` タグ内で呼び出 `<head>` します。
   > [!TIP] Hコードでは、タグ内でス `s_code.js` クリプトを呼び出す必要があ `<body>` ります。 これは他の実装方法とは異なり、そのほとんどがタグ内でスクリプト参照を必要とし `<head>` ます。
4. **各ページでページ固有の変数を定義します**。各ページには、ページ名やeVarなど、個々の変数を定義する必要があります。 個々の変数は、通常、各ページのインラインタ `<script>` グで定義されます。
5. **デバッガーを使用して、データ収集を検証します**。Experience cloudデバッガーをダウンロ [ードしてインストールし](../../validate/debugger.md) 、データがアドビに送信され、ページ変数が正しく定義されていることを確認します。

## キャッシュ

JavaScript ファイルは訪問者のブラウザーでの初回の読み込み後にキャッシュされます。通常、JavaScript ファイルは1 回のセッションで 2 回以上ダウンロードされることはありません。このファイルがサイトの各ページで使用されている場合でも、ページごとにダウンロードされることはありません。ほとんどの Web サイトでは、ユーザーは通常 1 回のセッションで複数のページを表示するので、何度も使用される JavaScript コードをこのファイルに記述しておくと、全体でダウンロードされるデータ量を削減できます。

## Hコード圧縮

ファイルのダウンロードサイズが問題となる場合は、GZIPを `s_code.js` 使用してファイルを圧縮するこ `s_code.js` とをお勧めします。 GZIPはすべての主要ブラウザーでサポートされ、JavaScript圧縮よりも高いパフォーマンスを提供します。 Apacheドキ [ュメントのApache Module mod_deflateを参照](http://httpd.apache.org/docs/current/mod/mod_deflate.html) 。
