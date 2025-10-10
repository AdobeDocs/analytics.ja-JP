---
title: linkDownloadFileTypes
description: ダウンロードリンクとして自動的に追跡されるファイル拡張子を決定します。
feature: Appmeasurement Implementation
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 55%

---

# linkDownloadFileTypes

[`trackDownloadLinks`](trackdownloadlinks.md) （AppMeasurement）または [`clickCollectionEnabled`](trackdownloadlinks.md) （web SDK）が有効になっていて、訪問者がリンクをクリックすると、AppMeasurementが filetype 拡張機能のリンクの URL をチェックします。 リンク URL に一致する filetype が含まれている場合、ダウンロードリンク画像リクエストが自動的に送信されます。

`linkDownloadFileTypes` を使用して、ダウンロードリンクとしてカウントするファイル拡張子をカスタマイズします。

>[!NOTE]
>
> 実際のクリックのみが自動的に追跡されます。次のタイプのリンクは自動的には追跡されません。
>
>* ページ読み込み時に自動的に開始するファイルダウンロード
>* リダイレクト後にトリガーするダウンロード
>* 右クリックして「ターゲットに名前を付けて保存…」を選択します
>* JavaScript を使用するリンク（`javascript:openLink()` など）
>
>これらのダウンロードタイプについては、[`link tracking`](../functions/tl-method.md) 呼び出しを手動で送信できます。

クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Web SDK拡張機能を使用したリンク修飾子のダウンロード

[!UICONTROL &#x200B; ダウンロードリンク修飾子 &#x200B;] テキストフィールドでは、正規表現を使用して、クリックされたリンクがダウンロードリンクに該当するかどうかを判断します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」タブに移動し、「&lbrace;4 **[!UICONTROL Adobe Experience Platform Web SDK]**」の下にある「設定 [!UICONTROL &#x200B; ボタンをクリックします。]
1. [!UICONTROL &#x200B; データ収集 &#x200B;] の下の **[!UICONTROL ダウンロードリンク修飾子]** テキストフィールドに目的の値を設定します。

## Web SDKを手動で実装するリンク修飾子をダウンロードします

[&#128279;](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja) を使用して [`downloadLinkQualifier`SDKを &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja#automaticLinkTracking) 設定」します。 このフィールドでは、クリックされた URL に対して正規表現を使用して、有効なダウンロードリンクかどうかを判断します。 `downloadLinkQualifier` が定義されていない場合、デフォルト値は `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$` に設定されます。

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Adobe Analytics拡張機能を使用した拡張機能のダウンロード

「ダウンロード拡張子」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にある、さらに追加するフィールドを含むファイル拡張子のリストです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「**[!UICONTROL ダウンロード拡張子]**」フィールドが表示されます。

フィールドにテキストを入力し、「**[!UICONTROL 追加]**」をクリックして、リストにファイル拡張子を追加します。ファイル拡張子の **&#39;X&#39;のアイコンをクリックして、リストからファイル拡張子** 削除します。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 変数は、コンマで区切られたファイル拡張子の文字列です。スペースは使用しないでください。

この変数を定義していないと、（[`trackDownloadLinks`](trackdownloadlinks.md) が `true` である場合でも）自動ダウンロードリンクトラッキングは機能しません。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
