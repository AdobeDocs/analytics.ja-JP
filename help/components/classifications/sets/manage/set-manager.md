---
title: 分類セットマネージャー
description: Adobe Analyticsで分類セットを管理します。
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 5%

---

# 分類セットマネージャー

分類セットマネージャを使用すると、分類セットを作成、編集または削除できます。

**[!UICONTROL コンポーネント]**／**[!UICONTROL 分類セット]**／**[!UICONTROL セット]**

分類セットは、 **購読** （レポートスイートとディメンションの組み合わせ）および **分類名** （分類データを含むディメンション）。 配信登録は以下で設定されます [設定](settings.md)分類名は [スキーマ](schema.md).

## 分類セットをフィルター

分類セットマネージャの左側には、目的の分類セットを見つけるためのフィルター設定が表示されます。 フィルターアイコンをクリックすると、フィルター設定の表示が切り替わります。分類セットは、 **[!UICONTROL タグ]**, **[!UICONTROL レポートスイート]**&#x200B;または **[!UICONTROL 所有者]**.

![分類セットフィルター](../../assets/classification-set-filters.png)

## 分類セットマネージャーの列

分類セットマネージャでは、次の列を使用できます。

* **[!UICONTROL 分類セット]**:分類セット名。 分類セット名のクリック [設定を編集します](settings.md).
* **[!UICONTROL 購読]**:この分類セットが適用される購読の数。
* **[!UICONTROL 所有者]**:分類セットの所有者。
* **[!UICONTROL 分類]**:分類セットに含まれる分類ディメンションの数。
* **[!UICONTROL 自動]**:クラウドの場所からデータを自動的にインポートするように分類セットを設定するかどうかを指定します。 自動処理は分類セットの [スキーマ](schema.md).
* **[!UICONTROL 最終変更日]**:分類セットが最後に変更された日時。

## オプションを作成または編集

分類セットマネージャでは、次のボタンを使用できます。

* **[!UICONTROL 追加]**: [作成](create.md) 分類セット。
* **[!UICONTROL タイトルで検索]**:分類セットを名前で検索します。
* **[!UICONTROL さらに読み込み]**:分類セットマネージャには、最初に最大 1000 個の分類セットが表示されます。 このボタンは、さらに 1,000 個の分類セットを読み込みます。
* **列を表示/非表示**:以外の任意の列の表示を切り替え [!UICONTROL 分類セット].

目的の分類セットの横にあるチェックボックスをオンにして、1 つ以上の分類セットを選択します。 分類セットを選択すると、次のオプションが表示されます。

* **[!UICONTROL タグ]**:選択した分類セットに 1 つ以上のタグを追加します。これにより、分類セットを整理またはグループ化して、将来見つけやすくすることができます。
* **[!UICONTROL 削除]**:分類セットを削除します。 この分類セットに基づく分類ディメンションは使用できなくなりました。 削除された分類セットを使用するスケジュール済みプロジェクトは、スケジュール済みプロジェクトを再保存するまで、依存ディメンションを使用し続けます。
* **[!UICONTROL 統合]**:新しい [統合](../consolidations/process.md).
* **[!UICONTROL 名前を変更]**:選択した分類セットの名前を変更します。