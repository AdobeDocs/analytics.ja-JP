---
description: レガシーのAdobe Experience cloudデバッガーをインストールします。 このデバッガーは、Analytics、Target、Advertising Cloud、IDサービス、DTMおよび起動のタグを調べます。
seo-description: レガシーのAdobe Experience cloudデバッガーをインストールします。 このデバッガーは、Analytics、Target、Advertising Cloud、IDサービス、DTMおよび起動のタグを調べます。
seo-title: レガシーAdobe Experience cloudデバッガー
title: レガシーAdobe Experience cloudデバッガー
translation-type: tm+mt
source-git-commit: 2ea071c4d4f675c74770396610219d405a07a0e1

---


# レガシーAdobe Experience cloudデバッガー

> [!IMPORTANT] このデバッグツールはもはやメンテナンスされません。 代わりに、 [Adobe Experience Cloud Debugger Chrome Extensionを使用することをお勧めします](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)。

レガシー [!UICONTROL デバッガーは] 、ほとんどのAdobe Experience cloudサービスに対してタグを調べます。 デバッガーを使用すると、サイトの任意のページでアドビに送信されるデータを確認できます。 この情報を使用して、組織の導入のトラブルシューティングや検証を行うことができます。

## レガシーデバッガのインストール

JavaScriptブックマークレットを作成してデバッガーをインストールします。

### 手順1:ブックマークレットコードのコピー

次のコードをクリップボードにコピーします。

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### 手順2:ブックマークレットコードのブックマークへの貼り付け

ブックマークの処理方法はブラウザごとに異なりますが、概念は同じです。 目的の名前とブックマークレットコードをURLとして使用してブックマークが作成されます。

#### Chrome

chrome拡張機能を使用しないようにする場合は [](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)、レガシーデバッガーブックマークレットを代わりに使用できます。

1. 右上の3つのドットをクリックし、ブックマーク/ブックマークマネージャーに移動します。 また、+ `Ctrl` + `Shift` (Windows)または `O` + `Cmd` + `Shift` (Mac)を押すこともで `O` きます。
2. ブックマークマネージャーの右上で、3つのドットをクリックし、「新しいブックマークの追加」をクリックします。
3. 「名前」フィールドで、「Adobe Experience Cloud Debugger」というラベルを付け、「URL」フィールドにコードスニペットを貼り付けます。
4. Use the bookmark manager to place your new bookmarklet in the desired location.

#### Firefox

1. 右上の3行をクリックし、ライブラリ/ブックマーク/すべてのブックマークを表示に移動します。 You can also press  +  +  (Windows) or  +  +  (Mac).`Ctrl``Shift``B``Cmd``Shift``B`
2. Click Organize &gt; New Bookmark.
3. In the Name field, label it "Adobe Experience Cloud Debugger", and paste the code snippet into the Location field. The Tags and Keyword fields are not required.
4. Use the library window to place your new bookmarklet in the desired location.

#### Edge

Edge does not have the ability to manually create a bookmarklet, but a bookmark URL can be edited.

1. Click the star icon on the right side of the URL field to bookmark the current page.
2. Name the bookmark "Adobe Experience Cloud Debugger", and save it in the desired location.
3. Click the star icon with lines to open the Favorites bar.
4. Right click the newly created bookmark, the select 'Edit URL'.
5. Paste the code snippet in the text field, then hit Enter.

#### Safari

Safari does not have the ability to manually create a bookmarklet, but a bookmark URL can be edited.

1. 右上の共有アイコンをクリックすると、ブックマークモーダルウィンドウが開きます。
2. Name the bookmark "Adobe Experience Cloud Debugger", and save it in the desired location.
3. ブックマーク/ブックマークの編集をクリックし、新しく作成したブックマークを見つけます。
4. Right click &gt; Edit Address, then paste the code snippet into text field.

## レガシーデバッガーの使用

デバッガーを使用するには、サイト上の目的のページに移動し、ブックマークレットをクリックします。 アドビに送信されたデータを示すポップアップウィンドウが表示されます。

> [!NOTE] 特定の広告ブロッキングプラグインやポップアップブロッカーが、デバッガーウィンドウの読み込みを妨げる可能性があります。 ブラウザーでブロックされたポップアップを確認し、デバッガーが正しく動作するようにポップアップを許可します。

デバッガには複数のオプションが用意されており、そのすべてでデータの表示方法をカスタマイズできます。 これらのオプションはデータ収集に影響を与えません。

* **** Experience cloud製品の表示：各Experience cloud製品の画像リクエストの表示/非表示を切り替えます。
* **** URLデコード：URLは、イメージ要求をデコードして、レポートに表示される内容に一致させます。 このチェックボックスはオンのままにすることをお勧めします。
* **** 自動更新：数秒ごとにポップアップを自動的に更新し、ページ上で追加のイメージリクエストがないかどうかを確認します。 デバッガーでコンテンツをコピー/貼り付ける必要がある場合は、自動更新を無効にして、選択を維持します。
* **** わかりやすい形式：イメージリクエストで役立つラベルと生のクエリ文字列の表示形式を切り替えます。 詳しくは、 [データ収集クエリのパラメータ](../js-implementation/data-collection/query-parameters.md) ーを参照してください。

デバッガーのデフォルトの表示オプションを保存するには、右上隅の「Adobe Debugger」リンクを右クリックし、リンクアドレスをコピーします。 現在のデバッガーのブックマークレットを編集し、更新したコードスニペットを「URL」フィールドに貼り付けます。
