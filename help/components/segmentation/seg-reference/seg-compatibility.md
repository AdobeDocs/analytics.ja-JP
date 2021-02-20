---
description: セグメントビルダーで作成するすべてのセグメントが Data Warehouse と互換性があるとは限りません。サポートされる機能を次の表に示します。
title: Data Warehouse セグメントの互換性
topic: Segments
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 100%

---


# Data Warehouse セグメントの互換性

セグメントビルダーで作成するすべてのセグメントが [!DNL Data Warehouse] と互換性があるとは限りません。サポートされる機能を次の表に示します。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis </th> 
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
   <td> <b>順次セグメント</b> </td> 
   <td> サポート </td> 
   <td> サポートなし </td> 
  </tr> 
  <tr> 
   <td> <b>AND と OR の無制限の結合</b> </td> 
   <td> サポート </td> 
   <td> 一部制限あり。テーブルの下の「注意」を参照。 </td> 
  </tr> 
  <tr> 
   <td> <b>コンテナのネスト</b> </td> 
   <td> サポート </td> 
   <td> 一部制限（スコープを狭くする必要があります。例えば、訪問者はヒットを含めることができるが、その逆はできません）。 </td> 
  </tr> 
  <tr> 
   <td> <b>ディメンション</b> </td> 
   <td>セグメントビルダーの<span class="uicontrol">定義</span>フィールドにディメンションをドラッグ＆ドロップして、プロトコルの互換性を調べます。例えば、次のディメンションは、Analysis Workspace、Reports &amp; Analytics および Ad Hoc Analysis でのみサポートされます。 
    <ul> 
     <li>入口サーバー </li> 
     <li>入口カテゴリ </li> 
     <li>エントリ日 </li> 
     <li>すべての検索ページのランク </li> 
    </ul> </td> 
   <td> セグメントビルダーの<span class="uicontrol">定義</span>フィールドにディメンションをドラッグ＆ドロップして、プロトコルの互換性を調べます。例えば、次のディメンションは、Data Warehouse でのみサポートされます。 
    <ul> 
     <li>IP アドレス </li> 
     <li>ページ URL </li> 
     <li>訪問者 ID </li> 
     <li>Experience Cloud 訪問者 ID </li> 
    </ul> <p>次のディメンションは、Data Warehouse セグメントでは使用<b>できません</b>。 </p> 
    <ul> 
     <li>すべての検索ページのランク </li> 
     <li>午前／午後 </li> 
     <li>日付 </li> 
     <li>曜日 </li> 
     <li>年間通算日 </li> 
     <li>入口ビジネスユニット </li> 
     <li>入口（「入口ページ」を除く、「入口」で始まるすべてのディメンション） </li> 
     <li>出口（「出口リンク」および「出口ページ」を除く、「出口」で始まるすべてのディメンション） </li> 
     <li>階層（「階層」で始まるすべてのディメンション） </li> 
     <li>ヒットの深さ </li> 
     <li>ヒットタイプ </li> 
     <li>時間 日 </li> 
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
   <td> サポート </td> 
   <td> サポート </td> 
  </tr>
  <tr>
    <td><b>「次のいずれかと等しい」および「次のいずれとも等しくない」演算子</b></td>
    <td>サポート</td>
    <td>サポートなし</td>
  </tr>
 </tbody> 
</table>

*注意：Data Warehouse では、`AND/OR` を使用する場合に、`exclusion` または `without` コンテナを使用するすべてのケースをサポートするわけではありません。このような組み合わせを使用する場合、`A AND NOT B` として書き直すことのできるセグメントのみが（または&#x200B;**この特性を含み****この特性を除外する**）Data Warehouse でサポートされます。*
