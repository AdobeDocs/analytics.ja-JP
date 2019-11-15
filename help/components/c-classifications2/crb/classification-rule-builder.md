---
description: トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベース分類を作成し、複数のレポートスイートに適用することができるようになりました。ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。
solution: Analytics
subtopic: Classifications
title: '分類ルールビルダーのワークフロー '
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 分類ルールビルダーのワークフロー 

トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベース分類を作成し、複数のレポートスイートに適用することができるようになりました。ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。

## 開始前の重要なお知らせ

分類ルールを使用する前に、次の点に注意してください。

* 現在の分類システムでは、一度に1,000万行までエクスポートできます。
* 分類ルールビルダー(CRB)は、エクスポートを要求すると、分類されたAND未分類の値を取り込み、未分類の値はエクスポートの最後に取り込みます。 つまり、時間の経過と共に、未分類の値に到達することなく、1,000万個の分類済みの値を埋め尽くすことができます。
* アーキテクチャは「n」台のサーバからCRBを引き出すように設定されているので、どのサーバがどの順序で取得されるかに関して不整合が生じる可能性があります。 そのため、未分類の値を取るのは非常に難しい。

ディメンショ **ンの分類値が** 1,000万を超える場合の回避策を次に示します。未分類の値は、FTP経由で1,000万個のバッチでエクスポートし、手動で分類する必要があります。

## 分類ルールの概要 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理者]** /分 **[!UICONTROL 類ルールビルダー]**

分類ルールを実装するための高レベルの手順を次に示します。

| 手順 | 作業する場所 | 説明 |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL 管理者] /レ [!UICONTROL ポートスイ] ート [!UICONTROL /設定を編集] /&lt;トラフィック分類またはコンバージョン分類&gt; | 変数を選択し、その変数で使用する分類を定義します。<br>変数をルールで使用するには、事前に 1 つ以上の分類列を作成しておく必要があります。<br>分類が有効になると、インポーターおよびルールビルダーを使用して特定の値を分類できます。 |
| Step 2: [Create a rule set](/help/components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL 管理者]／[!UICONTROL 分類ルールビルダー]／[!UICONTROL ルールセットを追加] | ルールセットは、特定の変数の分類ルールのグループです。 |
| 手順3:レポートスイートと変数を設定します。 | [!UICONTROL 分類ルールビルダー] /&lt;your rule set&gt; | レポートスイートおよび変数にルールセットを適用します。 |
| Step 4: [Add classification rules to the set](/help/components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL 分類ルールビルダー] /&lt;your rule set&gt; | 条件を分類に照合し、ルールに対して実行するアクションを指定します。「ルールの処理方法」の情 [報を確認します](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。 |
| Step 5: [Test a Classification Rule Set](/help/components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | ルールをドラフトモードで編集してその有効性をテストします。ドラフトモードでは、ルールを実行できません。<br>この手順は、正規表現を使用する場合 [に重要です](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。 |
| 手順6:有効なル [ールをアクティブ化](/help/components/c-classifications2/crb/classification-rule-definitions.md)。 | [!DNL Rules Page] | ルールが有効であることを確認したら、ルールセットをアクティブ化します。必要に応じて、既存のキーを上書きできます。詳しくは、[ルールの処理方法](/help/components/c-classifications2/crb/classification-quickstart-rules.md)を参照してください。 |
| Step 7 (Optional): [Delete unwanted rules](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 不要なルールをセットから削除します。<br>注意：ルールを削除しても、アップロードされた分類済みデータは削除されません。See  [Delete classification data](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>分類インポートツールを使用する権限を持つグループは、分類ルールを使用できます。 See [How Rules Are Processed](/help/components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**その他のリソース**

**ブログ**:この機能について詳しくは、Digital Marketing Blogを参照してください。ルー [ルベースの分類](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)。

**ビデオ**:YouTubeにアク [セスし](https://www.youtube.com/watch?v=6laI5SBXY-I) 、分類の概要 [!UICONTROL のビデオを確認] 。
