---
description: 汎用（トランザクション ID）カテゴリを選択して、トランザクション ID を統合することができます。
seo-description: 汎用（トランザクション ID）カテゴリを選択して、トランザクション ID を統合することができます。
seo-title: トランザクション ID
solution: Analytics
subtopic: データソース
title: トランザクション ID
topic: 開発者と実装
uuid: f3370bb7-3f28-460b- a20d- c9e58d7301d4
translation-type: tm+mt
source-git-commit: e9cb3575780db9eb5c9a766ef20d596e504a20d0

---


# トランザクション ID

汎用（トランザクション ID）カテゴリを選択して、トランザクション ID を統合することができます。

「オフラインデータ [の統合」を](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6)参照してください。

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**トランザクション ID のディメンション**

| 列名 | 説明 |
|--- |--- |
| トランザクション ID | （必須）オフラインアクティビティを導いたオンライントランザクションを表す一意の値。 |
| 日付 | MM/DD/YYYY/HH/mm/SS の日付フォーマットを使用します（例：01/01/2015/06/00/00）。 |
| トラッキングコード | トラッキングコード名。 |
| カテゴリ | カテゴリ名。カテゴリを指定する場合、製品も指定する必要があります。 |
| チャネル | チャネル名。 |
| eVarN | eVarN名。Nの有効な値は、1~250の整数です。 |
| 製品 | 製品名。 |
| 都道府県 | 都道府県名。 |
| 郵便番号 | 郵便番号。 |

<p class="head"> <b>トランザクション ID の指標</b> </p>



| 列名 | 説明 |
|--- |--- |
| クリックスルー数 | トラッキングコードの表示数。 |
| 買い物かごへの追加 | 買い物かごに追加された回数。 |
| 買い物かごが開かれた回数 | 買い物かごが開かれた回数。 |
| 買い物かごからの削除数 | 買い物かごから削除された回数。 |
| 買い物かご表示 | 買い物かごの表示回数。 |
| チェックアウト | チェックアウトの回数。 |
| eventN | eventNが発生した回数。Nの有効な値は、1~1000の整数です。表示イベントを指定する場合、対応するデータディメンション（eVar）も指定する必要があります。例えば、eVar2 表示数を含める場合、eVar2 と値をリストに含める必要があります。 |
| eVarnビュー数 | eVarNが表示された回数。Nの有効な値は、1~250の整数です。 |
| 価格 | 製品の価格。 |
| 購入回数 | 発注された回数。 |
| 商品ビュー | 製品の表示回数。 |
| 数量 | 販売数。 |
