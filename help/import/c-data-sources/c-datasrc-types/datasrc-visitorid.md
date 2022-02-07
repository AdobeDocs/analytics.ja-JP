---
description: 汎用（トランザクション ID）カテゴリを選択して、訪問者 ID を統合することができます。
subtopic: Data sources
title: 訪問者 ID
topic-fix: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: a7a116ddc9eddc500a52111e9c002bdbee3e4a56
workflow-type: ht
source-wordcount: '224'
ht-degree: 100%

---

# VisitorID

[!UICONTROL コールセンターデータ] カテゴリを選択して、訪問者 ID を統合することができます。

[オフラインデータの統合](/help/import/c-data-sources/datasrc-integrating-offline-data.md) を参照してください。

## VisitorID のディメンション

| 列名 | 説明 |
|--- |--- |
| [!UICONTROL VisitorID] | （必須）オンラインとオフラインの両方のシステムに存在する顧客を表す一意の値。 |
| [!UICONTROL 日付] | の日付形式を使用します `MM/DD/YYYY/hh/mm/ss`（例：07/14/2017/06/00/00）。 |
| [!UICONTROL トラッキングコード] | トラッキングコード名。 |
| [!UICONTROL カテゴリ] | カテゴリ名。カテゴリを指定する場合、製品も指定する必要があります。 |
| [!UICONTROL チャネル] | チャネル名。 |
| [!UICONTROL eVar ]*n* | eVar *n* 名。*n* には 1～75 の整数を指定できます。 |
| [!UICONTROL 製品] | 製品名。 |
| [!UICONTROL 都道府県] | 都道府県名。 |
| [!UICONTROL 郵便番号] | 郵便番号。 |

## 訪問者 ID の指標

| 列名 | 説明 |
| --- | --- |
| [!UICONTROL クリックスルー数] | トラッキングコードの表示数。 |
| [!UICONTROL 買い物かごへの追加] | 買い物かごに追加された回数。 |
| [!UICONTROL 買い物かごが開かれた回数] | 買い物かごが開かれた回数。 |
| [!UICONTROL 買い物かごからの削除数] | 買い物かごから削除された回数。 |
| [!UICONTROL 買い物かご表示] | 買い物かごの表示回数。 |
| [!UICONTROL チェックアウト] | チェックアウトの回数。 |
| [!UICONTROL イベント ]*n* | イベント *n* が発生した回数。n には 1～100 の整数を指定できます。[!UICONTROL 表示] イベントを指定する場合、対応するデータディメンション（eVar）も指定する必要があります。例えば、eVar2 表示数を含める場合、eVar2 と値をリストに含める必要があります。 |
| [!UICONTROL eVar ]*n* 表示回数 | eVar *n* が表示された回数。*n* には 1～75 の整数を指定できます。 |
| [!UICONTROL 価格] | 製品の価格。 |
| [!UICONTROL 注文件数] | 発注された回数。 |
| [!UICONTROL 製品表示回数] | 製品の表示回数。 |
| [!UICONTROL 数量] | 販売個数。 |
