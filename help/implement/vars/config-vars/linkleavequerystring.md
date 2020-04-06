---
title: linkLeaveQueryString
description: リンクトラッキングディメンションでクエリー文字列を保持できます。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkLeaveQueryString

AppMeasurement は、デフォルトで、リンクトラッキング URL からクエリー文字列を削除します。Use the `linkLeaveQueryString` variable to preserve query strings in link tracking dimensions.

ただし、一部の出口リンクおよびダウンロードリンクでは、URL の重要な部分は、クエリー文字列内にあることがあります。例えば、`https://example.com/download.asp?filename=myfile.exe` のようなダウンロードリンクの場合、クエリー文字列に重要なリンク情報が含まれます。

サイト上の URL にリンクトラッキング情報が含まれていない場合、この変数を使用する必要はありません。リンクトラッキング URL からクエリー文字列を削除すると、ディメンションに含まれる一意の値の数を制限するのに役立ちます。

`linkLeaveQueryString` を有効にすると、すべてのリンクトラッキングディメンション（カスタムリンク、出口リンク、ダウンロードリンクを含む）が有効になります。

>[!TIP] この変数は、リンクトラッキング以外のディメンションには影響しません。カスタムリンク、出口リンク、ダウンロードリンクのみが影響されます。

## Adobe Experience Platform Launch の「URL パラメーターの保持」

[!UICONTROL Keep URL Parameters] は、Adobe Analyticsの拡張機能を設定する際に、ア [!UICONTROL Link Tracking] コーディオンの下にあるチェックボックスです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオンを展 [!UICONTROL Link Tracking] 開し、チェックボックスを表 [!UICONTROL Keep URL Parameters] 示します。

リンクトラッキングディメンションにクエリー文字列を含める場合は、このチェックボックスをオンにします。

## AppMeasurement および Launch カスタムコードエディターの s.linkLeaveQueryString

`s.linkLeaveQueryString` 変数はブール値です。デフォルト値は `false` です。

* この変数を `true` に設定した場合、クエリー文字列はリンクトラッキング URL に保持されます。
* この変数が `false` に設定されているか、定義されていない場合、リンクトラッキング URL からクエリー文字列が削除されます。

```js
s.linkLeaveQueryString = true;
```

## 例

この変数を true に設定する場合、[`linkInternalFilters`](linkinternalfilters.md)、[`linkExternalFilters`](linkexternalfilters.md)、[`linkDownloadFiletypes`](linkdownloadfiletypes.md) などのリンクトラッキングフィルターに影響する可能性があるので、注意してください。

次の例を `adobe.com` にあるとして考えます。

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
