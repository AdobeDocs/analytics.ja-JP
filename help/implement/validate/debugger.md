---
title: レガシー Adobe Experience Cloud デバッガー
description: レガシー Adobe Experience Cloud デバッガーをインストールします。このデバッガーは、Analytics、Target、Advertising Cloud、ID サービスおよびデータ収集のタグを調べます。
feature: Implementation Basics
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 100%

---

# レガシー Adobe Experience Cloud デバッガー

>[!IMPORTANT]
>
>このデバッグツールはメンテナンスされなくなりました。代わりに、[Adobe Experience Cloud デバッガー Chrome 拡張機能](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用することをお勧めします。

[!UICONTROL レガシーデバッガー]は、ほとんどの Adobe Experience Cloud サービスに対してタグを調べます。デバッガーを使用すると、サイトの任意のページでアドビに送信されるデータを確認できます。この情報を使用して、組織の導入のトラブルシューティングや検証をおこなうことができます。

## レガシーデバッガーのインストール

JavaScript ブックマークレットを作成してデバッガーをインストールします。

### 手順 1：ブックマークレットコードのコピー

次のコードをクリップボードにコピーします。

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### 手順 2：ブックマークレットコードのブックマークへの貼り付け

ブックマークの処理方法はブラウザーごとに異なりますが、概念は同じです。ブックマークは、目的の名前と URL としてブックマークレットコードを使用して作成されます。

#### Chrome

[Chrome 拡張機能](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用したくない場合は、レガシーデバッガーブックマークレットを代わりに使用できます。

1. 右上の 3 つのドットをクリックし、ブックマーク／ブックマークマネージャーに移動します。また、`Ctrl` + `Shift` + `O`（Windows）または `Cmd` + `Shift` + `O`（Mac）を押すこともできます。
2. ブックマークマネージャーの右上で、3 つのドットをクリックし、「新しいブックマークの追加」をクリックします。
3. 「名前」フィールドで、「Adobe Experience Cloud Debugger」というラベルを付け、「URL」フィールドにコードスニペットを貼り付けます。
4. ブックマークマネージャーを使用して、新しいブックマークレットを目的の場所に配置します。

#### Firefox

1. 右上の 3 本の線をクリックし、ライブラリ／ブックマーク／すべてのブックマークを表示の順に移動します。また、`Ctrl` + `Shift` + `B`（Windows）または `Cmd` + `Shift` + `B`（Mac）を押すこともできます。
2. 整理／新しいブックマークをクリックします。
3. 「名前」フィールドで、「Adobe Experience Cloud Debugger」というラベルを付け、「場所」フィールドにコードスニペットを貼り付けます。「タグ」フィールドと「キーワード」フィールドは必須ではありません。
4. ライブラリウィンドウを使用して、新しいブックマークレットを目的の場所に配置します。

#### Edge

Edge にはブックマークレットを手動で作成する機能はありませんが、ブックマーク URL を編集してブックマークレットにすることができます。

1. 「URL」フィールドの右側にある星形のアイコンをクリックして、現在のページにブックマークを付けます。
2. ブックマークに「Adobe Experience Cloud Debugger」という名前を付け、目的の場所に保存します。
3. 線の付いた星形のアイコンをクリックして、お気に入りバーを開きます。
4. 新しく作成したブックマークを右クリックし、「URL を編集」を選択します。
5. テキストフィールドにコードスニペットを貼り付け、Enter キーを押します。

#### Safari

Safari ではブックマークレットを手動で作成することはできませんが、ブックマーク URL を編集してブックマークレットにすることができます。

1. 右上の共有アイコンをクリックすると、ブックマークモーダルウィンドウが開きます。
2. ブックマークに「Adobe Experience Cloud Debugger」という名前を付け、目的の場所に保存します。
3. ブックマーク／ブックマークの編集をクリックし、新しく作成したブックマークを見つけます。
4. 右クリックして、「アドレスを編集」を選択し、コードスニペットをテキストフィールドに貼り付けます。

## レガシーデバッガーの使用

サイト上の目的のページに移動し、ブックマークレットをクリックします。アドビに送信されたデータを示すポップアップウィンドウが表示されます。

>[!NOTE]
>
> 特定の広告ブロッキングプラグインやポップアップブロッカーが、デバッガーウィンドウの読み込みを妨げる可能性があります。ブラウザーでブロックされたポップアップを確認し、デバッガーが正しく動作するようにポップアップを許可します。

デバッガーには複数のオプションが用意されており、そのすべてでデータの表示方法をカスタマイズできます。これらのオプションはデータ収集に影響を与えません。

* **Experience Cloud 製品の表示**：各 Experience Cloud 製品の画像リクエストの表示／非表示を切り替えます。
* **URL デコード**：URL は、イメージリクエストをデコードして、レポートに表示される内容に一致させます。このチェックボックスはオンのままにすることをお勧めします。
* **自動更新**：数秒ごとにポップアップを自動的に更新し、ページ上で追加のイメージリクエストがないかどうかを確認します。デバッガーでコンテンツをコピー／ペーストする必要がある場合は、自動更新を無効にして、選択を維持します。
* **わかりやすい形式**：イメージリクエストで役立つラベルと生のクエリ文字列の表示形式を切り替えます。詳しくは、[データ収集クエリーのパラメーター](query-parameters.md)を参照してください。

デバッガーのデフォルトの表示オプションを保存するには、右上隅の「Adobe Debugger」リンクを右クリックし、リンクアドレスをコピーします。現在のデバッガーのブックマークレットを編集し、更新したコードスニペットを「URL」フィールドに貼り付けます。
