---
description: データフィードで使用される特殊文字に関する情報です。
keywords: データフィード;job;特殊文字;hit_ data;複数値の変数;events_ list;products_ list;mvvars
seo-description: データフィードで使用される特殊文字に関する情報です。
seo-title: 特殊文字
solution: Analytics
subtopic: データフィード
title: 特殊文字
topic: Reports and Analytics
uuid: 5ee019b-39e6-4226- a936-88202a02f5e6
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 特殊文字

データフィードで使用される特殊文字に関する情報です。

* [hit_data ファイル内の特殊文字](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_9759C7A6AE684EB5B4A154FB6A26B39E)
* [複数値の変数（events_list、products_list、mvvars）内の特殊文字](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_056F8D540FFC4F24A001DC74331C2AAC)
* [サンプルワークフロー](../../../export/analytics-data-feed/c-df-contents/datafeeds-spec-chars.md#section_97F8C2925A35433DA2E7E8BE60037E37)

## hit_data ファイル内の特殊文字 {#section_9759C7A6AE684EB5B4A154FB6A26B39E}

以下の文字は、hit_data ファイル内で特別な意味を持ちます。

| 文字 | 意味 | 説明 |
|--- |--- |--- |
| \t（タブ文字） | 列の終わり | データフィールドの終わりにマークを付けます。 |
| \n（改行文字） | 行の終わり | データの終わりにマークを付けます。 |
| \（バックスラッシュ文字） | エスケープ文字 | データ収集時に送信された値にタブ、改行、およびバックスラッシュが含まれていた場合、これらの文字をエスケープします。 |

すべての特殊文字はその前にバックスラッシュを付けると、リテラル文字を表します。

| 文字 | 意味 | 説明 |
|--- |--- |--- |
| \\t | タブ | タブのリテラル文字。データ収集時に送信された値にこの文字が含まれていました。 |
| \\n | 改行 | リテラルの改行。データ収集時に送信された値にこの文字が含まれていました。 |
| \\ | バックスラッシュ | バックスラッシュのリテラル文字。データ収集時に送信された値にこの文字が含まれていました。 |

## 複数値の変数（events_list、products_list、mvvars）内の特殊文字 {#section_056F8D540FFC4F24A001DC74331C2AAC}

以下の文字は、複数値の変数内で特別な意味を持ちます。

<table id="table_FDA13DE05A784ED4972C2955BD2642C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 文字 </th> 
   <th colname="col02" class="entry"> 意味 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code>,</code>（コンマ文字） </td> 
   <td colname="col02"> 値の終わり </td> 
   <td colname="col2"> <p>複数値の変数内にある製品文字列、イベント ID などの値を分離します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>;</code>（セミコロン文字） </td> 
   <td colname="col02"> 個々の製品の値内にある副値の終わり </td> 
   <td colname="col2"> <p><code>product_list</code> 内にある個々の製品に関連する値を分離します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>=</code>（等号文字） </td> 
   <td colname="col02"> 値の割り当て </td> 
   <td colname="col2"> <p><code>event_list</code> 内のイベントに値を割り当てます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

すべての特殊文字はその前にキャレットを付けると、リテラル文字を表します。

| 文字 | 意味 | 説明 |
|--- |--- |--- |
| ^, | コンマ | コンマのリテラル文字。データ収集時に送信された値にこの文字が含まれていました。 |
| ^; | セミコロン | セミコロンのリテラル文字。データ収集時に送信された値にこの文字が含まれていました。 |
| ^= | 等号 | 等号のリテラル文字。データ収集時に送信された値にこの文字が含まれていました。 |
| ^^ | キャレット | キャレットのリテラル文字。データ収集時に送信された値にこの文字が含まれていました。 |

## サンプルワークフロー {#section_97F8C2925A35433DA2E7E8BE60037E37}

データフィード内の一部の列にユーザーが送信したデータが格納されている場合、`split` や `readLine` などを使用して列または行ごとにデータを分離する前に、特殊文字がないかチェックする必要があります。

次のデータをご覧ください。

| ブラウザーの幅 | ブラウザーの高さ | eVar1 | prop1 |
|---|---|---|---|
| 1680 | 1050 | search\nstring | en |
| 800 | 600 | search\nstring | en |

 エクスポートの際、eVar1 内の改行およびタブ文字はエスケープされます。これらの行のデータフィードは次のようになります。

```
1680\t1050\tsearch\\nstring\ten\n 
800\t600\tsearch\\tstring\ten\n
```

Calling `readLine()` on the first row returns the following partial string:

```
800\t600\tsearch\
```

Calling `split("\t")` on the second row returns the following string array:

```
800 
600 
search\ 
string 
en
```

これを回避するには、次のような解決策を使用します。

1. ファイルの先頭から読み取りを開始し、タブ、改行、バックスラッシュ、またはキャレット文字が見つかるまで読み取りを行います。
1. 見つかった特殊文字に基づいてアクションを実行します。

   * タブ - そこまでの文字列を新しいデータストアセル内に挿入して処理を続行します。
   * 改行 - データストア行を完結させます。
   * バックスラッシュ - 次の文字を読み取り、適切な文字列リテラルを挿入して処理を続行します。
   * キャレット - 次の文字を読み取り、適切な文字列リテラルを挿入して処理を続行します。

