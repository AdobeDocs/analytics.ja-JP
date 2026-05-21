---
description: ルールセットは、特定の変数の分類ルールのグループです。 変数をルールセットに適用します。 1つの変数に複数のルールセットを作成する場合は、各ルールセットを複数のレポートスイートに適用する必要があります。
title: 分類ルールセット
feature: Classifications
exl-id: 5c118541-d143-4947-b693-514d7042abe6
TQID: https://experienceleague.adobe.com/wTH0I-JNEs-qu9DfgPVQCc6H9QMwoxoxqIFP-06QQpc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 407
ht-degree: 49%

---

# 分類ルールセット （レガシー）

{{classification-rulebuilder-deprecation}}

*このページでは、[分類ルールビルダー](classification-rule-builder.md)の一部として、分類ルールセットについて説明します。 Adobe Analyticsのデータを分類する現在の方法については、[分類セット ](../sets/overview.md)を参照してください。*

ルールセットは、特定の変数の分類ルールのグループです。 変数をルールセットに適用します。 1つの変数に複数のルールセットを作成する場合は、各ルールセットを複数のレポートスイートに適用する必要があります。

## 分類ルールビルダーページ {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL 分類ルールビルダー]**

次のフィールドとオプションは、[!UICONTROL 分類ルールビルダー]で利用できます。

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/classifications/crb/classification-rule-set.md"  >ルールセットを追加</a> </p> </td> 
   <td colname="col2"> <p>ルールセットを作成します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ルール </p> </td> 
   <td colname="col2"> セットに含まれるルールの数を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ステータス </p> </td> 
   <td colname="col2"> 「ドラフト」や「アクティブ」など、ルールセットのアクティビティステータスを表示します。 アクティブなルールは日次で処理され、通常は1か月さかのぼって分類データを調査します。 ルールは新しい値を自動的にチェックし、分類をアップロードします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最後の変更 </p> </td> 
   <td colname="col2"> ルールセットがいつ編集されたかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複製 </p> </td> 
   <td colname="col2"> ルールセットを別の変数や異なるレポートスイートの同じ変数に適用できるように、ルールセットを複製（コピー）します。 </td> 
  </tr> 
 </tbody> 
</table>

## 分類ルールセットの作成 {#create-classification-rule-set}

分類ルールセットに名前を付け、変数を適用して、上書き設定を指定します。

1. （前提条件）**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;で、分類構造を定義します。

   変数は、その変数に対して 1 つ以上の分類が定義されている場合にのみ[!UICONTROL 新しいルールセット]パネルに表示されます。

   変数の分類を作成するには、**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL トラフィック]**／**[!UICONTROL トラフィック分類]**（または&#x200B;**[!UICONTROL コンバージョン]**／**[!UICONTROL コンバージョンの分類]**）を使用します。 次に、変数を選択し、「**[!UICONTROL 分類の追加]**」をクリックします。

1. ルールセットを作成するには、**[!UICONTROL 管理者]**／**[!UICONTROL 分類ルールビルダー]**／**[!UICONTROL ルールセットを追加]**&#x200B;をクリックします。

   ![](assets/new_rule_set.png)

1. ルールセットに名前を付けて、「**[!UICONTROL ルールセットを作成]**」をクリックします。
1. 編集するルールセットを選択します。

   ![](assets/classification_rules_page.png)

1. 「**[!UICONTROL レポートスイートと変数を選択]**」をクリックします。

   レポートスイートと変数リストには、ログイン会社のすべてのレポートスイートで使用可能なすべての分類された変数が入力されます。 レポートスイート内の1つの変数は、1つのルールセットにのみ属することができます。

   詳しくは、[分類ルールビルダー](/help/components/classifications/crb/classification-rule-definitions.md) ページの定義の&#x200B;*`Variable`*&#x200B;を参照してください。
1. 使用するレポートスイートおよび変数を指定して、「**[!UICONTROL 保存]**」をクリックします。
1. 引き続き、[分類ルールの追加](/help/components/classifications/crb/classification-rule-set.md)をおこないます。
