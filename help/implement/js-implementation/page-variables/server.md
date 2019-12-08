---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# server

 変数は、Web ページのドメイン（ユーザーがアクセスするドメインを表示）またはページを提供するサーバー（ロードバランシングのクイック参照用）を示すために使用されます。


<!-- 

server.xml

 -->

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 100 バイト | server | サーバー | "" |

サイトに同じコンテンツを提供する複数のドメインが存在する場合は、*`server`* 変数を使用して、訪問者が使用しているドメインを追跡できます。次の JavaScript は、ページのドメインを server 変数に入力します。

```js
s.server=window.location.hostname
```

server 変数を使用してロードバランシングの結果確認手段を提供する場合は、サーバーの名前または番号を server 変数に設定します。次の例を参照してください。

```js
s.server="server 14"
```

[!UICONTROL 最頻訪問サーバー]レポートはロードバランシングのクイック参照として使用できますが、サーバー負荷の正確な測定値を示すものではありません。例えば、「戻る」ボタントラフィックによってサーバー負荷は高くなりませんが、レポートには表示されます。また、どのサーバーが画像やサイズの大きいダウンロードを提供しているかはレポートでは示されません。

**構文と可能な値** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

標準の変数の制限以外、*`server`* 変数に対する制限はありません。

**例** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**設定** {#section_969DB379D5BD469FBEE8D505D3000E49}

なし

**注意事項、質問、ヒント** {#section_42A28F9B01574F38891D9D54B411D8FE}

*`server`* 変数を使用して、アクセスの最も多いドメインまたは最も多くページを提供しているサーバーを示すことができます。

