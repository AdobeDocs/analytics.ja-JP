---
description: Analytics の導入時のリンクトラッキングのための Dynamic Tag Management のフィールドの説明です。
keywords: Dynamic Tag Management;リンクトラッキング、ClickMapを有効にする;ダウンロードリンク、ダウンロード拡張機能、トラッキングリンク、URLパラメーターを保持
seo-description: Analytics の導入時のリンクトラッキングのための Dynamic Tag Management のフィールドの説明です。
seo-title: リンクトラッキング
solution: Marketing Cloud、Analytics、Dynamic Tag Management
title: リンクトラッキング
uuid: 982b744b-5696-4c31- b1d1-410486b0edd
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# リンクトラッキング

Analytics の導入時のリンクトラッキングのための Dynamic Tag Management のフィールドの説明です。

**[!UICONTROL *`Property`*]** &gt;**[!UACROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Link Tracking]**

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
   <td colname="col2"> <p>Visitor Click Map データを収集するかどうかを決定します。 </p> <p>詳しくは、<a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local">s.trackInlineStats</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ダウンロードリンクを追跡 </td> 
   <td colname="col2"> <p>サイト上のダウンロード可能なファイルへのリンクを追跡します。 </p> <p>[設定変数]（/help/implementing/js- implementation/c- variables/configuration- variables. md）を参照してください。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ダウンロード拡張子 </td> 
   <td colname="col2"> <p>サイトにリストに記載された拡張子の付いたファイルへのリンクが含まれる場合、これらのリンクの URL がレポートに表示されます。 </p>[設定変数]（/help/implementing/js- implementation/c- variables/configuration- variables. md）を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 離脱リンクを追跡 </td> 
   <td colname="col2"> <p>クリックされたリンクのいずれかが他のサイトへのリンクであるかどうかが判断されます。 </p> <p>[設定変数]（/help/implementing/js- implementation/c- variables/configuration- variables. md）を参照してください。 </p> <p><b>単一ページアプリに関する考慮事項：</b>一部の SPA（単一ページアプリ）Web サイトで採用されているコーディング方法の場合、その SPA サイト上にあるページへの内部リンクが、外部リンクの形式になっていることがあります。 </p> <p>SPA サイトから外部へのリンクは、以下のいずれかの方法でトラッキングできます。 </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>SPA からの外部リンクをトラッキングする必要がない場合は、「<span class="wintitle">追跡しない</span> 」セクションにエントリを追加します。 </p> <p>For example, <span class="filepath"> https://testsite.com/spa/#</span> </p> <p>このホストに対する # リンクはすべて無視されます。All outbound links to other hosts are tracked, such as <span class="filepath"> https://www.google.com</span>. </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>SPA 上にある一部のリンクをトラッキングする必要がある場合は、「<span class="wintitle">常に追跡</span>」セクションを使用します。 </p> <p>例えば、<span class="filepath">spa/#/about</span> にあるページをトラッキングするには、「about」を「<span class="wintitle">常に追跡</span>」セクションに登録します。 </p> <p>そうすると、外部リンクのうち「about」ページだけがトラッキングされます。Any other links on the page (for example, <span class="filepath"> https://www.google.com</span>) are not tracked. </p> </li> 
    </ul> <p>これらのオプションは、どちらか一方しか使用できません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL パラメーターを保持 </td> 
   <td colname="col2"> <p>クエリ文字列を維持します。 </p> <p>[設定変数]（/help/implementing/js- implementation/c- variables/configuration- variables. md）を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

