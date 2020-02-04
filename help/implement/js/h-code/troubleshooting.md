---
title: Hコードの導入のトラブルシューティング
description: レガシーJavaScriptの導入に関する一般的な問題をいくつか説明します。
translation-type: tm+mt
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# Hコードの導入のトラブルシューティング

Hコードの実装に固有のトラブルシューティング手順を以下に示します。

## head タグへの Analytics コードの配置

> [!NOTE] Hコードの実装ではタグ内でコードを参照する必要がありますが、他の実装（Adobe Experience Platform Launchの使用など） `<body>` ではタグ内でコードを参照する必要があ `<head>` ります。

Analyticsコードは、非表示の1 x 1ピクセルの画像を作成します。 以前は、タグに参照を配置するのが一般的 `s_code.js` な導入方法で `<head>` した。 ここにコードを配置すると、画像がページレイアウトに影響を与えなくなりました。 また、処理が早くなり、部分的なページ読み込みに対するページビュー数をより効果的にカウントできます。

However, certain elements of the code require the existence of the `<body>` object. Analytics javaScriptコードがタグ内にある場合は、オ `<head>` ブジェクトが存在する前に実行 `<body>` されます。 As a result, your implementation does not collect [!UICONTROL ClickMap] data, automatic tracking of file downloads or exit links, or connection type data. タグにスクリプト参照を `s_code.js` 配置す `<head>` ると機能しますが、結果は非常に限られたバージョンのAnalyticsです。

The Analytics code can be placed anywhere inside the `<body>` tag of a well-formed HTML page. Analyticsコードは、可能な限りタグの先頭に近い位置に配置するこ `<body>` とをお勧めします。 ファイルの読み込み後に、ページ変数が設定されていることを確 `s_code.js` 認してください。

> [!TIP] Adobe AnalyticsをAdobe targetと統合する場合は、JavaScriptインクルードファイルをページの下部に配置する必要があります。
