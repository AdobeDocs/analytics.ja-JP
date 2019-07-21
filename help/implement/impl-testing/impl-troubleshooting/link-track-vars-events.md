---
description: リンクトラッキングの導入を正しくおこなうために重要なことは、s.linkTrackVars 変数と s.linkTrackEvents 変数について理解することです。これらの変数を使用して、ユーザーのアクション実行時にカスタム変数の値を渡すことができます。
keywords: Analytics の導入
seo-description: リンクトラッキングの導入を正しくおこなうために重要なことは、s.linkTrackVars 変数と s.linkTrackEvents 変数について理解することです。これらの変数を使用して、ユーザーのアクション実行時にカスタム変数の値を渡すことができます。
seo-title: s.linkTrackVars と s.linkTrackEvents の使用
solution: Analytics
title: s.linkTrackVars と s.linkTrackEvents の使用
topic: 開発者と導入
uuid: f6b7019b-987b-4b7d- a446-80205f7cc36c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# s.linkTrackVars と s.linkTrackEvents の使用

リンクトラッキングの導入を正しくおこなうために重要なことは、s.linkTrackVars 変数と s.linkTrackEvents 変数について理解することです。これらの変数を使用して、ユーザーのアクション実行時にカスタム変数の値を渡すことができます。

カスタムリンクトラッキングを導入し、[!UICONTROL custom] 変数と *`events`*&#x200B;に設定します。 [!UICONTROL s. linkTrackVars] 変数に *`events`* 、変数を含めて渡されるすべての変数のコンマ区切りリストが含まれていることを確認します。[!UICONTROL s.linkTrackEvents] に、渡されるすべてのイベントのコンマ区切りリストが含まれていることを確認します。

[!UICONTROL s.linkTrackVars] および [!UICONTROL s.linkTrackEvents] の設定によって、実際にこれらの変数やイベントが設定されるわけではなく、[!DNL Analytics] コードで設定できるようにするための準備がおこなわれます。手動で変数を設定する必要があります。次に例を示します。

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 
```

events が [!UICONTROL s.linkTrackVars] 変数に含まれていることに注意してください。渡される個々のイベントは、[!UICONTROL s.linkTrackEvents] 変数にも、関数の後の [!UICONTROL s.events] にも含まれます。渡される各変数は、関数の後で入力される前に、[!UICONTROL s.linkTrackVars] にリストされています。また、「event9」は [!UICONTROL s.linkTrackEvents] に含まれていますが、[!UICONTROL s.events] には含まれていません。「event9」は記録されませんが、ユーザーの選択により s.events="event5,event9" が設定された場合は記録されます。

自動ファイルダウンロードと[!UICONTROL 離脱]リンクトラッキングの動作は異なります。標準的な [!UICONTROL  ファイルには ]s.linkTrackVars[!UICONTROL  と ]s.linkTrackEvents[!DNL s_code.js] が含まれ、どちらも none に設定されています。これらの変数は通常、[!DNL s_code.js] ファイルでは none に設定されたままにし、自動リンクトラッキングでは（[!UICONTROL カスタムリンクトラッキング]とは異なり）グローバル JavaScript ファイルに設定した [!UICONTROL s.linkTrackVars] および [!UICONTROL s.linkTrackEvents] の値が使用されるようにします。また、ファイルダウンロードまたは[!UICONTROL 離脱]リンクが記録されるたびに、これらの変数に存在する値をすべて渡します。

ページが読み込まれる際に s.channel="Home" となり、[!DNL s_code.js] ファイルでは s.linkTrackVars="channel" となる例を考えてみます。ユーザーがクリックしてファイルのダウンロードをおこなうと、ファイルダウンロードの自動トラッキングによって、ページの読み込み時に設定された [!DNL Analytics]s.channel[!UICONTROL  の値を含むデータが ] に渡されます。2 回目に「Home」が渡されると、[!UICONTROL サイトセクション]レポートでこの値のページビューデータが水増しされます。

アドビでは、グローバル JavaScript ファイルで [!UICONTROL s.linkTrackVars] と [!UICONTROL s.linkTrackEvents] を「none」に設定しておき、必要に応じて、[!UICONTROL カスタムリンクトラッキング]の導入でこれらの変数を明示的に設定することを強く推奨します。
