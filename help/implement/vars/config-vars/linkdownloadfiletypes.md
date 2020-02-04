---
title: linkDownloadFileTypes
description: ダウンロードリンクとして自動的に追跡されるファイル拡張子を決定します。
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkDownloadFileTypes

をに設定 `trackDownloadLinks` し、訪問者がリ `true` ンクをクリックすると、AppMeasurementはリンクのURLでファイルタイプ拡張子を確認します。 リンクURLににで見つかったファイルタイプが含まれている場合、ダ `linkDownloadFileTypes`ウンロードリンクイメージリクエストが自動的に送信されます。

を使用し `linkDownloadFileTypes` て、ダウンロードリンクとしてカウントするファイル拡張子をカスタマイズします。

> [!NOTE] 実際のクリックのみが自動的に追跡されます。 次のタイプのリンクは自動的には追跡されません。
>
> * ページの読み込み時に自動的に開始するファイルのダウンロード
> * リダイレクト後にトリガーされるダウンロード
> * 右クリックして「ターゲットに名前を付けて保存…」を選択します。
> * JavaScriptを使用するリンク( `javascript:openLink()`
>
> 
これらのダウンロードタイプでは、手動で関数を呼び出すことがで `tl()` きます。

クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Adobe Experience Platform Launchでの拡張機能のダウンロード

「ダウンロード拡張子」は、Adobe Analyticsの拡張機能を設定する際に、リンクトラッキングアコーディオンの下に  さらに追加するフィールドを含むファイル拡張子のリストです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「リンクトラッ [!UICONTROL キング] 」アコーディオンを展開すると、「ダウンロード拡張 [!UICONTROL 子」フィールドが表示されます] 。

フィールドにテキストを入力し、「追加」をクリックして、リストにファイル拡張子を追 [!UICONTROL 加します]。 リストからファイル拡張子を削除するには、該当するXアイコンをクリックします。

## AppMeasurementのs.linkDownloadFileTypesおよびカスタムコードエディターの起動

変数 `s.linkDownloadFileTypes` は、コンマで区切られたファイル拡張子の文字列です。 スペースは使用しないでください。

この変数を定義していない場合、（が有効な場合でも）自動ダウンロードリンクトラッキング `trackDownloadLinks` は機能し `true`ません。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v"
```
