---
description: トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベースの分類を作成し、複数のレポートスイートに適用することができます。 ルールは、分類関連のトラフィックの量に応じて、頻繁に処理されます。
title: 分類ルールビルダーのワークフロー
feature: Classifications
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
TQID: https://experienceleague.adobe.com/OxaFgvuHsCQwBpx9V1d5fH7ge-7YszN1ODvgBFkpgs8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 596
ht-degree: 76%

---

# 分類ルールビルダーの概要（レガシー）

{{classification-rulebuilder-deprecation}}

トラッキングコードが変更されるたびに分類の編集とアップロードを実行するのではなく、自動のルールベースの分類を作成し、複数のレポートスイートに適用することができます。 ルールは、分類関連のトラフィックの量に応じて、頻繁に処理されます。

>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [分類ルールビルダー](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/components/classifications/using-the-classification-rule-builder){target="_blank"}を参照してください。

>[!ENDSHADEBOX]

## 始める前の重要なお知らせ

分類ルールを使用する際には、次の点に注意してください。

* 一度に最大1,000万行を書き出すことができます。
* CRB が書き出しを要求すると、分類された値と未分類の値の両方を（未分類の値は書き出しの最後に）取り込みます。 つまり、時間の経過と共に、1,000 万個の分類済みの値が埋め尽くされ、未分類の値に到達しないことがあります。
* アーキテクチャは「n」台のサーバから CRB を取り込むように設定されているので、どのサーバがどの順序で取得されるかに関して不整合が生じる可能性があります。 そのため、未分類の値を取得するのは非常に困難です。

ディメンションの分類値が 1,000 万件を超える場合の&#x200B;**回避策**&#x200B;を次に示します。未分類の値は FTP 経由で 1,000 万個のバッチに書き出し、手動で分類する必要があります。

## 分類ルールの概要 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理者]**／**[!UICONTROL 分類ルールビルダー]**

分類ルールを実装するためのおおまかな手順を次に示します。

| 手順 | パフォーマンスが | 説明 |
|--- |--- |--- |
| 手順1 （前提条件）：分類スキーマを設定します。 | [!UICONTROL 管理者] > [!UICONTROL &#x200B; レポートスイート &#x200B;] > [!UICONTROL 設定の編集] > [!UICONTROL &#x200B; トラフィック分類]または[!UICONTROL &#x200B; コンバージョン分類] | 変数を選択し、その変数で使用する分類を定義します。 <br>変数をルールで使用するには、事前に 1 つ以上の分類列を作成しておく必要があります。<br>分類が有効になると、インポーターおよびルールビルダーを使用して特定の値を分類できます。 |
| 手順 2：[ルールセットを作成する](classification-rule-set.md)。 | [!UICONTROL 管理者]／[!UICONTROL 分類ルールビルダー]／[!UICONTROL ルールセットを追加] | ルールセットは、特定の変数の分類ルールのグループです。 |
| 手順 3：レポートスイートと変数を設定します。 | [!UICONTROL 分類ルールビルダー]／&lt;ルールセット> | レポートスイートおよび変数にルールセットを適用します。 |
| 手順 4：[分類ルールをセットに追加する](classification-quickstart-rules.md)。 | [!UICONTROL 分類ルールビルダー]／&lt;ルールセット> | 条件を分類に照合し、ルールに対して実行するアクションを指定します。  「[ルールの処理方法](classification-quickstart-rules.md)」の情報を確認します。 |
| 手順 5：[分類ルールセットのテスト](classification-quickstart-rules.md) | [!DNL Testing Page] | ルールをドラフトモードで編集して、検証用にテストする必要があります。 ドラフトモードでは、ルールを実行できません。<br>この手順は、[正規表現](classification-quickstart-rules.md)を使用する場合に重要です。 |
| 手順 6：[有効なルールをアクティブ化する](classification-rule-definitions.md)。 | [!DNL Rules Page] | ルールが有効であることを確認したら、ルールセットをアクティブ化します。  必要に応じて、既存のキーを上書きできます。 [&#x200B; ルールの処理方法](classification-quickstart-rules.md)を参照してください。 |
| 手順 7（任意）：[不要なルールを削除する](classification-rule-definitions.md)。 | [!DNL Rules Page] | セットから不要なルールを削除します。<br>注意：ルールを削除しても、アップロードされた分類データは削除されません。 分類データを削除する必要がある場合は、[分類データの削除](/help/components/classifications/importer/t-delete-classification-data.md)を参照してください。 |

>[!NOTE]
>
>分類インポートツールを使用する権限を持つグループが分類ルールを使用できます。 処理に関する重要な情報については、 [ルールの処理方法](classification-quickstart-rules.md) を参照してください。

**その他のリソース**

**ブログ**：この機能について詳しくは、Digital Marketing Blog の [ルールベースの分類](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/) を参照してください。

**ビデオ**：[分類の概要](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/classifications/overview-of-classifications.html?lang=ja)ビデオを参照してださい。

