---
title: レガシーデバッガー
description: 従来のデバッガーをインストールします。 このデバッガーは、Analytics、Target、Advertising、Identity ServiceおよびData Collection タグのタグを検査します。
feature: Implementation Basics
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
TQID: 'https://experienceleague.adobe.com/UzZipOHP99eBzygkSajbyuPsWsRM-MvfVf5Myv2CSmA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
subfeature_v2: id: e992d880-33bc-4949-a648-aa7d410276cd
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 681
ht-degree: 75%

---

# レガシーデバッガー

>[!IMPORTANT]
>
>このデバッグツールはメンテナンスされなくなりました。 Adobeでは、代わりに[Adobe CX Enterprise Debugger Chrome Extension](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用することをお勧めします。

[!UICONTROL Legacy Debugger]は、ほとんどのAdobe CX Enterprise サービスのタグを検査します。 デバッガーを使用すると、サイトの任意のページでアドビに送信されるデータを確認できます。 この情報を使用して、組織の導入のトラブルシューティングや検証をおこなうことができます。

## レガシーデバッガーのインストール

JavaScript ブックマークレットを作成してデバッガーをインストールします。

### 手順 1：ブックマークレットコードのコピー

次のコードをクリップボードにコピーします。

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### 手順 2：ブックマークレットコードのブックマークへの貼り付け

ブックマークの処理方法はブラウザーごとに異なりますが、概念は同じです。 ブックマークは、目的の名前と URL としてブックマークレットコードを使用して作成されます。

#### Chrome

[Chrome 拡張機能](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=ja)を使用したくない場合は、レガシーデバッガーブックマークレットを代わりに使用できます。

1. 右上の 3 つのドットをクリックし、ブックマーク／ブックマークマネージャーに移動します。 また、`Ctrl` + `Shift` + `O`（Windows）または `Cmd` + `Shift` + `O`（Mac）を押すこともできます。
2. ブックマークマネージャーの右上で、3 つのドットをクリックし、「新しいブックマークの追加」をクリックします。
3. 「名前」フィールドで「従来のデバッガー」というラベルを付け、コードスニペットをURL フィールドに貼り付けます。
4. ブックマークマネージャーを使用して、新しいブックマークレットを目的の場所に配置します。

#### Firefox

1. 右上の 3 本の線をクリックし、ライブラリ／ブックマーク／すべてのブックマークを表示の順に移動します。 また、`Ctrl` + `Shift` + `B`（Windows）または `Cmd` + `Shift` + `B`（Mac）を押すこともできます。
2. 整理／新しいブックマークをクリックします。
3. 「名前」フィールドで「従来のデバッガー」というラベルを付け、コードスニペットを「場所」フィールドに貼り付けます。 「タグ」フィールドと「キーワード」フィールドは必須ではありません。
4. ライブラリウィンドウを使用して、新しいブックマークレットを目的の場所に配置します。

#### Edge

Edge にはブックマークレットを手動で作成する機能はありませんが、ブックマーク URL を編集してブックマークレットにすることができます。

1. 「URL」フィールドの右側にある星形のアイコンをクリックして、現在のページにブックマークを付けます。
2. ブックマークに「従来のデバッガー」という名前を付け、目的の場所に保存します。
3. 線の付いた星形のアイコンをクリックして、お気に入りバーを開きます。
4. 新しく作成したブックマークを右クリックし、「URL を編集」を選択します。
5. テキストフィールドにコードスニペットを貼り付け、Enter キーを押します。

#### Safari

Safari ではブックマークレットを手動で作成することはできませんが、ブックマーク URL を編集してブックマークレットにすることができます。

1. 右上の共有アイコンをクリックすると、ブックマークモーダルウィンドウが開きます。
2. ブックマークに「従来のデバッガー」という名前を付け、目的の場所に保存します。
3. ブックマーク／ブックマークの編集をクリックし、新しく作成したブックマークを見つけます。
4. 右クリックして、「アドレスを編集」を選択し、コードスニペットをテキストフィールドに貼り付けます。

## レガシーデバッガーの使用

サイト上の目的のページに移動し、ブックマークレットをクリックします。 アドビに送信されたデータを示すポップアップウィンドウが表示されます。

>[!NOTE]
>
>特定の広告ブロッキングプラグインやポップアップブロッカーが、デバッガーウィンドウの読み込みを妨げる可能性があります。 ブラウザーでブロックされたポップアップを確認し、デバッガーが正しく動作するようにポップアップを許可します。

デバッガーには複数のオプションが用意されており、そのすべてでデータの表示方法をカスタマイズできます。 これらのオプションはデータ収集に影響を与えません。

* **[!UICONTROL 表示されたExperience Cloud製品]**：各CX Enterprise製品のイメージリクエストを表示または非表示にします。
* **[!UICONTROL URL デコード]**: URLは、レポートに表示される内容に一致するように画像リクエストをデコードします。 このチェックボックスはオンのままにすることをお勧めします。
* **[!UICONTROL 自動更新]**：数秒ごとにポップアップを自動的に更新して、ページ上のその他の画像リクエストを確認します。 デバッガーでコンテンツをコピー／ペーストする必要がある場合は、自動更新を無効にして、選択を維持します。
* **[!UICONTROL わかりやすい形式]**：画像リクエスト内の役に立つラベルと生のクエリ文字列の表示形式を切り替えます。 詳しくは、[データ収集クエリーのパラメーター](query-parameters.md)を参照してください。

デバッガーのデフォルトの表示オプションを保存するには、右上隅の「Adobe Debugger」リンクを右クリックし、リンクアドレスをコピーします。 現在のデバッガーのブックマークレットを編集し、更新したコードスニペットを「URL」フィールドに貼り付けます。
