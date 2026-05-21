---
title: H コード実装のトラブルシューティング
description: レガシー JavaScript の実装に関する一般的な問題をいくつか説明します。
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
TQID: https://experienceleague.adobe.com/DootwtTj5kDIRHKhFPeY3Fnt3bWdVLsXc6J3UEc5LPI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 100%

---

# H コード実装のトラブルシューティング

H コードの実装に固有のトラブルシューティング手順を以下に示します。

## head タグへの Analytics コードの配置

>[!NOTE]
>
>H コードの実装では `<body>` タグ内でコードを参照する必要がありますが、他の実装（Adobe Experience Platform のタグの使用など）では `<head>` タグ内でコードを参照する必要があります。

Analytics コードは、非表示の 1 x 1 ピクセル画像を作成します。 以前は、`s_code.js` の参照を `<head>` タグに配置するのが一般的な実装方法でした。 ここにコードを配置すると、画像がページレイアウトに影響を与えなくなります。 また、コードは早い段階で実行され、部分的なページ読み込みのページビューをより効果的にカウントできます。

ただし、コードの特定の要素には `<body>` オブジェクトが必要です。 `<head>` タグ内にある Analytics の JavaScript コードは、`<body>` オブジェクトが存在する前に実行されます。 その結果、実装では [!UICONTROL ClickMap] データが収集されず、ファイルのダウンロード数、離脱リンク、接続タイプデータの自動トラッキングは実行されません。 `s_code.js` へのスクリプト参照を `<head>` タグに配置しても機能しますが、結果は非常に限られたバージョンの Analytics です。

Analytics コードは、HTML ページの `<body>` タグ内の任意の場所に配置できます。 Analytics コードは、可能な限り `<body>` タグの先頭に近い位置に配置することをお勧めします。 ページ変数が `s_code.js` ファイルの読み込み後に設定されていることを確認してください。

>[!TIP]
>
>Adobe Analytics を Adobe Target と統合する場合は、JavaScript インクルードファイルをページの末尾に配置する必要があります。
