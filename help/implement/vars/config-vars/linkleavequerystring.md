---
title: linkLeaveQueryString
description: リンクトラッキングディメンションでクエリー文字列を保持できます。
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '289'
ht-degree: 100%

---

# linkLeaveQueryString

AppMeasurement は、デフォルトで、リンクトラッキング URL からクエリー文字列を削除します。`linkLeaveQueryString` 変数は、リンクトラッキングディメンションでクエリー文字列を保持するために使用します。

ただし、一部の出口リンクおよびダウンロードリンクでは、URL の重要な部分は、クエリー文字列内にあることがあります。例えば、`https://example.com/download.asp?filename=myfile.exe` のようなダウンロードリンクの場合、クエリー文字列に重要なリンク情報が含まれます。

サイト上の URL にリンクトラッキング情報が含まれていない場合、この変数を使用する必要はありません。リンクトラッキング URL からクエリー文字列を削除すると、ディメンションに含まれる一意の値の数を制限するのに役立ちます。

`linkLeaveQueryString` を有効にすると、すべてのリンクトラッキングディメンション（カスタムリンク、出口リンク、ダウンロードリンクを含む）が有効になります。

>[!TIP]
>
> この変数は、リンクトラッキング以外のディメンションには影響しません。カスタムリンク、出口リンク、ダウンロードリンクのみが影響されます。

## Adobe Experience Platform Launch の「URL パラメーターの保持」

「[!UICONTROL URL パラメーターの保持]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるチェックボックスです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL URL パラメーターの保持]」チェックボックスが表示されます。

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
