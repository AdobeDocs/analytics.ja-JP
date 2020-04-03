---
description: Ad Hoc分析の用語とタスクをWorkspaceと比較します。
title: Analysis Workspace と Ad Hoc Analysis の比較
uuid: e4b3e40f-2b08-49a0-95f1-384d85c1640d
translation-type: tm+mt
source-git-commit: 025ac334f9191b6455eea0530a2a21c01199000a

---


# Analysis Workspace と Ad Hoc Analysis の比較

Ad Hoc分析の用語とタスクをWorkspaceと比較します。

分析ワークスペースは、アドホック分析機能の多くをブラウザーワークフローに導入します。 一部の用語と機能は製品間で同じままですが、Propert Workspaceで導入された新しい用語や分析の方法がいくつかあります。

この2つの製品の主な機能と必要システム構成の技術的な比較については、こちらを参照して [くださ](https://marketing.adobe.com/resources/help/en_US/reference/analytics-product-comparison.html)い。

## 主要用語の比較 {#section_6109406B83B043A18E46D38F130B1D2E}

| Ad Hoc Analysis | Analysis Workspace |
|--- |--- |
| プロジェクト | Workspace またはプロジェクト |
| Workspace | パネル |
| レポート | フリーフォームテーブル |
| グラフ | 視覚化 |
| 階層：プロジェクト／Workspace／レポート | 階層：プロジェクト/パネル/テーブル |
| ランク、トレンド、合計のレポートテンプレート | フリーフォームテーブルのビジュアライゼーション |
| フローテンプレート | フロービジュアライゼーション |
| フォールアウト | フォールアウトビジュアライゼーション |

## 主要タスク {#section_F31446F1DFA742D794A30D713E223440}

<table id="table_90D4461F04F34D70844C5E3FBB0BBE44"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> アドホック分析タスク </th> 
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
   <td colname="col2"> <p>セグメントは、セグメントコンポーネントメニューの下で使用でき、Segment Workspace内の3か所に適用できます。分析ワークスペース </p> 
    <ol id="ol_800D81FE2C84459B94B085C51E140330"> 
     <li id="li_F2E050902F9A4831BBA57F466E07DEAE">パネルレ <b>ベル</b>（パネル内の多くのビジュアライゼーションに適用）。 これは、Ad Hoc でセグメントを Workspace に適用する場合に似ています。 </li> 
     <li id="li_2D88E43E0161485C95B08DC3C593EFD9">As <b>rows in a table</b>. これは、Ad Hocの表ビルダーの「行/分類」セクションにセグメントを追加するのと似ています。 </li> 
     <li id="li_102E1A1DAA9247C08FC46C5AB3D78113">表の <b>列として</b>。 これは、表ビルダーの「列」セクション(Ad Hoc分析)にセグメントを追加する場合や、Ad Hoc分析のレポートレベルでセグメントを適用する場合と似ています。 </li> 
    </ol> <p><a href="https://www.youtube.com/watch?v=QlUCdQDnni4"  > ビデオ：Workspace でのセグメントの使用</a> </p> <p><a href="https://www.youtube.com/watch?v=YjaRlJoQqRA"  > ビデオ：パネルへのセグメントの適用</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付範囲と精度の選択 </p> </td> 
   <td colname="col2"> <p>日付範囲と精度は、時間コンポーネントメニューで使用でき、次の3つの方法で使用できます。 </p> 
    <ol id="ol_8B57C8A840694A879B22B809C58E7482"> 
     <li id="li_58FAE6A87B494A5C9007CD35BB101608">日付範囲を列/行に適用し、選択したパネルの日付範囲を上書きできます。 これは、レポートレベルの日付範囲に似ています。 </li> 
     <li id="li_85BB89EFF9C8466A992815BB7804EA37">「適用」は、パネル内のすべてのビジュアライゼーションに日付範囲を適用します。 これは、Ad Hoc Analysis での Workspace の日付範囲に似ています。 </li> 
     <li id="li_BC18564A8FBB48F4A522BCAC60838759">「すべてのパネルに適用」は、Workspaceプロジェクト内のすべてのパネルに日付範囲を適用します。 これは、Ad Hoc分析のプロジェクトの日付範囲と似ています。 </li> 
    </ol> <p><a href="https://www.youtube.com/watch?v=ybmv6EBmhn0"  > ビデオ：Analysis Workspace での日付の操作</a> </p> <p><a href="https://www.youtube.com/watch?v=L4FSrxr3SDA"  > ビデオ：カスタム日付範囲</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>内部（「アドホック」）セグメントの作成 </p> </td> 
   <td colname="col2"> <p>ディメンション項目をパネルの上部にあるセグメントドロップゾーンにドラッグすると、Analysis Workspace で<a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  >内部（「アドホック」）セグメントを即座に作成できます</a>。 </p> <p><a href="https://www.youtube.com/watch?v=NKm7Rj23TtE"  > ビデオ：Analysis Workspace のアドホックセグメント</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>フォールアウトおよびコンバージョンファネルの使用 </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md"  >フォールアウトビジュアライゼーション</a>は、Analysis Workspace のビジュアライゼーションコンポーネントメニューから利用できます。アドホック分析と同様： </p> 
    <ol id="ol_625FF45AED4E403DBEE1A906282E8531"> 
     <li id="li_7B6C5F2682774641B82D2021786AE5C4">フォールアウトは1回の訪問または1回の訪問者にまたがり、「すべての訪問」をオプションで含めることができます。 右クリックメニューを使用して、フォールアウトの傾向をすばやく把握できます。 </li> 
     <li id="li_CFBDDAB8E96A445DB0624640AEB25994">ディメンション項目はOR演算子（グループと同様）で接続でき、イベントはファネルで使用できます。 </li> 
     <li id="li_6638E6A62C744A27B2C066E5F9EC62C0">右クリックメニューからも、次のステップのフォールスルーとフォールアウトをレンダリングできます。 </li> 
    </ol> <p>さらに、分析ワークスペースのフォールアウトでは <a href="/help/analyze/analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md"  ></a> 、ステップ内でディメンションを混在させ、アドホック分析を改善できます。 ステップ内でのディメンションの組み合わせは、AND 演算子で処理します。 </p> <p><a href="https://www.youtube.com/watch?v=VcrfHSyIoj8"  > ビデオ：フォールアウトとファネル</a> </p> <p><a href="https://www.youtube.com/watch?v=EeLV366pQag"  > ビデオ：複数のフォールアウトディメンションの使用</a> </p> <p><a href="https://www.youtube.com/watch?v=H-oT3QZlyZQ"  > ビデオ：フォールアウトでのセグメントの比較</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>フロー（パス）の検証 </p> </td> 
   <td colname="col2"> <p><a href="/help/analyze/analysis-workspace/visualizations/c-flow/flow.md"  >フロービジュアライゼーション</a>は、Analysis Workspace のビジュアライゼーションコンポーネントメニューから利用できます。アドホック分析と同様： </p> 
    <ul id="ul_42D259310823496499F7D1474E1639AF"> 
     <li id="li_5DE6980EF66A49E58B8946A0422BC02C">フローは1回の訪問または1回の訪問者に及びます。 </li> 
     <li id="li_70A692266D32416BA3D70C1F8999F837">主要な統計は、%パスの統計で表示されます。表示 </li> 
    </ul> <p>Additionally, Flow allows for <a href="/help/analyze/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md"  > mixed dimensions</a> and the ability to right-click and create a segment, an improvement over Ad Hoc Analysis. </p> <p>現在、分析ワークスペースのフローは次のこ <b>とはでき</b>ません： </p> 
    <ul id="ul_2696A9DCB86E427DB5267BE2793693FF"> 
     <li id="li_384141A577BB4A94899C3E36714225EE">繰り返しインスタンスをオフにします。 </li> 
     <li id="li_CC451BFB9FFC4C68AE28A7462B339460">ユーザーが成功オプションを選択できるようにイベントします。 </li> 
    </ul> <p><a href="https://www.youtube.com/watch?v=3R1HTM7y_RM"  > ビデオ：フロービジュアライゼーションの概要</a> </p> <p><a href="https://www.youtube.com/watch?v=m1Wa6inC1rQ"  > ビデオ：複数ディメンションのフロー</a> </p> <p><a href="https://www.youtube.com/watch?v=XrJoNQy6RaQ"  > ビデオ：フローからのセグメントの作成</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>無限の分類の実行 </p> </td> 
   <td colname="col2"> <p>分析ワークスペースを使用すると、ブラウザー内の無限のレベルまでドリルダウンできます。 セグメントとディメンションは混在できます。 複数のディメンション項目を複数選択してから、分類ディメンションをドラッグすることで、複数のディメンション項目を一度に分類できます。 </p> <p><a href="https://www.youtube.com/watch?v=3mQ2HN7-lIc"  > ビデオ：分類の強化</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迅速なトレンドデータ </p> </td> 
   <td colname="col2"> <p>データは、レポート行内のグラフアイコンをクリックすると、すばやく視覚化できます。 さらに、これらのクイックビジュアライゼーションはソーステーブルにリンクされ、テーブル内の値を次々にクリックして、グラフが自動的に更新されるのを確認できます。 </p> <p><a href="https://www.youtube.com/watch?v=kzlPjsBVYFQ"  > ビデオ：ディメンションとグラフのライブリンク</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>レポートスイートの選択 </p> </td> 
   <td colname="col2"> <p>アドホック分析と同様に、1つのWorkspaceプロジェクトに対して1つのレポートスイートのみを選択できます。 ただし、複数レポートスイートの処理は計画されています。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attribution IQ </p> </td> 
   <td colname="col2"> <p>Analysis Workspace の <a href="/help/analyze/analysis-workspace/attribution-iq.md"  >Attribution IQ</a> では、新しいタイプの多数のアトリビューションモデルをフリーフォームテーブル、ビジュアライゼーション、計算指標に追加できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>含まれない </p> </td> 
   <td colname="col2"> <p>セグ追加メントの日付範囲。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>含まれない </p> </td> 
   <td colname="col2"> <p>セグメントで「前/後のみ」の順に並べて使用します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

