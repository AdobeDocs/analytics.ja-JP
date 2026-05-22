---
title: linkDownloadFileTypes
description: ダウンロードリンクとして自動的に追跡されるファイル拡張子を決定します。
feature: Appmeasurement Implementation
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/Qt6o34l2I96kZhsuK6zh3L8OsP7vJI4QiEUYeH6SeP4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 419
ht-degree: 57%

---

# linkDownloadFileTypes

[`trackDownloadLinks`](trackdownloadlinks.md) （AppMeasurement）または[`clickCollectionEnabled`](trackdownloadlinks.md) （Web SDK）が有効になっていて、訪問者がリンクをクリックすると、AppMeasurementはリンクのURLでファイル形式の拡張機能を確認します。 リンク URLに一致するファイルタイプが含まれている場合、ダウンロードリンク画像リクエストが自動的に送信されます。

`linkDownloadFileTypes` を使用して、ダウンロードリンクとしてカウントするファイル拡張子をカスタマイズします。

>[!NOTE]
>
>実際のクリックのみが自動的に追跡されます。 次のタイプのリンクは自動的には追跡されません。
>
>* ページ読み込み時に自動的に開始するファイルダウンロード
>* リダイレクト後にトリガーするダウンロード
>* 右クリックして「ターゲットに名前を付けて保存…」を選択します
>* JavaScript を使用するリンク（`javascript:openLink()` など）
>
>これらのダウンロードタイプでは、[`link tracking`](../functions/tl-method.md)呼び出しを手動で送信できます。

クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Web SDK拡張機能を使用したリンク修飾子のダウンロード

「[!UICONTROL  ダウンロードリンク修飾子]」テキストフィールドでは、クリックされたリンクがダウンロードリンクとして認定されるかどうかを判断するために正規表現を使用します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. [!UICONTROL 拡張機能] タブに移動し、[!UICONTROL Adobe Experience Platform Web SDK]の下にある&#x200B;**[!UICONTROL Configure]** ボタンをクリックします。
1. [!UICONTROL  データ収集]で、**[!UICONTROL ダウンロードリンク修飾子]** テキストフィールドに目的の値を設定します。

## Web SDKを手動で実装するリンク修飾子のダウンロード

[`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=ja#automaticLinkTracking)を使用してSDKを[構成](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)します。 このフィールドは、クリックしたURLに正規表現を使用して、有効なダウンロードリンクかどうかを判断します。 `downloadLinkQualifier`が定義されていない場合、デフォルト値は`\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`に設定されます。

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

フィールドにテキストを入力し、「**[!UICONTROL 追加]**」をクリックして、リストにファイル拡張子を追加します。 それぞれの&#x200B;**&#39;X&#39;** アイコンをクリックして、リストからファイル拡張子を削除します。

## AppMeasurementのs.linkDownloadFileTypesとAnalytics拡張機能のカスタムコードエディター

`s.linkDownloadFileTypes` 変数は、コンマで区切られたファイル拡張子の文字列です。 スペースは使用しないでください。

この変数を定義していないと、（[`trackDownloadLinks`](trackdownloadlinks.md) が `true` である場合でも）自動ダウンロードリンクトラッキングは機能しません。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
