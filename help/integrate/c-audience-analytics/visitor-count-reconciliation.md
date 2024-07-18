---
description: Adobe Analytics と Adobe Audience Manager には同様の定義の訪問者指標がありますが、様々な理由で 100％同じではありません。
title: 訪問者数の相違
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 85%

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
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=ja"  > Adobe Audience Manager：合計セグメント母集団 </a> </p> </td> 
   <td colname="col3"> <p>ルックバック期間にセグメントのメンバーであったデバイス（Experience Cloud ID）の数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=ja"  > Adobe Audience Manager：リアルタイムセグメント母集団 </a> </p> </td> 
   <td colname="col3"> <p>ルックバック期間にセグメントのメンバーであり、プロパティにアクセスしたデバイス（Experience Cloud ID）の数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：ユニーク訪問者 </p> </td> 
   <td colname="col3"> <p>レポート期間にプロパティにアクセスしたユニーク訪問者の数を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics：Experience Cloud ID での訪問者 </p> </td> 
   <td colname="col3"> <p>レポート期間にプロパティにアクセスした Experience Cloud ID を持つユニーク訪問者の数を表示します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Adobe Audience Managerのリアルタイムセグメント母集団と、Audience Analyticsレポート内で使用されるExperience CloudID を持つ Analytics 訪問者は、最も似ています。 ただし短期間の場合は、いくつかの要因により、若干の相違があります。関係する要因は次のとおりです。

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要因 </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager：リアルタイムセグメント母集団 </th> 
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
