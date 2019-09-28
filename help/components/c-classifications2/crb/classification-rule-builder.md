---
description: トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベース分類を作成し、複数のレポートスイートに適用することができるようになりました。ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。
seo-description: トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベース分類を作成し、複数のレポートスイートに適用することができるようになりました。ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。
seo-title: '分類ルールビルダーのワークフロー '
solution: Analytics
subtopic: 分類
title: '分類ルールビルダーのワークフロー '
topic: 管理ツール
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 分類ルールビルダーのワークフロー 

トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベース分類を作成し、複数のレポートスイートに適用することができるようになりました。ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。

## Important Notice before you get started

Keep this in mind before you start using classification rules:

* Our current classification system can only export up to 10 million rows at a time.
* When classification rule builder (CRB) requests an export, it pulls both classified AND unclassified values, with unclassified values coming through at the end of the export. This means that, over time, you could fill up 10 million classified values - without ever getting to the unclassified values.
* Because the architecture is set up in a way that CRB could be pulling from "n" number of servers, this can lead to inconsistencies as to which servers get picked up and in what order. For that reason, it is very difficult to get to unclassified values.

This is the workaround for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.****

## 分類ルールの概要 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理者]** /分 **[!UICONTROL 類ルールビルダー]**

分類ルールを実装するための高レベルの手順を次に示します。

| 手順 | 作業する場所 | 説明 |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL Admin &gt; Report Suites &gt; Edit Settings &gt; &lt;Traffic Classifications or Conversion Classifications&gt;] | 変数を選択し、その変数で使用する分類を定義します。<br>変数をルールで使用するには、事前に 1 つ以上の分類列を作成しておく必要があります。<br>分類が有効になると、インポーターおよびルールビルダーを使用して特定の値を分類できます。 |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL 管理者]／[!UICONTROL 分類ルールビルダー]／[!UICONTROL ルールセットを追加] | ルールセットは、特定の変数の分類ルールのグループです。 |
| Step 3: Configure report suites and variables. | [!UICONTROL Classification Rule Builder &gt;  &lt;your rule set&gt;] | レポートスイートおよび変数にルールセットを適用します。 |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder &gt;  &lt;your rule set&gt;] | 条件を分類に照合し、ルールに対して実行するアクションを指定します。Be familiar with the information in  How Rules Are Processed.[](../../../components/c-classifications2/crb/classification-quickstart-rules.md) |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | ルールをドラフトモードで編集してその有効性をテストします。ドラフトモードでは、ルールを実行できません。<br>この手順は、正規表現を使用する場合 [に重要です](../../../components/c-classifications2/crb/classification-quickstart-rules.md)。 |
| 手順6:有効なル [ールをアクティブ化](../../../components/c-classifications2/crb/classification-rule-definitions.md)。 | [!DNL Rules Page] | ルールが有効であることを確認したら、ルールセットをアクティブ化します。必要に応じて、既存のキーを上書きできます。詳しくは、[ルールの処理方法](../../../components/c-classifications2/crb/classification-quickstart-rules.md)を参照してください。 |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 不要なルールをセットから削除します。<br>注意：ルールを削除しても、アップロードされた分類済みデータは削除されません。See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>分類インポートツールを使用する権限を持つグループは、分類ルールを使用できます。 See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**その他のリソース**

**ブログ**:この機能について詳しくは、Digital Marketing Blogを参照してください。ルー [ルベースの分類](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)。

**ビデオ**:YouTubeにアク [セスし](https://www.youtube.com/watch?v=6laI5SBXY-I) 、分類の概要 [!UICONTROL のビデオを確認] 。
