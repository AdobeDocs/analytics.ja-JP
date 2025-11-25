---
title: 分類セットの作成
description: 分類セットを作成する際に使用できるフィールドと説明について学習します。
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: ec49a5fd5771e4ca0a35ead681b556336bbc7031
workflow-type: ht
source-wordcount: '442'
ht-degree: 100%

---

# 分類セットの作成と編集

分類セットマネージャーから分類セットを[作成](#create-a-classification-set)および[編集](#edit-a-classification-set)します。

## 分類セットを作成

分類セットを作成するには：

1. Adobe Analytics の上部メニューバーで&#x200B;**[!UICONTROL コンポーネント]**&#x200B;を選択し、**[!UICONTROL 分類セット]**&#x200B;を選択します。
1. **[!UICONTROL 分類セット]**&#x200B;で、「**[!UICONTROL 分類セット]**」タブを選択します。
1. ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新規]** を選択します。
1. **[!UICONTROL 新しい分類セットを追加]**&#x200B;ダイアログで、次の手順を実行します：

   ![分類セット - 新しい分類セットを追加](assets/classifications-sets-new.png)

   1. **[!UICONTROL 名前]**&#x200B;を入力します。例：`Classification Set Example`。
   1. **[!UICONTROL 説明（オプション）]**&#x200B;を入力します。例：`Example classification set`。
   1. 「**[!UICONTROL 問題を通知]**」に 1 つ以上のメールアドレス（コンマ区切り）を入力します。問題に関するメール通知がこれらのユーザーに送信されます。
   1. 分類セットの&#x200B;**[!UICONTROL タイプ]**&#x200B;を選択します。使用可能なタイプは次のとおりです：
      * **[!UICONTROL プライマリ]**&#x200B;プライマリ分類セットは、Adobe Analytics で収集されたディメンションに適用されます。プライマリ分類は、詳細なディメンション値を、より有意義なデータレベルにグループ化（分類）する方法です。例えば、内部検索キーワードを内部検索カテゴリにグループ化して、検索データのテーマを把握することができます。または、商品 SKU をカラーまたはカテゴリ別に分類します。
         * 1 つ以上の&#x200B;**[!UICONTROL サブスクリプション]**&#x200B;を入力します。1 つの分類セットに対して複数の&#x200B;**[!UICONTROL レポートスイート]**&#x200B;と&#x200B;**[!UICONTROL ディメンション]**&#x200B;の組み合わせを定義できます。

         * 「![CrossSize400](/help/assets/icons/CrossSize400.svg)」を選択して、**[!UICONTROL レポートスイート]**&#x200B;と&#x200B;**[!UICONTROL キーディメンション]**&#x200B;の組み合わせを削除します。

        別の分類セットに既に存在する&#x200B;**[!UICONTROL レポートスイート]**&#x200B;と&#x200B;**[!UICONTROL キーディメンション]**の組み合わせを追加すると、その組み合わせの下に赤いメッセージが表示されます。
次の対応ができます。
         * 「**[!UICONTROL 既存に追加]**」を選択して他の分類セットを開き、その他の分類セットの[スキーマに分類を追加](schema.md)します。
         * **[!UICONTROL レポートスイート]**&#x200B;と&#x200B;**[!UICONTROL キーディメンション]**&#x200B;を、既に別の分類セットに登録されていない組み合わせに変更します。
      * **[!UICONTROL 参照]**。子の分類または下位分類と呼ばれることが多いルックアップテーブルは、プライマリ分類の分類です。参照は、元のディメンションではなく、分類値に関するメタデータです。例えば、*製品*&#x200B;ディメンションは、*カラーコード*&#x200B;というプライマリ分類を持つ場合があります。次に、*カラー名*&#x200B;のルックアップテーブルを&#x200B;*カラーコード*&#x200B;に添付して、各カラーコードを説明できます。
1. 「**[!UICONTROL 保存]**」を選択して分類セットを保存します。「**[!UICONTROL キャンセル]**」を選択して、定義をキャンセルします。
1. 分類セットのスキーマを定義するには、新しく作成した分類セットを&#x200B;**[!UICONTROL 分類セット]**&#x200B;マネージャーから選択して、[分類セットを編集](#edit-a-classification-set)します。


## 分類セットの作成

分類セットを編集するには：

1. Adobe Analytics の上部メニューバーで「**[!UICONTROL コンポーネント]**」、「**[!UICONTROL 分類セット]**」の順に選択します。
1. 「**[!UICONTROL 分類セット]**」で、「**[!UICONTROL 分類セット]**」タブを選択します。
1. 分類セットの名前を選択します。
1. **[!UICONTROL 分類セット：_分類セット名_]**ダイアログで、分類セットの[設定](settings.md)と[スキーマ](schema.md)を定義できます。
1. 完了したら、「**[!UICONTROL 保存]**」を選択して変更を保存します。「**[!UICONTROL キャンセル]**」を選択すると、キャンセルします。


<!--


### Schema

In the Schema tab 





You can use the Classification set manager to create a classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

When creating a classification set, the following fields are available.

* **[!UICONTROL Name]**: A text field used to identify the classification set. This field cannot be edited upon creation, but can be renamed later.
* **[!UICONTROL Column Name]**: The name of the first classification dimension that you want to create. This field is the dimension name used in Analysis Workspace, and the column name when exporting classification data. You can add more column names after the classification set is created.
* **[!UICONTROL Type]**: Radio buttons that indicate the type of classification.
  * **[!UICONTROL Primary]**: Apply to dimensions collected in Analytics. They are a way to group (classify) granular dimension values into more meaningful levels of data. For example, you might want to group internal search keywords into internal search categories, to better understand themes in your search data.
  * **[!UICONTROL Lookup]**: Commonly referred to as child or subclassifications, a lookup table is a classification of a primary classification. It is metadata about a classification value, rather than the original dimension. For example, the Product variable might have a primary classification of 'Color code'. A lookup table of 'Color name' could then be attached to 'Color code' to further explain what each code means.
* **[!UICONTROL Subscriptions]** The report suites and dimensions that this classification set applies to. You can add multiple report suite and dimension combinations to a classification set.

![Create a Classification set](../../assets/classification-set-create.png)

If a classification set exists for a given report suite + variable, the classification is added to the schema instead. A given report suite + variable combination cannot belong to multiple classification sets.

-->