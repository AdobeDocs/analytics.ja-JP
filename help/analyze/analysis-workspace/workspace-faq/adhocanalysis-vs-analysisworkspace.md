---
description: Ad Hoc Analysis の用語およびタスクを Analysis Workspace と比較します。
title: Analysis Workspace と Ad Hoc Analysis の比較
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 85%

---


# Analysis Workspace と Ad Hoc Analysis の比較

>[!IMPORTANT]
>
>Adobeは2021年3月1日にAd Hoc Analysisを廃止に移す。 [詳細情報](https://adobe.ly/discoverworkspace)

Ad Hoc Analysis の用語およびタスクを Analysis Workspace と比較します。

Analysis Workspace では、Ad Hoc Analysis の機能の多くがブラウザーワークフローに取り入れられています。両製品で同じままの用語と機能もありますが、Analysis Workspace ではいくつかの新しい用語と分析アプローチが導入されています。

両製品の主要機能と必要システム構成の技術的な比較については、[こちら](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-overview/analytics-product-comparison.html)を参照してください。

## 主な用語の比較 {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| プロジェクト | Workspace またはプロジェクト |
| Workspace | パネル |
| レポート | フリーフォームテーブル |
| グラフ | ビジュアライゼーション |
| 階層：プロジェクト／Workspace／レポート | 階層：プロジェクト／パネル／テーブル |
| ランク、トレンド、合計レポートテンプレート | フリーフォームテーブルビジュアライゼーション |
| フローテンプレート | フロービジュアライゼーション |
| フォールアウト | フォールアウトビジュアライゼーション |

## 主なタスクの比較 {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ad Hoc Analysisタスク </th> 
   <th colname="col2" class="entry"> Analysis Workspace のタスク </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>指標列へのディメンションとセグメントの追加 </p> </td> 
   <td colname="col2"> <p>ディメンションの項目またはセグメントを列のヘッダーとして取り込んで、指標の比較ビューを簡単に作成できます。<a href="https://www.youtube.com/watch?v=P9W0hhIHhCs"  > ビデオ：ディメンションの操作</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>セグメントの適用 </p> </td> 
   <td colname="col2"> <p>セグメントは、セグメントコンポーネントメニューにあり、Analysis Workspace の次の 3 つの場所で適用できます。 </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE"><b>パネルレベル</b>。パネル内の様々なビジュアライゼーションに適用されます。これは、Ad Hoc でセグメントを Workspace に適用する場合に似ています。 </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9"><b>テーブルの行</b>として。これは、Ad Hoc で表ビルダーの「行 / 分類」セクションにセグメントを追加する場合に似ています。 </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113"><b>テーブルの列</b>として。これは、Ad Hoc Analysis で表ビルダーの「列」セクションにセグメントを追加する場合、または Ad Hoc Analysis でセグメントをレポートレベルで適用する場合に似ています。 </li> 
    </ol> <p><a href="https://www.youtube.com/watch?v=QlUCdQDnni4"  > ビデオ：Workspace でのセグメントの使用</a> </p> <p><a href="https://www.youtube.com/watch?v=YjaRlJoQqRA"  > ビデオ：パネルへのセグメントの適用</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>一時的な（「アドホック」）セグメントの作成 </p> </td> 
   <td colname="col2"> <p>You can <a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > create instant, temporary ("ad-hoc") segments</a> in Analysis Workspace by dragging dimension items into the segment drop zone at the top of the panel. さらに、パネルのドロップゾーンにドロップダウンフィルターを追加して、一時セグメントを多数作成し、プロジェクトの操作を制御できます。 </p> <p><a href="https://www.youtube.com/watch?v=NKm7Rj23TtE"  > ビデオ：Analysis Workspace のアドホックセグメント</a> </p> <p><a href="https://www.youtube.com/watch?v=vpJywtsFVPI"  > ビデオ：Analysis Workspaceのドロップダウンフィルター</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付範囲および精度の選択 </p> </td> 
   <td colname="col2"> <p>日付範囲および精度は、日時コンポーネントメニューにあり、次の 3 つの方法で使用できます。 </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">日付範囲を列や行に適用して、選択されているパネルの日付範囲を上書きできます。これは、レポートレベルの日付範囲に似ています。 </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">「適用」では、パネル内のすべてのビジュアライゼーションに日付範囲が適用されます。これは、Ad Hoc Analysis での Workspace の日付範囲に似ています。 </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">「すべてのパネルに適用」では、Workspace プロジェクト内のすべてのパネルに日付範囲が適用されます。これは、Ad Hoc Analysis でのプロジェクトの日付範囲に似ています。 </li> 
    </ol> <p><a href="https://www.youtube.com/watch?v=ybmv6EBmhn0"  > ビデオ：Analysis Workspace での日付の操作</a> </p> <p><a href="https://www.youtube.com/watch?v=L4FSrxr3SDA"  > ビデオ：カスタム日付範囲</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>フォールアウトおよびコンバージョンファネルの使用 </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  >フォールアウトビジュアライゼーション</a>は、Analysis Workspace のビジュアライゼーションコンポーネントメニューから利用できます。Ad Hoc Analysis に似ています。 </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">フォールアウトは、訪問または訪問者にまたがることができ、オプションで「すべての訪問」を含めることができます。フォールアウトは、右クリックメニューですぐに表示できます。 </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">ディメンション項目同士を OR 演算子で結合でき（グループ化に似ています）、イベントをファネル内で使用できます。 </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">フォールスルーとフォールアウトの次のステップは右クリックメニューでも表示できます。 </li> 
    </ol> <p>また、Analysis Workspace のフォールアウトでは、Ad Hoc Analysis よりも改善された点として、ステップ内で<a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  >ディメンションを組み合わせる</a>ことができます。ステップ内でのディメンションの組み合わせは、AND 演算子で処理します。 </p> <p><a href="https://www.youtube.com/watch?v=VcrfHSyIoj8"  > ビデオ：フォールアウトとファネル</a> </p> <p><a href="https://www.youtube.com/watch?v=EeLV366pQag"  > ビデオ：複数のフォールアウトディメンションの使用</a> </p> <p><a href="https://www.youtube.com/watch?v=H-oT3QZlyZQ"  > ビデオ：フォールアウトでのセグメントの比較</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>フロー（パス）の検証 </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  >フロービジュアライゼーション</a>は、Analysis Workspace のビジュアライゼーションコンポーネントメニューから利用できます。Ad Hoc Analysis に似ています。 </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">フローは訪問または訪問者にまたがることができます。 </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">主な統計は、％パス表示で示されます。 </li> 
    </ul> <p>また、フローでは、Ad Hoc Analysis よりも改善された点として、<a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  >混合したディメンション</a>と右クリックでセグメントを作成できることは、Ad Hoc Analysis における改善点です。 </p> <p>現在、Analysis Workspaceのフローでは、成功イベントの選択をユーザーに <b>許可できません</b> 。 </li> 
    </ul> <p><a href="https://www.youtube.com/watch?v=3R1HTM7y_RM"  > ビデオ：フロービジュアライゼーションの概要</a> </p> <p><a href="https://www.youtube.com/watch?v=m1Wa6inC1rQ"  > ビデオ：複数ディメンションのフロー</a> </p> <p><a href="https://www.youtube.com/watch?v=XrJoNQy6RaQ"  > ビデオ：フローからのセグメントの作成</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>無制限の分類の実行 </p> </td> 
   <td colname="col2"> <p>Analysis Workspace では、ブラウザー内でレベルの制限なくドリルダウンできます。セグメントとディメンションを組み合わせることができます。複数のディメンションアイテムを複数選択してから分類ディメンションにドラッグすることで、即座に分類できます。 </p> <p><a href="https://www.youtube.com/watch?v=3mQ2HN7-lIc"  > ビデオ：分類の強化</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データのトレンドのすばやい表示 </p> </td> 
   <td colname="col2"> <p>レポート行でグラフのアイコンをクリックすることで、データをすばやく視覚化できます。また、これらのビジュアライゼーションはソーステーブルとリンクされるので、テーブルで別の値をクリックするとグラフが自動的に更新されます。 </p> <p><a href="https://www.youtube.com/watch?v=kzlPjsBVYFQ"  > ビデオ：ディメンションとグラフのライブリンク</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートスイートの選択 </p> </td> 
   <td colname="col2"> <p>複数のレポートスイートをAnalysis Workspaceの1つのプロジェクトに追加できます。  </p> <p><a href="https://www.youtube.com/watch?v=kRPTBDNLJKk"  > ビデオ：Workspaceの複数のレポートスイート</a> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p>Analysis Workspace の <a href="/help/analyze/analysis-workspace/attribution/overview.md"  >Attribution IQ</a> では、新しいタイプの多数のアトリビューションモデルをフリーフォームテーブル、ビジュアライゼーション、計算指標に追加できます。これには、10以上のルールベースモデルとアルゴリズムモデルが含まれます。 </p>  <p><a href="https://www.youtube.com/watch?v=aYbGcQvAN1E"  > ビデオ：フリーフォームテーブルのAttribution IQ</a> </p> </td> 
  </tr>  
 </tbody> 
</table>

