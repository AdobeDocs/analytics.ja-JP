---
title: linkLeaveQueryString
description: リンクトラッキングディメンションでクエリ文字列を保持できます。
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkLeaveQueryString

AppMeasurementは、デフォルトで、リンクトラッキングURLからクエリ文字列を削除します。 リンクトラッキングディメンションでクエリ文字列を保持するには、linkLeaveQueryString変数を使用します。

一部の離脱リンクおよびダウンロードリンクでは、URLの重要な部分をクエリ文字列に含めることができます。 例えば、ダウンロードリンクのような場合、クエ `https://example.com/download.asp?filename=myfile.exe` リ文字列に重要なリンク情報が含まれます。

サイト上のURLにリンクトラッキング情報が含まれていない場合、この変数を使用する必要はありません。 リンクトラッキングURLからクエリ文字列を削除すると、ディメンションに含まれる一意の値の数を制限するのに役立ちます。

有効にす `linkLeaveQueryString` ると、すべてのリンクトラッキングディメンション（カスタムリンク、離脱リンク、ダウンロードリンクを含む）に適用されます。

> [!TIP] この変数は、リンクトラッキング以外のディメンションには影響しません。 これは、カスタムリンク、離脱リンクおよびダウンロードリンクにのみ影響します。

## Adobe Experience Platform LaunchでURLパラメーターを保持

[!UICONTROL 「URLパラメーターを保持] 」は、Adobe Analyticsの拡張機能を設定する際に [!UICONTROL 、「リンクトラッキング] 」アコーディオンの下にあるチェックボックスです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「リンクトラッ [!UICONTROL キング] 」アコーディオンを展開すると、「URLパラメーターを保持」 [!UICONTROL チェックボックスが表示されます] 。

リンクトラッキングディメンションにクエリ文字列を含める場合は、このチェックボックスをオンにします。

## AppMeasurementのs.linkLeaveQueryStringおよびカスタムコードエディターの起動

変数 `s.linkLeaveQueryString` はブール値です。 Its default value is `false`.

* この変数をに設定した場合、ク `true`エリ文字列はリンクトラッキングURLに保持されます。
* この変数が設定されているか、定義され `false` ていない場合、リンクトラッキングURLからクエリ文字列が削除されます。

```js
s.linkLeaveQueryString = true;
```

## 例

この変数をtrueに設定する場合は、、、などのリンクトラッキングフィルタに影響を与える可能性があるので、注 `linkInternalFilters`意して `linkExternalFilters`くださ `linkDownloadFiletypes`い。

次の例をオンにしたかのように考えてみま `adobe.com`す。

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
