---
description: 'null'
seo-description: 'null'
seo-title: セグメント
title: セグメント
uuid: 677f6030-5b3e-4dfa- bb79-9f27f3382fb1
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# セグメント {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Segment rail {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

コンポーネントメニューのセグメントレールには、次のアイコンで示されるようにセグメントとセグメントテンプレートが表示されます。

![](assets/segment_icons.png)

[YouTube上のAnalysis Workspaceでのセグメントの使用](https://www.youtube.com/watch?v=QlUCdQDnni4)（6:46）

## Create segments {#section_693CFADA668B4542B982446C2B4CF0F5}

任意の種類のコンポーネント（ディメンション、ディメンション項目、イベント、指標、セグメント、セグメントテンプレート、日付範囲）をパネルの上部にあるセグメントドロップゾーンにドロップすることで、セグメントを即座に作成できます。

コンポーネントの種類はセグメントに自動変換されます。また、「セグメントを追加」ドロップダウンの「+」記号をクリックすることもできます。

次の点に注意してください。

* 次の種類のコンポーネントをセグメントゾーンにドロップすることは&#x200B;**できません**：セグメントを作成できない計算指標およびディメンション／指標。
* Analysis Workspace では、すべてのディメンションおよびイベントに対して、「存在する」ヒットセグメントを作成します。例：「eVar1 が存在するヒット」または「event1 が存在するヒット」
* セグメントドロップゾーンに「未指定」または「なし」がドロップした場合、セグメント化で正しく処理されるように、セグメントは「存在しない」セグメントに自動的に変換されます。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>この方法で作成されたセグメントは、プロジェクトの内部にあります。

次の手順に従うことで、これらのセグメントを公開（グローバル）できます。

1. ドロップゾーンのセグメントの上にマウスポインターを置いて、「i」アイコンをクリックします。
1. In the information panel that displays, click **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Other methods for applying segments {#section_10FF2E309BA84618990EA5B473015894}

フリーフォームプロジェクトにセグメントを適用するには、他にもいくつかの方法があります。

<table id="table_45B3839D70674430AF3AC5AA3134F825"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> アクション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>選択からセグメントを作成 </p> </td> 
   <td colname="col2"> <p>インラインセグメントを作成します。行を選択して、選択範囲を右クリックし、インラインセグメントを作成します。このセグメントは、オープンプロジェクトにのみ適用し、Analytics セグメントとして保存されません。 </p> <p> 
     <ol id="ol_1D1E661387354EBF992CC150915F642E"> 
      <li id="li_B96666FD426F4AEE8EAB61B2C00A07FB">行を選択します。 </li> 
      <li id="li_C2245B3EA81F4FAC88A33647922535AF">選択範囲を右クリックします。 </li> 
      <li id="li_AB4F8988B9A84920ABA06A91094625F6">「<span class="uicontrol">選択からセグメントを作成</span>」をクリックします。 </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> コンポーネント</span>／<span class="uicontrol">新しいセグメント</span> </td> 
   <td colname="col2"> <p><span class="wintitle">セグメントビルダー</span>を表示します。セグメント化について詳しくは、<a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html" format="https" scope="external">セグメントの作成</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="ignoretag"><span class="uicontrol"> 共有</span>／<span class="uicontrol">プロジェクトを共有</span></span>または </p> <p> <span class="ignoretag"><span class="uicontrol">共有</span>／<span class="uicontrol">プロジェクトデータをキュレート</span></span> </p> </td> 
   <td colname="col2"> <p><a href="../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6" format="dita" scope="local"> キュレーションと共有</a>では、プロジェクトに適用するセグメントは、受信者の共有分析で使用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ディメンションとしてセグメントを使用 </p> </td> 
   <td colname="col2"> <p>ビデオ:<a href="https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39" format="https" scope="external">Analysis Workspace でセグメントをディメンションとして使用する</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

