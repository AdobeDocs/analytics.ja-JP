---
description: 検索方法ページでは、様々な検索方法レポートがサイト上のコンバージョン成功イベントに対するクレジットを受け取る方法を特定します。 例えば、検索エンジンが購入したサイトの訪問者を参照する場合、「検索方法」では、検索エンジンが紹介に対するクレジットを受け取る方法を指定します。
title: 検索方法
feature: Admin Tools
role: Admin
exl-id: 58c4510c-2343-4b0a-9c09-5583f6d4250f
TQID: https://experienceleague.adobe.com/eIZhSAm5tZsV4bY3Bznamfq87nhWd82ZwL-M4OIkFSM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 48%

---

# 検索方法

検索方法ページでは、様々な検索方法レポートがサイト上のコンバージョン成功イベントに対するクレジットを受け取る方法を特定します。 例えば、検索エンジンが購入したサイトの訪問者を参照する場合、「検索方法」では、検索エンジンが紹介に対するクレジットを受け取る方法を指定します。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** > **[!UICONTROL 設定の編集]** > **[!UICONTROL コンバージョン]** > **[!UICONTROL 検索方法]**

## 検索方法の説明 {#section_8B6278DB75224EAB9F49D89A86274E8A}

<table id="table_8ABC1C9BD63F419082E4C4C69E401526"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> 修正する検索方法 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配分 </td> 
   <td colname="col2"> 紹介に対するクレジットを適用する方法を指定します。 サポートされる配分オプションは次のとおりです。 <p> <span class="uicontrol">最新（最後）：</span>最後のリファラーに全クレジットを与えます。 </p> <p> <span class="uicontrol">元の値：</span>最初のリファラーに全クレジットを与えます。 </p> <p> <span class="uicontrol">線形：</span>すべてのリファラー間で等しく配分されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 有効期限 </td> 
   <td colname="col2"> 
    <ul id="ul_95EB224CAD164E9997B148E08AFA5F9B"> 
     <li id="li_C240460C21E14AA498D2EA62B9354710"> <span class="uicontrol">訪問：</span>無操作状態が指定時間（通常 30 分間）続いた後。 </li> 
     <li id="li_A3AE5438919E44B68DF99BEEA60C44EE"> <span class="uicontrol">ページ表示：</span>サイトのいずれかのページが開き次第。 </li> 
     <li id="li_D5E20FEF313E4C5B99E7097CA175761A"> <span class="uicontrol">分：</span>無操作状態が 1 分間続いた後。 </li> 
     <li id="li_7315AA3EDDBB47A2BEA3C173881378A1"> <span class="uicontrol">購入：</span>購入時。 </li> 
     <li id="li_C0CF07581654472C9C9EC944E6F18164"> <span class="uicontrol">製品表示：</span>訪問者が商品の web ページを閲覧したとき。 </li> 
     <li id="li_A1B04065150B407491D2EC78EC0DBDF5"> <span class="uicontrol">買い物かご：</span>訪問者が新しい買い物かごを開いたとき。 </li> 
     <li id="li_2AA50C6B9CB14500B67909CDF2AA700C"> <span class="uicontrol">買い物かごのチェックアウト：</span>訪問者が買い物かごをチェックアウトしたとき。 </li> 
     <li id="li_F58CE6FB8DCE4BE4927FFCB35A6D8E31"> <span class="uicontrol">買い物かごへの追加：</span> 訪問者が買い物かごに商品を追加したとき。 </li> 
     <li id="li_AD7C846F46604FC48E0919ACB7515E14"> <span class="uicontrol">買い物かごから削除：</span>訪問者が買い物かごから商品を削除したとき。 </li> 
     <li id="li_EB66E0563F564C9F985BE922DABD0A56"> <span class="uicontrol">買い物かご表示：</span>訪問者が買い物かごの内容を表示したとき。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>すべての検索方法は、その訪問が終了すると有効期限が切れます。 別のイベント（買い物かごのチェックアウトなど）の後に有効期限を切ることを選択した場合、検索方法は、訪問中に買い物かごのチェックアウトが発生すると期限切れになります。 訪問中にカートのチェックアウトが発生しない場合でも、検索方法は訪問が終了したときに期限切れになります。
