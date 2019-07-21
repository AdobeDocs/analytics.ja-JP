---
description: 汎用（トランザクション ID）カテゴリを選択して、トランザクション ID を統合することができます。
seo-description: 汎用（トランザクション ID）カテゴリを選択して、トランザクション ID を統合することができます。
seo-title: トランザクション ID
solution: Analytics
subtopic: データソース
title: トランザクション ID
topic: 開発者と導入
uuid: f3370bb7-3f28-460b- a20d- c9e58d7301d4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# トランザクション ID

汎用（トランザクション ID）カテゴリを選択して、トランザクション ID を統合することができます。

See [Integrating Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**トランザクション ID のディメンション**

| 列名 | 説明 |
|--- |--- |
| トランザクション ID | （必須）オフラインアクティビティを導いたオンライントランザクションを表す一意の値。 |
| 日付 | MM/DD/YYYY/HH/mm/SS の日付フォーマットを使用します（例：01/01/2015/06/00/00）。 |
| トラッキングコード | トラッキングコード名。 |
| カテゴリ | カテゴリ名。カテゴリを指定する場合、製品も指定する必要があります。 |
| チャネル | チャネル名。 |
| eVarN | eVarN名。n には 1～250 の整数を指定できます。 |
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
| イベント n | イベント n が発生した回数。n には 1～1000 の整数を指定できます。表示イベントを指定する場合、対応するデータディメンション（eVar）も指定する必要があります。例えば、eVar2 表示数を含める場合、eVar2 と値をリストに含める必要があります。 |
| eVarnビュー数 | eVar n が表示された回数。n には 1～250 の整数を指定できます。 |
| 価格 | 製品の価格。 |
| 購入回数 | 発注された回数。 |
| 製品表示 | 製品の表示回数。 |
| 数量 | 販売数。 |