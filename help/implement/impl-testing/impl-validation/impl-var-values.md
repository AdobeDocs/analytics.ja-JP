---
description: サーバーのスクリプトまたはコードによって設定される変数が、値に影響する引用符を出力しないことを確認してください。
keywords: Analytics の導入
seo-description: サーバーのスクリプトまたはコードによって設定される変数が、値に影響する引用符を出力しないことを確認してください。
seo-title: 変数と値
solution: Analytics
title: 変数と値
topic: 開発者と導入
uuid: 2ff4857a-9451-4794-9146- f417abd1d1ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 変数と値

サーバーのスクリプトまたはコードによって設定される変数が、値に影響する引用符を出力しないことを確認してください。

例：

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 
```

変数の値は、このドキュメントで指定されている最大の長さを超えないようにしてください。超過した文字は、データ収集サーバーで切り捨てられます。余分な文字は、合計の長さに影響を与え、不必要に帯域幅が増加し、その他の問題も発生する可能性があります。

products 変数には、$、™、®、© またはコンマ（,）を使用しないでください。通常、これらの文字はどの [!DNL Analytics] 変数でも有用ではありません。また、フィールドの解釈やエクスポートの機能に影響を与える場合があります。使用する文字を ASCII 文字の最初の 127 文字に制限するのが最善の方法です。

Ensure that the events variable is populated with an appropriate value ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen], or event1-event5) whenever *`products`* is populated. 次のように、すべての [!DNL Analytics] 変数および関数で大文字と小文字の区別が維持されていることを確認してください。

```js
s.pageName 
s.server 
s.channel 
s.pageType 
s.prop1 - s.prop20 
s.campaign 
s.state 
s.zip 
s.events 
s.products 
s.purchaseID 
s.eVar1 - s.eVar20 
var s_code=s.t();if(s_code)document.write(s_code)//--> 
```

ページ名では大文字と小文字が区別され、大文字と小文字が異なると、ページレコードが追加されます。つまり、「Home」と「home」は、[!DNL Analytics] では 2 つの異なるページになります。

>[!NOTE]
>
>複数のページレコードをレポート内で結合することはできません。

リンクが[!UICONTROL カスタムリンク]レポートに表示されていることを確認します。[!UICONTROL tl] 関数に適切なパラメーターが渡されていることを確認します。[!UICONTROL カスタムリンク]について詳しくは、 [リンクトラッキング](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E).
