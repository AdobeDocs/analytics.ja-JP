---
description: Analytics の導入時のリンクトラッキングのための Dynamic Tag Management のフィールドの説明です。
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: リンクトラッキング
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# リンクトラッキング

Analytics の導入時のリンクトラッキングのための Dynamic Tag Management のフィールドの説明です。

**[!UICONTROL *`Property`*]**／**[!UICONTROL   ![](assets/settings_gear.png)

ツールを編集]**／**[!UICONTROL リンクトラッキング]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ClickMap を有効にする </td> 
   <td colname="col2"> <p>訪問者クリックマップ用のデータを収集するかどうかを指定します。 </p> <p>詳しくは、<a href="/help/implement/js-implementation/c-variables/configuration-variables.md"  >s.trackInlineStats</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ダウンロードリンクを追跡 </td> 
   <td colname="col2"> <p>サイト上のダウンロード可能なファイルへのリンクを追跡します。 </p> <p>詳しくは、<a href="/help/implement/js-implementation/c-variables/configuration-variables.md">設定変数</a>を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ダウンロード拡張子 </td> 
   <td colname="col2"> <p>サイトにリストに記載された拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクの URL がレポートに表示されます。 </p>詳しくは、<a href="/help/implement/js-implementation/c-variables/configuration-variables.md">設定変数</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 離脱リンクを追跡 </td> 
   <td colname="col2"> <p>クリックされたリンクのいずれかが他のサイトへのリンクであるかどうかが判断されます。 </p> <p>詳しくは、<a href="/help/implement/js-implementation/c-variables/configuration-variables.md">設定変数</a>を参照してください。 </p> <p><b>単一ページアプリに関する考慮事項：</b>一部の SPA（単一ページアプリ）Web サイトで採用されているコーディング方法の場合、その SPA サイト上にあるページへの内部リンクが、外部リンクの形式になっていることがあります。 </p> <p>SPA サイトから外部へのリンクは、以下のいずれかの方法でトラッキングできます。 </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>SPA からの外部リンクをトラッキングする必要がない場合は、「<span class="wintitle">追跡しない</span> 」セクションにエントリを追加します。 </p> <p>例：<span class="filepath">https://testsite.com/spa/#</span> </p> <p>このホストに対する # リンクはすべて無視されます。その他のホストに対するすべての外部リンク（例：<span class="filepath">https://www.google.com</span>）は追跡されます。 </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>SPA 上にある一部のリンクをトラッキングする必要がある場合は、「<span class="wintitle">常に追跡</span>」セクションを使用します。 </p> <p>例えば、<span class="filepath">spa/#/about</span> にあるページをトラッキングするには、「about」を「<span class="wintitle">常に追跡</span>」セクションに登録します。 </p> <p>そうすると、外部リンクのうち「about」ページだけがトラッキングされます。ページ上にあるその他のリンク（例：<span class="filepath">https://www.google.com</span>）は追跡されません。 </p> </li> 
    </ul> <p>これらのオプションは、どちらか一方しか使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL パラメーターを保持 </td> 
   <td colname="col2"> <p>クエリ文字列を維持します。 </p> <p>詳しくは、<a href="/help/implement/js-implementation/c-variables/configuration-variables.md">設定変数</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>
