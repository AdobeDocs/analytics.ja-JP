---
description: ターゲットでは、Web サイトのパフォーマンスを測定し、目標に対する達成度をトラッキングできます。例えば、ある地理的な地域からの訪問者数、注文ごとの売上高、または特定のリファラーからのヒット数などを向上することを目標にしているとします。
seo-description: ターゲットでは、Web サイトのパフォーマンスを測定し、目標に対する達成度をトラッキングできます。例えば、ある地理的な地域からの訪問者数、注文ごとの売上高、または特定のリファラーからのヒット数などを向上することを目標にしているとします。
seo-title: ターゲット
solution: Analytics
title: ターゲット
topic: Reports and Analytics
uuid: bfe29dc8-8da8-4107-8bb1-4a7494f12bc9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ターゲット

ターゲットでは、Web サイトのパフォーマンスを測定し、目標に対する達成度をトラッキングできます。例えば、ある地理的な地域からの訪問者数、注文ごとの売上高、または特定のリファラーからのヒット数などを向上することを目標にしているとします。

## ターゲット {#concept_6516E81923E845198B7FC5D8F81DC35C}

ターゲットでは、Web サイトのパフォーマンスを測定し、目標に対する達成度をトラッキングできます。例えば、ある地理的な地域からの訪問者数、注文ごとの売上高、または特定のリファラーからのヒット数などを向上することを目標にしているとします。

ターゲットを作成する場合は、測定する属性指標や eVar を選択するか、選択した指標を使ってサイト全体を測定します。

例えば、Web サイトへの個別訪問者数を測定し、ターゲットとして使用するとします。この場合、Web サイト全体を選択する必要があります。一方、シカゴから Web サイトに来訪した個別訪問者数をターゲットにする場合は、Web サイト全体ではなく、該当する eVar のみを指定します。

## ターゲットフィールドの説明 {#section_44DFFB4A7AC54D65BC2345411686B2AD}

**[!UICONTROL Analytics]** / **[!UICONTROL コンポーネント]** / **[!UICONTROL ターゲット]**

[!UICONTROL ターゲットの追加/編集]ページのフィールドとオプションについて説明します。

<table id="table_E08728BECC204DF59F0AC99957A68CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ターゲット名 </td> 
   <td colname="col2"><span class="wintitle">ターゲットマネージャー</span>ページに表示するターゲット名を指定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 適用先 </td> 
   <td colname="col2"> ターゲットの適用先は、サイト全体または選択した属性または eVar のいずれかを選択できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 項目の選択 </td> 
   <td colname="col2"> <p>関連アイテムに対してアドバンス検索を実行できるよう、選択した属性または eVar の選択フォームを表示します。‎例えば、「<span class="uicontrol">国</span>」という eVar を選択すると、アイテムリストに選択可能な国名が表示されます。同様に、「<span class="uicontrol">製品</span>」という eVar を選択すると、アイテムリストに選択可能な製品が表示されます。このメニューには、カスタムインサイト変数も表示されます。訪問者の年齢範囲を測定するカスタムインサイト変数を設定している場合は、アイテムリストに「18 ～ 24」、「25 ～ 35」などの年齢範囲が表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 指標 </td> 
   <td colname="col2">ターゲットを指標に適用できます。このメニューには、指定の eVar に適用される指標のみが表示されます。例えば、「<span class="uicontrol">製品</span>」を eVar として選択すると、「<span class="uicontrol">ページ移動</span>」などの指標は適用できません。「<span class="uicontrol">ページ移動</span>」指標は、Web ページ数 eVar に適用できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ピリオド </td> 
   <td colname="col2"> <p>ターゲットの<span class="uicontrol">日付範囲</span>設定および<span class="uicontrol">精度</span>設定を定義できます。指定した期間によっては、一部の精度オプションを使用できない場合があります。指標の値を入力する場合は、それぞれの精度の設定に対する値を入力してください。例えば、期間を「2 月」、精度を「週」に設定した場合、2 月の各週ごとの値を入力します。ターゲットレポートは、それぞれの精度の設定ごとに表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 値 </td> 
   <td colname="col2"> <p>期間および選択した指標に対するターゲット値を指定できます。この値は、達成しようとしているターゲット値です。例えば、売上高に基づいたターゲットで、ある月の売上高目標を $10,000 としている場合は、その月の値フィールドに「10000」と入力します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## ターゲットの追加 {#task_94915391E26E4F808F2538AA92BC7E71}

ターゲットを追加する手順を説明します。

<!-- 

t_add_a_target.xml

 -->

1. **[!UICONTROL Analytics]** / **[!UICONTROL コンポーネント]** / **[!UICONTROL ターゲット]**&#x200B;をクリックします。
1. [!UICONTROL ターゲットマネージャ] ページで、「新規追加」をクリック ****&#x200B;します。
1. [ターゲットフィールドの説明](../../analyze/reports-analytics/targets.md#section_44DFFB4A7AC54D65BC2345411686B2AD)で説明したオプションを構成します。
1. Click **[!UICONTROL OK]**.

## ターゲットの編集 {#task_946C558D2ECC4922ABD4A5A6183A095A}

1. **[!UICONTROL Analytics]** / **[!UICONTROL コンポーネント]** / **[!UICONTROL ターゲット]**&#x200B;をクリックします。
1.  「**管理**」列で、「**[!UICONTROL 編集]」アイコンをクリックします。**
1. [ターゲットフィールドの説明](../../analyze/reports-analytics/targets.md#section_44DFFB4A7AC54D65BC2345411686B2AD)で説明したオプションを構成します。
1. Click **[!UICONTROL OK]**.
