---
description: Analytics のデプロイ時にページコードをカスタマイズするには、Dynamic Tag Management のフィールドの説明を使用します。
keywords: Dynamic Tag Management;ページコードのカスタマイズ;open editor;execute
seo-description: Analytics のデプロイ時にページコードをカスタマイズするには、Dynamic Tag Management のフィールドの説明を使用します。
seo-title: ページコードのカスタマイズ
solution: Marketing Cloud、Analytics、Target、Dynamic Tag Management
title: ページコードのカスタマイズ
uuid: b7CAD069-3eb8-4388- b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# ページコードのカスタマイズ

Analytics のデプロイ時にページコードをカスタマイズするには、Dynamic Tag Management のフィールドの説明を使用します。

Analytics ツールと同時に確実にコードを実行させるには、プラグインを追加します。Analytics のプラグインについて詳しくは、 [導入プラグイン](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**[!UICONTROL *`Property`*]** &gt;**[!UACROL ![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Customize Page Code]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>エディターを開く </p> </td> 
   <td colname="col2"> <p><code>s_code</code> に含まれる、最後の <code>s.t()</code> 呼び出しの前にトリガーされる必要のある任意の JavaScript 呼び出しを挿入できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>実行 </p> </td> 
   <td colname="col2"> <p> 「<b>UI 設定の前</b>」：インターフェイス設定をカスタムコードよりも優先します（例えば、インターフェイスで設定が有効になっている場合に eVar をオーバーライドする場合）。 </p> <p> 「<b>UI 設定の後</b>」：カスタムコードをインターフェイス設定よりも優先します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

