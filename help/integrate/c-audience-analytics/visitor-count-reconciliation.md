---
description: Adobe Analytics と Adobe Audience Manager には同様の定義の訪問者指標がありますが、様々な理由で 100％同じではありません。
title: 訪問者数の相違
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
TQID: https://experienceleague.adobe.com/ksfYYDZ6G9vH7WEZVh-JsN93Rl-jsZTe9-CQADSwnfI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 44%

---

# 訪問者数の相違

Adobe Analytics と Adobe Audience Manager には同様の定義の訪問者指標がありますが、様々な理由で 100％同じではありません。

訪問者指標は次のとおりです。

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> 指標 </th> 
   <th colname="col3" class="entry"> 定義 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=ja"  > Adobe Audience Manager：合計セグメント数</a> </p> </td> 
   <td colname="col3"> <p>ルックバック期間にセグメントのメンバーであったデバイス（Experience Cloud ID）の数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=ja"  > Adobe Audience Manager: リアルタイム セグメントの母集団</a> </p> </td> 
   <td colname="col3"> <p>ルックバック期間中にセグメントのメンバーであり、プロパティに到達したデバイス（Experience Cloud ID）の数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>分析：ユニーク訪問者 </p> </td> 
   <td colname="col3"> <p>レポート ウィンドウでプロパティに到達したユニーク訪問者の数を表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics:Experience Cloud IDを持つ訪問者 </p> </td> 
   <td colname="col3"> <p>レポート ウィンドウでプロパティに到達したExperience Cloud IDを持つ一意の訪問者の数を表示します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Adobe Audience Manager Audience Analytics レポート内で使用されるExperience Cloud IDを持つReal-time Segment PopulationとAnalytics Visitorsは、最も類似しています。 しかしながら、短期的に見ると、いくつかの要因によって、それらの間に若干の相違が生じるであろう。 その要因は、次のとおりです。

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要因 </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager：リアルタイムのセグメント化 </th> 
   <th colname="col3" class="entry"> Analytics:Experience Cloud IDを持つ訪問者 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>タイムゾーン </p> </td> 
   <td colname="col2"> <p>UTC （協定世界時） </p> </td> 
   <td colname="col3"> <p>レポートスイートごとに指定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>カスタムフィルター </p> </td> 
   <td colname="col2"> <p>いいえ </p> </td> 
   <td colname="col3"> <p>はい（例：IP フィルター、ボットフィルター） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>150 セグメントの制限 </p> </td> 
   <td colname="col2"> <p>いいえ </p> </td> 
   <td colname="col3"> <p>はい – Analyticsのカウントは、150 セグメントの統合制限によって最大5%の影響を受ける可能性があります。 切り捨てが発生した場合、オーディエンス名ディメンションに「オーディエンスの制限に達しました」と表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Analytics および Audience Manager のデータとセグメントのニュアンスについて詳しくは、[Analytics と Audience Manager のセグメントについて](/help/integrate/c-audience-analytics/aam-analytics-segments.md)を参照してください。
