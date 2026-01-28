---
title: 分類の統合の作成と編集
description: 分類の統合を作成、検証、実行、承認およびキャンセルする方法について説明します。
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: 7cc33ac36f51b9e36657a4fe84c1ae675611b56e
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 4%

---

# 分類の統合の作成と編集

分類セットの統合を使用すると、複数の分類セットから分類を取得し、それらを 1 つに結合できます。 このインタフェースを使用して、最初から最後まで分類セットの連結を作成します。 このインターフェイスは、従来の分類から分類セットに移行する組織にとって最も役に立ちます。 分類セットを既に使用している組織では、この統合ワークフローを使用する必要はありません。

## 統合の作成 {#create-a-consolidation}


>[!CONTEXTUALHELP]
>id="classificationsets_consolidation_setpriority"
>title="分類セットの優先度"
>abstract="![ キー ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Key_18_N.svg) *分類セット* は基本分類セットで、スキーマ全体を定義します。結合の競合が発生した場合は、このセットが優先されます。 その他の分類セットは、上から順に適用されます。"


分類統合を作成するには、メイン Adobe Analytics インターフェイスで次の手順を実行します。

1. **[!UICONTROL コンポーネント]** メニューから **[!UICONTROL 分類セット]** を選択します。
1. **[!UICONTROL 分類セット]** マネージャーで、「**[!UICONTROL 統合]**」タブを選択します。
1. **[!UICONTROL 分類セット – 統合]** マネージャーで、「![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL New]**」を選択します。
1. **[!UICONTROL 新規連結]** ダイアログで、

   ![ 分類セット – 新規統合 ](assets/classifications-sets-consolidations-new.png)
   1. **[!UICONTROL 名前]**&#x200B;を入力します。例：`Consolidation Example`。
   1. **[!UICONTROL 説明（オプション）]**&#x200B;を入力します。例：`Example classification set`。
   1. 「**[!UICONTROL 問題を通知]**」に 1 つ以上のメールアドレス（コンマ区切り）を入力します。問題に関するメール通知がこれらのユーザーに送信されます。
   1. **[!UICONTROL 一致する分類セット]** ドロップダウンメニューから分類セットを選択します。

      **[!UICONTROL Source分類セット]** の左側のリストには、選択した分類リストに類似しており、統合に使用できる分類セットが表示されます。 選択した ![ キー ](/help/assets/icons/Key.svg) 分類セットが右側のリストに自動的に入力されます。 このベースセットは、スキーマ全体を定義し、結合の競合では常に優先されます。

   1. 統合する分類セットを左側のリストから選択し、選択したセットを右側のリストの選択した ![ キー ](/help/assets/icons/Key.svg) ベース **[!UICONTROL _分類セット_]** の下にドロップします。

      連結を実行すると、追加の分類セットが昇順で連結されます。 キーが複数の追加セットに存在する場合、最上位ランキングの分類セットからのキーの値が取得されます。 ![Key](/help/assets/icons/Key.svg) ベースセットと追加セットの両方にキーが存在する場合は、ベースセットの値が使用されます。

      使用されるキーの値を管理するには、ドラッグ&amp;ドロップで、リスト内の個々の分類セットと選択した分類セットを移動します。 また、![ キー ](/help/assets/icons/Key.svg) **[!UICONTROL _分類セット_]** を、ドラッグ&amp;ドロップで選択した分類セットに置き換えることもできます。

   1. 「**[!UICONTROL 保存]**」を選択して、分類の統合を保存します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。

保存すると、分類の統合は自動的に検証され、統合されます。 この検証により、個々の分類セットがこの統合に対して有効であることが確認されます。 成功すると、分類統合リストのエントリにステータス **[!UICONTROL 検証済み]** が表示されます。

連結を作成した後、次の手順は次のとおりです。

* 初期設定を変更した場合の分類の統合 [ 再検証 ](#re-validate) します。
* [ 実行 ](#run) 分類統合。
* [ 承認 ](#approve) 分類の統合。



<!--
         
  

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

The following fields are available when creating a consolidation:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Notify of issues]**: A comma-delimited list of email addresses that are notified of issues with this consolidation.
* **[!UICONTROL Dataset to match]**: A drop-down list of all classification sets.

Once you select a classification set, a table with two columns appears:

* The right column contains all classification sets that you want to consolidate. It starts with the classification set selected using the above drop-down list.
* The left column contains all classification sets eligible to be merged with the originally selected dataset. **Schemas must exactly match to be eligible for consolidation**. If schemas do not match the selected classification set, they do not appear in this left column.

Drag the desired classification sets from the available column on the left to the consolidation column on the right. Once the consolidation is given a name and two or more classification sets are in the right column, click **[!UICONTROL Save & Continue]**.

-->

## 統合の編集 {#edit-a-classification}

>[!CONTEXTUALHELP]
>id="classificationsets_consolidations_mismatch"
>title="不一致"
>abstract="統合された分類セット内の値がソース分類セットと一致しない場合のキーの不一致の割合。"

>[!CONTEXTUALHELP]
>id="classificationsets_consolidations_absent"
>title="不在"
>abstract="統合された分類セット内のキーの割合（ソースの分類セットには含まれない）。"

Adobe Analyticsのメインインターフェイスで分類の統合を編集するには：

1. **[!UICONTROL コンポーネント]** メニューから **[!UICONTROL 分類セット]** を選択します。
1. **[!UICONTROL 分類セット]** マネージャーで、「**[!UICONTROL 統合]**」タブを選択します。
1. **[!UICONTROL 分類セット統合]** マネージャーで、次の操作を行います。
   1. 分類統合の名前を選択します。 **[!UICONTROL 統合：_分類統合名_]**ダイアログが表示されます。 表示と使用可能なアクションは、統合の現在のステータスと、分類の統合を変更するオプションがまだあるかどうかによって異なります。

      | 使用可能なアクション | 説明 |
      |---|---|
      | ![ キャンセル ](/help/assets/icons/Cancel.svg)**[!UICONTROL キャンセル]** | [ 統合のキャンセル ](#cancel)。 |
      | ![ チェックマーク ](/help/assets/icons/Checkmark.svg) **[!UICONTROL 再検証]** | [ 統合を再検証します ](#re-validate)。 |
      | ![Play](/help/assets/icons/Play.svg) **[!UICONTROL Run]** | [ 連結を実行します ](#run)。 |
      | ![ThumbUp](/help/assets/icons/ThumbUp.svg) **[!UICONTROL Approve]** | [ 統合を承認 ](#approve) します。 |



### 再検証

分類の統合を再検証するには、「統合：分類の統合」ダイアログを使用します。 ![ アラート ](/help/assets/icons/Alert.svg) は、統合の再構成が必要な、統合に関する問題に関する追加情報を提供します。

![ 分類セット – 統合の再検証 ](assets/classifications-sets-consolidations-validated.png)

分類統合を再検証するには、次の手順に従います。

1. 連結を作成した場合と同じドラッグ・アンド・ドロップ・インタフェースを使用して、連結を再構成します。
1. ![ チェックマーク ](/help/assets/icons/Checkmark.svg)**[!UICONTROL 再検証]** を選択します。 検証により、個々の分類セットがこの統合に対して有効であることが確認されます。 成功すると、トーストメッセージ「![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)**[!UICONTROL 検証のために統合が正常に送信されました！]**」が表示されます。
1. ![CrossSize400](/help/assets/icons/CrossSize400.svg) を選択して、ダイアログを閉じます。 または、「![ 再生 ](/help/assets/icons/Play.svg) **[!UICONTROL 実行]**」を選択して連結を実行するか、「![ キャンセル ](/help/assets/icons/Cancel.svg) **[!UICONTROL キャンセル]**」を選択して分類をキャンセルします。



<!--
Once you have created a consolidation, a list of source datasets appears on the right. The **[!UICONTROL Validate]** button makes sure that each individual classification set is valid for this consolidation. You can reorder the classification steps here to determine priority in cases of mismatched classification values. **The highest classification set in the list overwrites any mismatched values in other classification sets.**

-->

### 実行

分類統合が正常に検証されたら、統合を実行できます。

分類連結を実行する手順は、次のとおりです。

1. 「![ 再生 ](/help/assets/icons/Play.svg)**[!UICONTROL 実行]**」を選択します。 トーストメッセージ ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)**[!UICONTROL 処理のために統合が正常に送信されました！]** が表示されます。
1. ![CrossSize400](/help/assets/icons/CrossSize400.svg) を選択して、ダイアログを閉じます。


### 承認

分類統合が正常に実行されると、統合ステータスは ![StatusOrange](/help/assets/icons/StatusOrange.svg)**[!UICONTROL Waiting for Approval]** になります。 分類統合を承認すると、個々の分類セットが統合分類セットに置き換えられ、個々の分類セットが削除されます。

![ 分類セット – 統合が承認待ち ](assets/classifications-sets-consolidations-waitingforapproval.png)

分類セットの連結を承認する手順は、次のとおりです。

1. **[!UICONTROL 類似性レポート]** レポートを使用して、統合を確認します。 このレポートには、次の列を含むテーブルが表示されます。

   * **[!UICONTROL 分類セット名]**：分類セットの名前。
   * **[!UICONTROL 不一致]**：キー値がソース分類セットと一致しない行の割合。 ミスマッチの割合が高い場合、ミスマッチは、分類データが異なすぎることを示している可能性があります。 選択した分類セットに類似した分類データが含まれていることを確認してください。
   * **[!UICONTROL 存在しない]**：キー値が ![ キー ](/help/assets/icons/Key.svg) 分類セットに含まれ、ソース分類セットには含まれない行の割合。 存在しない行はすべて、統合された分類セットに追加されます。

1. 分類の統合を承認する準備ができている場合は、「![ チェックマーク ](/help/assets/icons/Checkmark.svg)**[!UICONTROL 承認]**」を選択します。 **[!UICONTROL 統合を承認しますか？確認]** 求めるダイアログ。 「**[!UICONTROL 承認]**」を選択して、連結を承認します。 「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。

承認されると、統合された分類セットが作成されます。 ステータスが **[!UICONTROL 完了]** に設定されます。


### キャンセル

承認前に分類の統合をキャンセルできます。

分類連結を取り消す手順は、次のとおりです。

1. 「**[!UICONTROL キャンセル]**」を選択します。

   連結が取り消された後は、連結を再開できません。
1. 「**[!UICONTROL 連結の取消し]**」を選択して、連結を取り消します。 「**[!UICONTROL 戻る]** を選択して、キャンセルを元に戻します。
