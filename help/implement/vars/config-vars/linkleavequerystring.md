---
title: linkLeaveQueryString
description: リンクトラッキングディメンションでクエリ文字列を保持できます。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkLeaveQueryString

AppMeasurementは、デフォルトで、リンクトラッキングURLからクエリ文字列を削除します。 変数を使用し `linkLeaveQueryString` て、リンクトラッキングディメンションのクエリ文字列を保持します。

一部の離脱リンクおよびダウンロードリンクでは、URLの重要な部分がクエリ文字列に含まれる場合があります。 例えば、などのダウンロードリンクは、クエ `https://example.com/download.asp?filename=myfile.exe` リ文字列に重要なリンク情報を含んでいます。

リンクトラッキング情報がサイトのURLに含まれていない場合、この変数を使用する必要はありません。 リンク追跡URLからクエリ文字列を削除すると、ディメンションに含まれる一意の値の数を制限できます。

有効にす `linkLeaveQueryString` ると、すべてのリンクトラッキングディメンション（カスタムリンク、離脱リンク、ダウンロードリンクを含む）に適用されます。

> [!TIP] この変数は、リンクトラッキング以外のディメンションには影響しません。 これは、カスタムリンク、離脱リンクおよびダウンロードリンクにのみ影響します。

## Adobe Experience Platform LaunchでURLパラメーターを保持

[!UICONTROL Keep URL Parameters] は、Adobe Analyticsの拡張機能を設定する際に、ア [!UICONTROL Link Tracking] コーディオンの下にあるチェックボックスです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオンを展 [!UICONTROL Link Tracking] 開し、チェックボックスを表 [!UICONTROL Keep URL Parameters] 示します。

リンクトラッキングディメンションにクエリ文字列を含める場合は、このチェックボックスをオンにします。

## AppMeasurementのs.linkLeaveQueryStringとカスタムコードエディターの起動

変数 `s.linkLeaveQueryString` はブール値です。 Its default value is `false`.

* この変数をに設定した場合、ク `true`エリ文字列はリンクトラッキングURLに保持されます。
* この変数がに設定されているか、定義さ `false` れていない場合、リンクトラッキングURLからクエリ文字列が削除されます。

```js
s.linkLeaveQueryString = true;
```

## 例   

この変数をtrueに設定する場合は、、、などのリンクトラッキングフィルタに影響を与える可能性があるので、注 [`linkInternalFilters`](linkinternalfilters.md)意して [`linkExternalFilters`](linkexternalfilters.md)くださ [`linkDownloadFiletypes`](linkdownloadfiletypes.md)い。

次の例は、オンの場合と同じです `adobe.com`。

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
