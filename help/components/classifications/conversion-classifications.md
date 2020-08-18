---
description: 分類は値をグループにまとめてグループレベルで報告するために使用します。例えば、すべての有料検索キャンペーンを「ポップミュージック用語」という分類に入れて、インスタンス（クリックスルー）や成功イベントへのコンバージョンなどの指標に関してそのカテゴリの成功を報告します。
subtopic: Classifications
title: コンバージョンの分類
topic: Admin tools
uuid: 4c8726c9-f527-44e1-be01-8c7b3b5c20f0
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 100%

---


# コンバージョンの分類

分類は値をグループにまとめてグループレベルで報告するために使用します。例えば、すべての有料検索キャンペーンを「ポップミュージック用語」という分類に入れて、インスタンス（クリックスルー）や成功イベントへのコンバージョンなどの指標に関してそのカテゴリの成功を報告します。

## コンバージョンの分類 {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

分類は値をグループにまとめてグループレベルで報告するために使用します。例えば、すべての有料検索キャンペーンを「*ポップミュージック用語*」という分類に入れて、インスタンス（クリックスルー）や成功イベントへのコンバージョンなどの指標に関してそのカテゴリの成功を報告します。

コンバージョン分類では、コンバージョン変数を分類できます。分類後は、主要データを使用して生成できるすべてのレポートは、関連付けられたデータプロパティを使用して生成することもできるようになります。

分類を有効にした後、[分類インポーター](/help/components/classifications/importer/c-working-with-saint.md)を使用して、該当する分類に特定の値を割り当てます。

## コンバージョン分類の説明 {#section_4A98DD5F5C314B9DAEE710AEE4EE51D4}

<table id="table_0B72C485467348E2A34BF913441F4AF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle">名前</span> </td> 
   <td colname="col2"> 分類の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">有効な日付（テキストのみ）</span> </td> 
   <td colname="col2"> <p>テキスト分類が campaign 変数の日付範囲かどうかを示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">オプション（テキストのみ）</span> </td> 
   <td colname="col2">その分類に使用できる分類値のリストを作成します。<span class="wintitle">オプション</span>は campaign 変数で使用され、<span class="wintitle">キャンペーンマネージャー</span>の分類でサポートされている値のリストをユーザーに提供します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">数値のタイプ（数値のみ）</span> </td> 
   <td colname="col2">数値分類での数値のタイプを指定します。オプションには [<span class="wintitle">数値</span>]、[<span class="wintitle">パーセント</span>]、[<span class="wintitle">通貨</span>] があります。 </td> 
  </tr> 
 </tbody> 
</table>

## コンバージョン分類の追加 {#task_D535D09E3EAF4CD1A15A6B93C0BB1BB5}

<!-- 

t_classification_conversion.xml

 -->

管理でコンバージョン分類を追加する方法について手順を説明します。

1. **[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;の順にクリックします。
1. レポートスイートを選択します。
1. **[!UICONTROL 設定の編集]**／**[!UICONTROL コンバージョン]**／**[!UICONTROL コンバージョンの分類]**&#x200B;の順にクリックします。
1. **[!UICONTROL 分類タイプの選択]**&#x200B;ドロップダウンリストで分類の追加先の変数を選択します。

   ![ステップ情報](assets/sub_class_create.png)

1. 「**[!UICONTROL 分類の編集]**」アイコンにマウスを移動して、「**[!UICONTROL 分類の追加]**」を選択します。
1. 「**[!UICONTROL タイプの選択]**」フィールドで、変数に追加する分類のタイプを選択します。

   オプションには「**[!UICONTROL テキスト]**」と「**[!UICONTROL 数値]**」があります。分類タイプの詳細については、「[分類について](/help/components/classifications/c-classifications.md)」を参照してください。
1. **[!UICONTROL テキスト分類]**&#x200B;ダイアログボックスで、必要に応じて分類を設定します。

   これらのエレメントについて詳しくは、[コンバージョン分類の説明](/help/components/classifications/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4)を参照してください。

1. **[!UICONTROL ドロップダウンリスト]**&#x200B;ダイアログボックスで、オプションを追加または削除します。

   オプションを追加すると、その分類に使用できる分類値のリストが作成されます。campaign 変数でこのオプションを使用して、キャンペーンマネージャーの分類でサポートされている値のリストをユーザーに提供することができます。このリストは、ほとんどまたはまったく変更がない少数の値を許可する分類ディメンションに使用します。例えば、異なるレベルの顧客忠誠度（シルバー、ゴールド、プラチナ）向けに異なるキャンペーンを実施するとします。その際、ドロップダウンリストを使用すると、3 つのレベルに適した値だけを受け付けることが可能です。異なる値を使用しようとすると、破棄されます。
1. 「**[!UICONTROL 保存]**」をクリックします。

## コンバージョンの分類の削除 {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

不要になった時点でコンバージョンの分類を削除します。

1. スイートのヘッダーで&#x200B;**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**&#x200B;の順にクリックして、Report Suite Manager を開きます。
1. レポートスイートを選択します。
1. **[!UICONTROL 設定の編集]**／**[!UICONTROL コンバージョン]**／**[!UICONTROL コンバージョンの分類]**&#x200B;の順にクリックします。
1. **[!UICONTROL 分類タイプの選択]**&#x200B;ドロップダウンリストで分類を削除する変数を選択します。
1. 「**[!UICONTROL 分類の編集]**」アイコンにマウスを移動して、「**[!UICONTROL 分類の削除]**」を選択します。
1. 分類の削除ダイアログボックスで「**[!UICONTROL 削除]**」をクリックします。
