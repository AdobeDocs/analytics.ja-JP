---
title: linkDownloadFileTypes
description: ダウンロードリンクとして自動的に追跡されるファイル拡張子を決定します。
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 100%

---

# linkDownloadFileTypes

[`trackDownloadLinks`](trackdownloadlinks.md) を有効にし、訪問者がリンクをクリックすると、AppMeasurement はリンクの URL でファイルタイプ拡張子を確認します。リンク URL に `linkDownloadFileTypes` で見つかったファイルタイプが含まれている場合、ダウンロードリンクイメージリクエストが自動的に送信されます。

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
>これらのダウンロードタイプでは、手動で [`tl()`](../functions/tl-method.md) メソッドを呼び出すことができます。

クリックされたリンクが出口リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Adobe Experience Platform のタグを使用した拡張機能のダウンロード

「ダウンロード拡張子」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にある、さらに追加するフィールドを含むファイル拡張子のリストです。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL ダウンロード拡張子]」フィールドが表示されます。

フィールドにテキストを入力し、「[!UICONTROL 追加]」をクリックして、リストにファイル拡張子を追加します。リストからファイル拡張子を削除するには、該当する「X」アイコンをクリックします。

## AppMeasurement および カスタムコードエディターの s.linkDownloadFileTypes 

`s.linkDownloadFileTypes` 変数は、コンマで区切られたファイル拡張子の文字列です。スペースは使用しないでください。

この変数を定義していないと、（[`trackDownloadLinks`](trackdownloadlinks.md) が `true` である場合でも）自動ダウンロードリンクトラッキングは機能しません。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
