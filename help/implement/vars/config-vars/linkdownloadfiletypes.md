---
title: linkDownloadFileTypes
description: ダウンロードリンクとして自動的に追跡されるファイル拡張子を決定します。
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 55%

---

# linkDownloadFileTypes

条件 [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) または [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) が有効になっていて、訪問者がリンクをクリックすると、AppMeasurementはリンクの URL でファイルタイプ拡張子を確認します。 リンク URL に一致するファイルタイプが含まれている場合、ダウンロードリンクイメージリクエストが自動的に送信されます。

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
>これらのダウンロードタイプでは、 [`link tracking`](../functions/tl-method.md) を呼び出します。

クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Web SDK 拡張機能を使用してリンク修飾子をダウンロード

The [!UICONTROL リンク修飾子をダウンロード] テキストフィールドは正規表現を使用して、クリックされたリンクがダウンロードリンクに該当するかどうかを判断します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. の下 [!UICONTROL データ収集]」をクリックし、 **[!UICONTROL リンク修飾子をダウンロード]** テキストフィールド。

## Web SDK を手動で実装するリンク修飾子をダウンロード

[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja) を使用する SDK [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja#automaticLinkTracking). このフィールドは、クリックされた URL の正規表現を使用して、有効なダウンロードリンクであるかどうかを判断します。 次の場合 `downloadLinkQualifier` が定義されていない場合、デフォルト値は `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

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

フィールドにテキストを入力し、「**[!UICONTROL 追加]**」をクリックして、リストにファイル拡張子を追加します。リストからファイル拡張子を削除するには、該当する **&#39;X&#39;** アイコン。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.linkDownloadFileTypes

`s.linkDownloadFileTypes` 変数は、コンマで区切られたファイル拡張子の文字列です。スペースは使用しないでください。

この変数を定義していないと、（[`trackDownloadLinks`](trackdownloadlinks.md) が `true` である場合でも）自動ダウンロードリンクトラッキングは機能しません。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
