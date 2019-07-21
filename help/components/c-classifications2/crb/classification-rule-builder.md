---
description: トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベース分類を作成し、複数のレポートスイートに適用することができるようになりました。ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。
seo-description: トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベース分類を作成し、複数のレポートスイートに適用することができるようになりました。ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。
seo-title: 分類ルールビルダーのワークフロー
solution: Analytics
subtopic: '分類      '
title: 分類ルールビルダーのワークフロー
topic: 管理ツール
uuid: edb1f07e- fa86-4055-8f4b- cce2d370edbb
translation-type: tm+mt
source-git-commit: e71c24fa4762d7f0bc80fc7133ca1cd79dfaf7c5

---


# 分類ルールビルダーのワークフロー

トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベース分類を作成し、複数のレポートスイートに適用することができるようになりました。ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。

## 開始する前に重要なお知らせ

分類ルールを使用する前に、次の点に注意してください。

* 現在の分類システムでは、一度に最大1千万行しかエクスポートできません。
* 分類ルールビルダー（CRB）がエクスポートをリクエストすると、分類されたANDの未分類値の両方が取り込まれ、エクスポートの最後に未分類の値が渡されます。つまり、時間の経過とともに、未分類の値に達することなく、1,000万件の分類値を入力することができます。
* アーキテクチャは、"n"サーバーの数からCRBを取り込むことができるので、どのサーバーがどのサーバーを取得したかという不整合が生じる可能性があります。そのため、未分類の値を取得するのは非常に困難です。

This is the **workaround** for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.

## 分類ルールの概要 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理]** 者/ **[!UICONTROL 分類ルールビルダー]**

分類ルールの実装に使用する高度な手順を以下に示します。

| 手順 | 作業する場所 | 説明 |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/?f=c_classifications). | [!UICONTROL 管理] 者/ [!UICONTROL レポートスイート] / [!UICONTROL 設定] の編集/&lt;トラフィック分類またはコンバージョンの分類&gt; | 変数を選択し、その変数で使用する分類を定義します。<br>変数をルールで使用するには、事前に 1 つ以上の分類列を作成しておく必要があります。<br>分類が有効になると、インポーターおよびルールビルダーを使用して特定の値を分類できます。 |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL 管理者]／[!UICONTROL 分類ルールビルダー]／[!UICONTROL ルールセットを追加] | ルールセットは、特定の変数の分類ルールのグループです。 |
| 手順3:レポートスイートと変数の設定 | [!UICONTROL 分類ルールビルダー] /&lt;ルールセット&gt; | レポートスイートおよび変数にルールセットを適用します。 |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL 分類ルールビルダー] /&lt;ルールセット&gt; | 条件を分類に照合し、ルールに対して実行するアクションを指定します。Be familiar with the information in  [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | ルールをドラフトモードで編集してその有効性をテストします。ドラフトモードでは、ルールを実行できません。<br>この手順は、正規表現を使用 [する場合に重要](../../../components/c-classifications2/crb/classification-quickstart-rules.md)です。 |
| Step 6: [Activate valid rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | ルールが有効であることを確認したら、ルールセットをアクティブ化します。必要に応じて、既存のキーを上書きできます。詳しくは、[ルールの処理方法](../../../components/c-classifications2/crb/classification-quickstart-rules.md)を参照してください。 |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 不要なルールをセットから削除します。<br>注意：ルールを削除しても、アップロードされた分類済みデータは削除されません。See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>分類インポートツールを使用する権限を持つグループでは、分類ルールを使用できます。See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**その他のリソース**

**ブログ**:この機能について詳しくは、Digital Marketing Blogを参照してください。 [ルールベースの分類](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)を参照してください。

**ビデオ**: [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) にアクセスして [!UICONTROL 分類の概要] ビデオをご覧ください。
