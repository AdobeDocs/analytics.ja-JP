---
description: pageName 変数は読みやすい、直観的なページ識別子で入力する必要があります。
keywords: Analytics の導入
seo-description: pageName 変数は読みやすい、直観的なページ識別子で入力する必要があります。
seo-title: ページネーミング戦略
solution: Analytics
title: ページネーミング戦略
topic: 開発者と導入
uuid: a829d0c7-6ebf-459a- b403-5e9c05161e5c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ページネーミング戦略

pageName 変数は読みやすい、直観的なページ識別子で入力する必要があります。

You can determine the best way of populating the *`pageName`* variable by looking at the structure of your website. The methods listed below outline various ways of populating the *`pageName`* variable.

While the *`pageName`* variable is central to identifying user behavior, Adobe recommends using multiple variables to indicate page information. 最も良いページ命名の戦略は、次に示すように、サイト内部のそれぞれの階層レベルに対して異なる変数を使用するものです。

* "*`channel`* 変数は、サイトセクションを示すために使用します。
* The *`pageName`* variable can be used to show content type.
* [!UICONTROL カスタムインサイト]変数（prop1）は、コンテンツの詳細説明に使用します。

次に示すように、詳細のレベルはプロパティに応じて異なります。

| 変数 | 詳細 のレベル | 例 |
|---|---|---|
| チャネル | 全般セクション | エレクトロニクス |
| Prop1 | サブセクション | スポーツ：ローカルスポーツ |
| PageName | 全般的内容説明 | ローン：住宅ローン：金利の比較 |
| Prop2 | 詳細な内容説明 | エレクトロニクス：ノート PC：詳細な仕様：IBM Thinkpad T20 |

サイトの層が詳細になればなるほど、ページのコンテンツを確認するためにより多くの変数を使用する必要があります。変数間での重複を許可する値もあります。例えば、詳細な変数には表示されている製品に関する情報だけではなく、サイトセクションとサブセクションに関する情報も含めることができます。これは、製品や記事がサイトの複数のセクションに表示されるときに特に役立ちます。

次のページ命名戦略で、*`pageName`* 変数を使用します。最も導入が容易なページ命名戦略を選択しがちですが、ページ命名戦略により、すべての[!UICONTROL パス]レポートと[!UICONTROL ページ]レポートの使い勝手が大きく左右されます。ページの名前を決める際は適切な判断を下してください。

## 各ページに固有な名前 {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

ページに名前を付ける上で最も役に立つ方式は、各ページに社内のすべての [!DNL Analytics] ユーザーが理解しやすい固有の識別子を提供することです。ページ名の例としては、「ホームページ」、「エレクトロニクス部門のホーム」、「スポーツ：ローカルスポーツ：高校」などがあります。

ほとんどの [!DNL Analytics] ユーザーにとっては、ページがサイトで見つかる場所およびページの目的を識別する上で階層的なページ名が役立ちます。次の表は、様々な産業のサンプルページ名を示しています。

| コンバージョン | メディア | ファイナンス |
|---|---|---|
| ホームページ | ホームページ | ホームページ |
| エレクトロニクス | 技術 | 住宅ローン |
| エレクトロニクス：ノート PC | 技術：新型機器 | 住宅ローン：金利の比較 |
| エレクトロニクス：ノート PC：製品ページ | 技術：新型機器：記事ページ | 住宅ローン：金利の比較：10 年固定 |

## ファイルパス（完全修飾 URL ではない） {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

一部のサイトでは、ファイルパスが明瞭で読みやすくなっています。ビジネスユーザーは URL を読んでファイルパスが参照するページを判断することができます。このようなサイトの場合、次のように、サーバーサイドの変数を使用して *`pageName`*&#x200B;変数にファイルへのパスを入力することができます。

```js
s.pageName="<%= file_path %>"
```

*`pageName`* 空白のままにしておくことはお勧めしません（ページの完全修飾URLを使用することになります）。The following side-effects are caused by leaving the *`pageName`* variable blank and using the *`pageURL`* as the page identifier.

* ページのドメインとパスが同じように表示されないことがあります。例えば、以下の 4 つの URL は単一ページを返します。

   * `https://www.mysite.com/index.jsp`
   * `https://www.mysite.com`
   * `https://mysite.com/index.jsp`
   * `https://mysite.com/`
   If the *`pageName`* is left blank, each of these page names would occupy a separate entry in reports.

* 一部のページ（フォームなど）はそれ自体のページに配置されるので、元のフォームと結果として生じる出力の間の区別が消去されます。
* ページが検索エンジンや他のオンラインツールにより別の言語に翻訳されるとき、ページの URL はサイトの URL ではなく、検索エンジンの URL になります。

## HTML（document.title） {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

If you have invested time into making your HTML titles readable and intuitive, you might consider using the same title as the value in the *`pageName`* variable. Adobe recommends using a server-side variable to populate the *`pageName`* rather than using JavaScript's [!DNL document.title]. 一部のブラウザーでは、HTML タイトルが他のブラウザーとは異なる方法で解釈されます。したがって、[!DNL Analytics] がブラウザーから受け取るページ名はブラウザーごとに異なる場合があります。

HTML タイトルを使用する一番良い方法は、各ページの既存のタイトルを個別の変数またはコンテンツ管理要素にコピーすることです。検索エンジンの最適化またはその他の目的で HTML タイトルを変更しても、[!DNL Analytics] ページ名は影響を受けません。ページ名が [!DNL Analytics] 内で変更されると、そのページは新しいページになり、関連する URL とは関係なく、古いページ名には関連付けられません。
