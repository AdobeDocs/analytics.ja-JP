---
description: Adobe Analytics と Adobe Audience Manager には同様の定義の訪問者指標がありますが、様々な理由で 100％同じではありません。
title: 訪問者数の相違
uuid: c3bbb887-bd02-4c1c-9a2b-64811c0ef56a
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 100%

---


# 訪問者数の相違

Adobe Analytics と Adobe Audience Manager には同様の定義の訪問者指標がありますが、様々な理由で 100％同じではありません。

訪問者の指標は次のとおりです。

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> 指標 </th> 
   <th colname="col3" class="entry"> 定義 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://docs.adobe.com/content/help/ja-JP/audience-manager/user-guide/features/segments/segment-builder-data.html"  > AAM：Total Segment Population</a> </p> </td> 
   <td colname="col3"> <p>ルックバック期間にセグメントのメンバーであったデバイス（Experience Cloud ID）の数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html"  > AAM：Real-Time Segment Population</a> </p> </td> 
   <td colname="col3"> <p>ルックバック期間にセグメントのメンバーであり、プロパティにアクセスしたデバイス（Experience Cloud ID）の数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：個別訪問者 </p> </td> 
   <td colname="col3"> <p>レポート期間にプロパティにアクセスした個別訪問者の数を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：Experience Cloud ID での訪問者 </p> </td> 
   <td colname="col3"> <p>レポート期間にプロパティにアクセスした Experience Cloud ID を持つ個別訪問者の数を表示します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Audience Analytics レポート内で使用される AAM の「Real-time Segment Population」と Analytics の「Experience Cloud ID での訪問者」は、最も似ています。ただし短期間の場合は、いくつかの要因により、若干の相違があります。関係する要因は次のとおりです。

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要因 </th> 
   <th colname="col2" class="entry"> AAM：Real-time Segment Population </th> 
   <th colname="col3" class="entry"> Analytics：Experience Cloud ID での訪問者 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>タイムゾーン </p> </td> 
   <td colname="col2"> <p>UTC（協定世界時） </p> </td> 
   <td colname="col3"> <p>レポートスイートごとに指定します </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムフィルター </p> </td> 
   <td colname="col2"> <p>× </p> </td> 
   <td colname="col3"> <p>あり（IP フィルター、ボットフィルターなど） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>150 セグメントの制限 </p> </td> 
   <td colname="col2"> <p>× </p> </td> 
   <td colname="col3"> <p>あり - Analytics のカウントは、150 セグメントの統合制限によって最大 5％影響を受けることがあります。切り捨てが発生した場合、オーディエンス名ディメンションに「オーディエンスの制限に達しました」と表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Analytics および Audience Manager のデータとセグメントのニュアンスについて詳しくは、[Analytics と Audience Manager のセグメントについて](/help/integrate/c-audience-analytics/aam-analytics-segments.md)を参照してください。
