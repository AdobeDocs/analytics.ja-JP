---
title: 分類セットの作成
description: 分類セットの作成時に使用できるフィールドと説明です。
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 28%

---

# 分類セットの作成

分類セットマネージャを使用して、分類セットを作成できます。

**[!UICONTROL コンポーネント]**／**[!UICONTROL 分類セット]**／**[!UICONTROL セット]**／**[!UICONTROL 追加]**

分類セットを作成する際には、次のフィールドを使用できます。

* **[!UICONTROL 名前]**:分類セットの識別に使用されるテキストフィールド。 このフィールドは作成時には編集できませんが、後で名前を変更できます。
* **[!UICONTROL 列名]**:作成する最初の分類ディメンションの名前。 このフィールドは、Analysis Workspace で使用されるディメンション名で、分類データを書き出す際の列名です。分類セットの作成後に、列名を追加できます。
* **[!UICONTROL タイプ]**：分類のタイプを示すラジオボタン。 通常、プライマリ分類が使用され、ルックアップ分類は[サブ分類](../../c-sub-classifications.md)を表します。
* **[!UICONTROL 購読]** この分類セットが適用されるレポートスイートおよびディメンション。 分類セットには、複数のレポートスイートとディメンションの組み合わせを追加できます。

![分類セットの作成](../../assets/classification-set-create.png)

特定のレポートスイート+変数に対して分類セットが存在する場合、代わりに分類がスキーマに追加されます。 指定されたレポートスイートと変数の組み合わせは、複数の分類セットに属することはできません。