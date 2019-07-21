---
description: サイトの訪問者が最もアクセスしたサイトの領域を表示します。サイトセクションには、ユーザー定義可能な、カテゴリに類似した製品グループを含めることができます。例えば、カメラのページグループ、コンピューターのページグループなどが考えられます。コンバージョンサイトセクションレポートのデータは、トラフィックグループのサイトセクションレポートからインポートされ、トラッキングコードの channel 変数から情報を取得します。このレポートを使用すると、サイトの統計に最も大きな影響を与えるサイトセクションの項目を特定できます。
seo-description: サイトの訪問者が最もアクセスしたサイトの領域を表示します。サイトセクションには、ユーザー定義可能な、カテゴリに類似した製品グループを含めることができます。例えば、カメラのページグループ、コンピューターのページグループなどが考えられます。コンバージョンサイトセクションレポートのデータは、トラフィックグループのサイトセクションレポートからインポートされ、トラッキングコードの channel 変数から情報を取得します。このレポートを使用すると、サイトの統計に最も大きな影響を与えるサイトセクションの項目を特定できます。
seo-title: サイトセクション
solution: Analytics
title: サイトセクション
topic: レポート
uuid: 6839c566- f88f-4979-9cf5-52a77c0b0416
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# サイトセクション

サイトの訪問者が最もアクセスしたサイトの領域を表示します。サイトセクションには、ユーザー定義可能な、カテゴリに類似した製品グループを含めることができます。例えば、カメラのページグループ、コンピューターのページグループなどが考えられます。コンバージョンサイトセクションレポートのデータは、トラフィックグループのサイトセクションレポートからインポートされ、トラッキングコードの channel 変数から情報を取得します。このレポートを使用すると、サイトの統計に最も大きな影響を与えるサイトセクションの項目を特定できます。

* このレポートは、Web サイトで実装された [s.channel](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_channel) 変数からデータを直接参照します。
* このレポートは、トレンドおよびランクの両方のフォーマットで表示できます。
* このレポートでは、検索フィルターを使用して特定の行項目を見つけることができます。
* 分類をこのレポートで使用すると、行項目の名前変更や統合ができます。
* 相関関係は、管理ツールで他のトラフィック変数を使用して作成できます。
* このレポートでは以下の指標を利用できます。

   * **ページビュー数**：[pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_pagename) 変数または URL が（デフォルト指標として）定義された回数

   * **すべてのパス指標**：訪問回数、平均ページ深度、ページでの平均滞在時間、リロード回数、および単一アクセス数
   * 組織とレポートスイートの設定に応じて、日別、週別、月別、および四半期別訪問者数をこのレポートで有効化できます。
   * **e コマースのすべての標準的な指標**：売上高、注文件数、数量、買い物かご数、買い物かごの表示回数、チェックアウト数、買い物かごへの追加数、および買い物かごからの削除数
   * **すべてのカスタムイベント**：イベント 1 ～ 80（H22 コード以上では、さらにイベント 80 ～ 100）

[!UICONTROL サイトセクションレポート]では、すべてのコンバージョンイベントで最後の配分が使用されます。コンバージョンは、実装内で成功イベントを含まないページ間で分割されて表示されます。これは、線形配分を使用する[ページレポート](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5)とは異なります。

**製品固有の情報**

<table id="table_525FDF95C8ED4BF2A1E25BE2DA971EFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> インターフェイス </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics </td> 
   <td colname="col2"> <p> <span class="uicontrol"> サイトコンテンツ</span>／<span class="uicontrol">サイトセクション</span> </p> <p>相関関係に加え、このレポートでは以下の分類を利用できます。 </p> 
    <ul id="ul_9CD009D89B134C53807332E3C88D3C44"> 
     <li id="li_566417EB074D425C9A1F4FB28AA7FAB4"> 
      <ul id="ul_3795C7AAE6DA4B7E96FCDC7F3211DFBB"> 
       <li id="li_50B295E961724CFB83D222DE9B4C7FF2">このレポートに基づく分類レポート </li> 
       <li id="li_697682892D8841BC8120BEC0E1AE9753"> <span class="wintitle"> トラッキングコードレポート</span> </li> 
       <li id="li_F6D893FCBA7A4B3EB04715833CA41022"> <span class="wintitle"> 製品</span>および<span class="wintitle">カテゴリ</span>レポート </li> 
       <li id="li_9F379E61DB4F4753AE1FFFC8F9C17347"> <span class="wintitle"> 顧客忠誠度レポート</span> </li> 
       <li id="li_64A6A06F9265410ABB425DA4AF50C440">完全に下位副関連付けされたコンバージョン変数 </li> 
       <li id="li_907DDFCC35AB48EEA5B169B4A2598FB1"> <span class="wintitle"> マーケティングチャネルのファーストタッチとラストタッチ</span> </li> 
       <li id="li_B08A0DCB40154152AF1033B7629A5B5A"> <span class="uicontrol">Target</span>／<span class="uicontrol">キャンペーン</span>レポート（有効化されている場合） </li> 
       <li id="li_6D4E65DD6E2B49C9A8C12181D23F185A">訪問別滞在時間 </li> 
       <li id="li_C6D3AD5A534243A8A6E17C663FEBA6BA">サイトセクション </li> 
       <li id="li_E1F46EED5CE2425D83200A2FCB686EE5">入口ページ </li> 
       <li id="li_1201EE0EBF13476C9A9525E0700F30F3">ほとんどのトラフィックソースレポート </li> 
       <li id="li_563E07858FB1473BB22C2B191E8BE620">訪問回数 </li> 
       <li id="li_1CAD77ABA6A2454282A4DA7E88C047E8">多数の訪問者プロファイルレポート </li> 
       <li id="li_D3A04E4CD8EC4646AAB90BF19F0AFA8A">すべてのコンバージョン変数とリスト変数 </li> 
       <li id="li_01C194CE0F3E4C0694A34B4C6697F385">訪問回数のほか、日別、週別、月別、四半期別、および不定の実訪問者数が使用できます。 </li> 
      </ul> </li> 
    </ul> <p>このレポートではセグメントを利用できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Hoc Analysis </td> 
   <td colname="col2"> 
    <ul id="ul_DFF9BFC01FC1424B8905C2D2C0EFD156"> 
     <li id="li_65FDF1C165C84F729E0EE84FF671B5E4">Ad Hoc Analysis では、基本的にマーケティングレポートインターフェイス内の他のすべてのレポートでサイトセクションレポートを分類できます。 </li> 
     <li id="li_2159DE10C52D40AA89E4C934FC184641">前述のすべてのイベントに加えて、すべてのコンバージョンおよびトラフィック指標を利用できるほか、すべてのコンバージョン指標について様々な配分を使用できます。 </li> 
     <li id="li_3A23C6286D314B5D814612469F4F77C5">このレポートでは複数の高度なアドバンスセグメントを使用できます。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

