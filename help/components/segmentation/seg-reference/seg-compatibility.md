---
description: セグメントビルダーで作成されたすべてのセグメントがData Warehouseと互換性がない理由を理解します。 サポートされている関数について説明します。
title: Data Warehouse セグメントの互換性
feature: Segmentation
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 61%

---

# Data Warehouse セグメントの互換性

セグメントビルダーで作成されたすべてのセグメントが[!DNL Data Warehouse]と互換性があるわけではありません。 サポートされる機能を次の表に示します。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace、Reports &amp; Analytics </th> 
   <th> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td > <b>除外コンテナ</b> </td> 
   <td> あらゆるレベルでサポート </td> 
   <td> トップレベルの特殊なケースでのみサポート </td> 
  </tr> 
  <tr> 
   <td> <b> シーケンシャルセグメント </b> </td> 
   <td> 対応 </td> 
   <td> サポートなし </td> 
  </tr> 
  <tr> 
   <td> <b>ANDおよびORは、制限なしで組み合わせることができます</b> </td> 
   <td> 対応 </td> 
   <td> いくつかの制限。 テーブルの下の「メモ」を参照。 </td> 
  </tr> 
  <tr> 
   <td> <b> ネストされたコンテナ </b> </td> 
   <td> 対応 </td> 
   <td> いくつかの制限（例えば、訪問者にヒットを含めることができますが、その逆ではありません） </td> 
  </tr> 
  <tr> 
   <td> <b>ディメンション</b> </td> 
   <td>ディメンションをセグメントビルダーの<span class="uicontrol">定義</span> フィールドにドラッグ&amp;ドロップして、製品の互換性を確認します。 例えば、次のディメンションは、Analysis Workspace、Reports &amp; Analytics でのみサポートされます。 
    <ul> 
     <li>入口サーバー </li> 
     <li>入口カテゴリ </li> 
     <li>エントリ日 </li> 
     <li>すべての検索ページのランク </li> 
    </ul> </td> 
   <td> ディメンションをセグメントビルダーの<span class="uicontrol">定義</span> フィールドにドラッグ&amp;ドロップして、製品の互換性を確認します。 例えば、これらのディメンションはData Warehouseでのみサポートされています。 
    <ul> 
     <li>IP アドレス </li> 
     <li>ページ URL </li> 
     <li>訪問者 ID </li> 
     <li>Experience Cloud の訪問者 ID </li> 
    </ul> <p>次のディメンションは、Data Warehouse セグメントでは使用<b>できません</b>。 </p> 
    <ul> 
     <li>すべての検索ページのランク </li> 
     <li>午前／午後 </li> 
     <li>日付 </li> 
     <li>曜日 </li> 
     <li>年間通算日 </li> 
     <li>エントリ事業部 </li> 
     <li>入口（入口ページを除く、入口で始まるすべてのディメンション） </li> 
     <li>出口（「離脱リンク」および「出口ページ」を除く、「出口」で始まるすべてのディメンション） </li> 
     <li>階層（階層で始まるすべてのディメンション） </li> 
     <li>ヒットの深さ </li> 
     <li>ヒットタイプ </li> 
     <li>時間日 </li> 
     <li>月 </li> 
     <li>エラーページ（404） </li> 
     <li>有料検索 </li> 
     <li>四半期 </li> 
     <li>再来訪頻度 </li> 
     <li>単一ページ訪問数 </li> 
     <li>イベント前の時間 </li> 
     <li>ページでの滞在時間 - グループ </li> 
     <li>訪問別滞在時間 - グループ </li> 
     <li>トラッキングオプトアウト理由 </li> 
     <li>米国の州 </li> 
     <li>平日／週末 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <b>セグメントの積み重ね</b> </td> 
   <td> 対応 </td> 
   <td> サポート </td> 
  </tr>
  <tr>
    <td><b>「次のいずれかと等しい」および「次のいずれとも等しくない」演算子</b></td>
    <td>サポート</td>
    <td>サポートなし</td>
  </tr>
 </tbody> 
</table>

*メモ：Data Warehouse では、`AND/OR` を使用する場合に、`exclusion` または `without` コンテナを使用するすべてのケースをサポートするわけではありません。 このような組み合わせを使用する場合、`A AND NOT B` として書き直すことのできるセグメントのみが（または&#x200B;**この特性を含み****この特性を除外する**）Data Warehouse でサポートされます。*
