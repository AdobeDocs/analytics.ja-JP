---
description: 仮想レポートスイートの作成を始める前に、以下に注意してください。
keywords: 仮想レポートスイート
seo-description: 仮想レポートスイートの作成を始める前に、以下に注意してください。
seo-title: 仮想レポートスイートの作成
solution: Analytics
title: 仮想レポートスイートの作成
topic: Reports and Analytics
uuid: 022a6656-808e-4c92- b7ec-4d2a42e84fa8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 仮想レポートスイートの作成

仮想レポートスイートの作成を始める前に、以下に注意してください。

* 仮想レポートスイートマネージャーは管理者ユーザー以外には表示されません。
* 仮想レポートスイートは共有できません。「共有」するには、グループや権限を使用します。
* 仮想レポートスイートマネージャーには、自分が所有する仮想レポートスイートのみが表示されます。他のユーザーの仮想レポートスイートを表示するには、「すべて表示」をクリックする必要があります。

1. **[!UICONTROL コンポーネント]** / **[!UICONTROL 仮想レポートスイートに移動]**&#x200B;します。
1. **[!UICONTROL 「追加+]**」をクリックします。

   ![](assets/new_vrs.png)

1. 以下のフィールドを設定します。

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> <p>仮想レポートスイートの名前は親レポートスイートから継承されません。別の名前を指定する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 説明 </td> 
   <td colname="col2"> <p>ビジネスユーザーにとってわかりやすい説明を追加します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> タグ </td> 
   <td colname="col2"> <p>タグを追加してレポートスイートを整理できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> グループ </td> 
   <td colname="col2"> <p>この VRS へのアクセスを許可する権限グループを選択します（グループ権限は、<span class="ignoretag"><span class="uicontrol">管理者</span>／<span class="uicontrol">ユーザー管理</span>／<span class="uicontrol">グループ</span></span>からも管理できます）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 親レポートスイート </td> 
   <td colname="col2"> <p>レポートスイートはこの仮想レポートスイートから次の設定を継承します。ほとんどのサービスレベルと機能（eVar 設定、処理ルール、分類など）を継承します。VRS の継承設定を変更するには、親レポートスイートを編集する必要があります（<span class="ignoretag"><span class="uicontrol">管理者</span>／<span class="uicontrol">レポートスイート</span></span>）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> タイムゾーン </td> 
   <td colname="col2"> <p>タイムゾーンの選択はオプションです。 </p> <p>選択したタイムゾーンは VRS と共に保存されます。タイムゾーンを選択していない場合は、親レポートスイートのタイムゾーンが使用されます。 </p> <p>VRS の編集時には、その VRS と共に保存されたタイムゾーンがドロップダウンセレクターに表示されます。タイムゾーンのサポートが追加される前に作成された VRS の場合は、その親レポートスイートのタイムゾーンがドロップダウンセレクターに表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セグメント </td> 
   <td colname="col2"> <p>セグメントは、1 つだけ追加することも、<a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_stack.html" format="https" scope="external">積み重ねることもできます</a>。 </p> <p> <p>注意：2 つのセグメントを積み重ねると、それらのセグメントが AND ステートメントで結合されます。これを OR ステートメントに変更することはできません。 </p> </p> <p>仮想レポートスイートで現在使用中のセグメントを削除または編集しようとすると、警告が表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

