---
description: 処理ルールはデータ収集をシンプル化し、レポーティングに送信されるコンテンツを管理します。
subtopic: Processing rules
title: 処理ルールの概要
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 97%

---

# 処理ルールの概要

処理ルールはデータ収集をシンプル化し、レポーティングに送信されるコンテンツを管理します。処理ルールは、以下に対するインターフェイスを提供することにより、IT グループおよび Web 開発者とのやり取りの単純化に役立ちます。

* 製品の概要ページでイベントを設定する
* クエリ文字列パラメーターでキャンペーンを入力する
* レポートを容易にするために、prop でカテゴリとページ名を連結する
* eVar を prop にコピーし、パスを確認する
* スペルを間違えたサイトセクションのクリーンアップ
* クエリ文字列から eVar に内部検索用語またはキャンペーン ID を取り込む



>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ 処理ルールの概要 ](https://video.tv.adobe.com/v/327637/?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## 処理ルールの権限 {#section_8A4846688050453784DAE4D89355169A}

管理者には、処理ルールを使用する権限が&#x200B;**デフォルトで**&#x200B;与えられています。また、管理者は、管理ツールインターフェイスを使用してこの権限を管理者以外のユーザーに付与することもできます。手順については、[]を参照してください

![処理ルール](assets/processing-rules.png)

## コンテキストデータを使用したデータ収集の単純化 {#section_09EEA03612D24C15839631AA9E9668D8}

コンテキストデータ変数は、処理ルールにのみ使用できるタイプの変数です。コンテキストデータを使用するには、キー／値データペアを送信し、処理ルールを使用して標準的な Analytics 変数にこれらの値を取り込みます。これによって、プログラマーは prop や eVar に含めるべき値を正確に理解する必要がなくなります。

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

コード内で設定すると、変数に値を割り当てるための処理ルールを設定できます。次に例を示します。

1. `author` を `eVar2` にマッピングします
2. `section` を `prop1` と `eVar3` にマッピングします
3. `author` と `section` が存在する場合は、`event5` を設定します

詳しくは、実装ユーザーガイドの [contextData](/help/implement/vars/page-vars/contextdata.md) を参照してください。

## 処理ルールを使用したヒットデータの変換とイベントのトリガー {#section_8284E72E999244E091CD7FB1A22342B6}

処理ルールでは、受け入れる値を監視し、よくある入力ミスを変換したり、レポートされたデータに基づいてイベントを設定したりできます。prop は eVar にコピーでき、レポートで値を連結でき、イベントを設定できます。

## レポートでのコンテキストデータ変数の使用 {#section_BD098BC503024A0B8703596628071134}

定義したコンテキストデータ変数をレポートで使用するには、eVar などの変数にコピーする必要があります。

詳しくは、[コンテキストデータ変数の eVar へのコピー](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)および[コンテキストデータ変数を使用したイベントの設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)を参照してください。

## 既知の制限事項

**処理ルールでキャレット（^）を使用します。**&#x200B;処理ルールでキャレットを区切り文字または他の目的で使用したい場合、各単一のキャレットは、2 つのキャレットで表される必要があります。例えば、単一のキャレットを ^^ で表し、二重キャレットを ^^^^ で表します。