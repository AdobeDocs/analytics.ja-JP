---
title: linkDownloadFileTypes
description: ダウンロードリンクとして自動的に追跡されるファイル拡張子を指定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkDownloadFileTypes

を有効 [`trackDownloadLinks`](trackdownloadlinks.md) にし、訪問者がリンクをクリックすると、AppMeasurementはリンクのURLをチェックしてファイルタイプの拡張子を確認します。 リンクURLににで見つかったファイルタイプが含まれている場合、ダ `linkDownloadFileTypes`ウンロードリンクイメージリクエストが自動的に送信されます。

を使用し `linkDownloadFileTypes` て、ダウンロードリンクとしてカウントするファイル拡張子をカスタマイズします。

> [!NOTE] 実際のクリックのみが自動的に追跡されます。 次のタイプのリンクは自動的には追跡されません。
>
> * ページの読み込み時に自動的に開始するファイルのダウンロード
> * リダイレクト後にトリガーされるダウンロード
> * 右クリックし、「ターゲットに名前を付けて保存」を選択します。
> * JavaScriptを使用するリンク( `javascript:openLink()`
>
> 
これらのダウンロードタイプでは、手動でメソッドを呼び出すことがで [`tl()`](../functions/tl-method.md) きます。

クリックされたリンクが離脱リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクのタイプが優先されます。

## Adobe Experience Platform Launchでの拡張機能のダウンロード

「ダウンロード拡張子」は、Adobe Analyticsの拡張子を設定する際に、アコーディオンの下にさらに追加するフ [!UICONTROL Link Tracking] ィールドを持つファイル拡張子のリストです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオ [!UICONTROL Link Tracking] ンを展開すると、フィールドが表示 [!UICONTROL Download Extensions] されます。

フィールドにテキストを入力し、をクリックして、ファイル拡張子をリストに追加しま [!UICONTROL Add]す。 「X」アイコンをクリックして、リストからファイル拡張子を削除します。

## AppMeasurementのs.linkDownloadFileTypesおよびカスタムコードエディターの起動

変数 `s.linkDownloadFileTypes` は、カンマで区切られたファイル拡張子の文字列です。 スペースは使用しないでください。

この変数を定義していない場合、（が有効な場合でも）自動ダウンロードリンクトラッキングは機 [`trackDownloadLinks`](trackdownloadlinks.md) 能しま `true`せん。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
