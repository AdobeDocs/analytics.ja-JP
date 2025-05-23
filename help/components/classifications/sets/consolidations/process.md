---
title: 分類セットの統合プロセス
description: 分類セットを統合する完全なプロセス。
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: 828f41bf45c1954c3b68ad71a7746e24626b9eed
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---

# 分類セットの統合プロセス

分類の統合を使用すると、複数のデータセットから分類を取得し、それらを 1 つに結合できます。 このインタフェースを使用して、最初から最後まで分類セットの連結を作成します。 このインターフェイスは、従来の分類アーキテクチャから分類セットアーキテクチャに移行する組織にとって最も役立ちます。 分類セットアーキテクチャに既に存在するほとんどの組織は、通常、この統合ワークフローを使用する必要はありません。

## 作成

**[!UICONTROL コンポーネント]**/**[!UICONTROL 分類セット]**/**[!UICONTROL 連結]**/**[!UICONTROL 追加]**

連結を作成する場合、次のフィールドを使用できます。

* **[!UICONTROL 名前]**：統合の名前。
* **[!UICONTROL 問題の通知]**：この統合の問題を通知するメールアドレスのコンマ区切りリスト。
* **[!UICONTROL 一致するデータセット]**：すべての分類セットのドロップダウンリスト。

分類セットを選択すると、2 つの列を持つテーブルが表示されます。

* 右側の列には、統合するすべての分類セットが含まれています。 上記のドロップダウンリストを使用して選択した分類セットから開始します。
* 左側の列には、最初に選択したデータセットと結合できるすべての分類セットが含まれています。 **統合の対象にするには、スキーマが完全に一致する必要があります**。 選択した分類セットと一致しないスキーマは、この左の列には表示されません。

左側の使用可能な列から右側の統合列に目的の分類セットをドラッグします。 統合に名前を付け、2 つ以上の分類セットが右側の列に含まれたら、「**[!UICONTROL 保存して続行]**」をクリックします。

## 検証

統合を作成すると、ソースデータセットのリストが右側に表示されます。 「**[!UICONTROL 検証]**」ボタンを使用して、個々の分類セットがこの統合に対して有効であることを確認します。 ここで分類ステップを並べ替えると、分類値が一致しない場合の優先度を判断できます。 **リストの最上位の分類セットにより、他の分類セット内の一致しない値が上書きされます。**

## Run

統合を検証したら、その統合を実行できます。 統合を実行すると、次のテーブル列を含む類似性レポートが表示されます。

* **[!UICONTROL データセット名]**：分類セットの名前。
* **[!UICONTROL 不一致]**：キー値がソース分類セットと一致しなかった行の割合。 不一致の割合が高い場合は、分類データが異なる可能性があります。 選択した分類セットに類似した分類データが含まれていることを確認してください。
* **[!UICONTROL 不在]**：キー値がその分類セットには含まれているが、ソース分類セットには含まれていない行の割合。 存在しない行はすべて、統合された分類セットに追加されます。

## 承認

個々の分類セットを削除して統合分類セットに置き換える前の最後の呼び出し。 すべてが正しいことを検証してから、「**[!UICONTROL 承認]**」を選択します。

承認されると、統合された分類セットが作成されます。 ステータスは [!UICONTROL &#x200B; 完了 &#x200B;] に設定されているので、統合に対してこれ以上のアクションは必要ありません。
