---
description: Analytics のデプロイ時にページコードをカスタマイズするには、Dynamic Tag Management のフィールドの説明を使用します。
keywords: Dynamic Tag Management, ページコードのカスタマイズ, エディターの起動, 実行
seo-description: Analytics のデプロイ時にページコードをカスタマイズするには、Dynamic Tag Management のフィールドの説明を使用します。
seo-title: ページコードのカスタマイズ
solution: Experience Cloud, Analytics, Target, Dynamic Tag Management
title: ページコードのカスタマイズ
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# ページコードのカスタマイズ

Analytics のデプロイ時にページコードをカスタマイズするには、Dynamic Tag Management のフィールドの説明を使用します。

Analytics ツールと同時に確実にコードを実行させるには、プラグインを追加します。Analytics のプラグインについて詳しくは、[実装プラグイン](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F)を参照してください。

**[!UICONTROL *`Property`*]**／**[!UICONTROL   ![](assets/settings_gear.png)

ツールの編集]**／**[!UICONTROL ページコードをカスタマイズ]**

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

