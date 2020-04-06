---
title: linkDownloadFileTypes
description: ダウンロードリンクとして自動的に追跡されるファイル拡張子を決定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkDownloadFileTypes

When [`trackDownloadLinks`](trackdownloadlinks.md) is enabled and a visitor clicks on a link, AppMeasurement checks the URL of the link for filetype extensions. リンク URL に `linkDownloadFileTypes` で見つかったファイルタイプが含まれている場合、ダウンロードリンクイメージリクエストが自動的に送信されます。

`linkDownloadFileTypes` を使用して、ダウンロードリンクとしてカウントするファイル拡張子をカスタマイズします。

>[!NOTE] 実際のクリックのみが自動的に追跡されます。次のタイプのリンクは自動的には追跡されません。
>
> * ページ読み込み時に自動的に開始するファイルダウンロード
> * リダイレクト後にトリガーするダウンロード
> * 右クリックして「ターゲットに名前を付けて保存…」を選択します
> * JavaScript を使用するリンク（`javascript:openLink()` など）
>
> 
For these download types, you can manually call the [`tl()`](../functions/tl-method.md) method.

クリックされたリンクが出口リンクとダウンロードリンクの両方の条件に一致する場合、ダウンロードリンクタイプが優先されます。

## Adobe Experience Platform Launch の「ダウンロード拡張子」

Download Extensions is a list of file extensions with a field to add more under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオ [!UICONTROL Link Tracking] ンを展開すると、フィールドが表示 [!UICONTROL Download Extensions] されます。

Add file extensions to the list by entering text in the field and clicking [!UICONTROL Add]. 「X」アイコンをクリックして、リストからファイル拡張子を削除します。

## AppMeasurement および Launch カスタムコードエディターの s.linkDownloadFileTypes 

`s.linkDownloadFileTypes` 変数は、コンマで区切られたファイル拡張子の文字列です。スペースは使用しないでください。

この変数を定義していないと、（[`trackDownloadLinks`](trackdownloadlinks.md) が `true` である場合でも）自動ダウンロードリンクトラッキングは機能しません。

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
