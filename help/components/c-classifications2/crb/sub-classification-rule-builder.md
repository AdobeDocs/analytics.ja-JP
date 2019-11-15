---
description: 分類ルールビルダーを下位分類と組み合わせることで、分類の管理をシンプル化し、必要なルール数を削減できます。トラッキングコードに、個別に分類したいコードが含まれているような場合に、この方法を使用できます。
solution: Analytics
subtopic: Classifications
title: 下位分類とルールビルダー - 使用事例
topic: Admin tools
uuid: 6db6a4a9-b93c-413b-8049-1e6cc1ba4a38
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 下位分類とルールビルダー - 使用事例

分類ルールビルダーを下位分類と組み合わせることで、分類の管理をシンプル化し、必要なルール数を削減できます。トラッキングコードに、個別に分類したいコードが含まれているような場合に、この方法を使用できます。

## 下位分類とルールビルダー - 使用事例 {#concept_6C8672C242544D7487E82886BBFABE6E}

分類ルールビルダーを下位分類と組み合わせることで、分類の管理をシンプル化し、必要なルール数を削減できます。トラッキングコードに、個別に分類したいコードが含まれているような場合に、この方法を使用できます。

See [Sub-Classifications](/help/components/c-classifications2/c-sub-classifications.md) for conceptual information about sub-classifications.

**例**

以下のようなトラッキングコードがあるとします。

`channel:broad_campaign:creative`

分類階層を使用すると、分類に対して分類を適用できます（ *`sub-classification`*). つまり、複数のテーブルが含まれるリレーショナルデータベースのようにインポーターを使用することができます。あるテーブルでトラッキングコード全体をキーにマッピングし、別のテーブルでこれらのキーをさらに別のテーブルにマッピングします。

![](assets/sub_class_table.png)

この構造を作成したら、[分類ルールビルダー](/help/components/c-classifications2/crb/classification-rule-builder.md)を使用して、参照テーブル（前述の画像の緑と赤のテーブル）を更新するだけの小さなファイルをアップロードできます。次に、このルールビルダーを使用して、メインの分類テーブルを最新の状態に維持できます。

以下のタスクで、この実現方法を説明します。

## Set up Sub-Classifications using the Rule Builder{#task_2D9016D8B4E84DBDAF88555E5369546F}

<!-- 

t_rule_builder_subclass.xml

 -->

ルールビルダーを使用して下位分類をアップロードする方法についての手順の例を説明します。

>[!NOTE]
>
>次の手順では、下位分類とルールビルダーで説明した使用例 [を達成する方法を説明します](/help/components/c-classifications2/crb/sub-classification-rule-builder.md)。

1. [分類マネージャー](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html)で、分類と下位分類を作成します。

   例：

   ![ステップ情報](assets/sub_class_create.png)

1. In the [Classifications Rule Builder](/help/components/c-classifications2/crb/classification-rule-builder.md), classify the sub-classification key from the original tracking code.

   この操作には、正規表現を使用します。この例では、*`Broad Campaign code`* の設定ルールで次の正規表現を使用します。

   | `#` | ルールタイプ | 一致 | 分類の設定 | 設定先 |
   |---|---|---|---|---|
   |  | 正規表現 | `[^\:]:([^\:]):([^\:]`) | Broad Campaign code | `$1` |
   |  | Regular Expression | `[^\:]:([^\:]):([^\:]`) | Creative code | `$2` |

   >[!NOTE]
   >
   >At this point, you do not populate the sub-classifications *`Campaign Type`* and *`Campaign Director`*.

1. 指定した下位分類のみを含む分類ファイルをアップロードします。

   「複数レ [ベルの分類」を参照してください](/help/components/c-classifications2/c-sub-classifications.md)。

   例：

   | キー | チャネル | Broad Campaign code | Broad Campaign code &amp;Hat;Campaign type | Broad Campaign code &amp;Hat;Campaign Director | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | Brand | Suzanne |  |
   | * |  | 222 | Brand | Frank |  |

1. 参照テーブルをメンテナンスするために、（この例のような）小さなファイルをアップロードします。

   You would upload this file, for example, when a new *`Broad Campaign code`* is introduced. このファイルは、以前に分類した値に適用されます。同様に、新しい下位分類を作成する（例えば  の副分 *`Creative Theme`* 類として)、分類フ *`Creative code`*&#x200B;ァイル全体ではなく、副分類ファイルのみをアップロードします。

   レポーティングでは、これらの下位分類はトップレベル分類と同様に機能します。これにより、分類の利用に必要となる管理上の負荷が軽減されます。
