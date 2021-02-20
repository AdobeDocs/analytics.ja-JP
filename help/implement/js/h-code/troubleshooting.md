---
title: H コード実装のトラブルシューティング
description: レガシー JavaScript の実装に関する一般的な問題をいくつか説明します。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 100%

---


# H コード実装のトラブルシューティング

H コードの実装に固有のトラブルシューティング手順を以下に示します。

## head タグへの Analytics コードの配置

>[!NOTE]
>
>H コードの実装では `<body>` タグ内でコードを参照する必要がありますが、他の実装（Adobe Experience Platform Launch の使用など）では `<head>` タグ内でコードを参照する必要があります。

Analytics コードは、非表示の 1 x 1 ピクセル画像を作成します。以前は、`s_code.js` の参照を `<head>` タグに配置するのが一般的な実装方法でした。ここにコードを配置すると、画像がページレイアウトに影響を与えなくなります。また、コードは早い段階で実行され、部分的なページ読み込みのページビューをより効果的にカウントできます。

ただし、コードの特定の要素には `<body>` オブジェクトが必要です。`<head>` タグ内にある Analytics の JavaScript コードは、`<body>` オブジェクトが存在する前に実行されます。その結果、実装では [!UICONTROL ClickMap] データが収集されず、ファイルのダウンロード数、離脱リンク、接続タイプデータの自動トラッキングは実行されません。`s_code.js` へのスクリプト参照を `<head>` タグに配置しても機能しますが、結果は非常に限られたバージョンの Analytics です。

Analytics コードは、HTML ページの `<body>` タグ内の任意の場所に配置できます。Analytics コードは、可能な限り `<body>` タグの先頭に近い位置に配置することをお勧めします。ページ変数が `s_code.js` ファイルの読み込み後に設定されていることを確認してください。

>[!TIP]
>
> Adobe Analytics を Adobe Target と統合する場合は、JavaScript インクルードファイルをページの末尾に配置する必要があります。
