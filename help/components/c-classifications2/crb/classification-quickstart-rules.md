---
description: 分類ルールでは、分類されていない用語が定期的に検索されます。 ルールの一致が見つかった場合、ルールによって分類データテーブルにキーワードが自動的に追加されます。 また、分類ルールを使用して既存のキーを上書きすることもできます。
subtopic: Classifications
title: 分類ルール
topic: Admin tools
uuid: 08685919-216d-448b-b886-3adf5ff5405e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 分類ルール

分類ルールでは、分類されていない用語が定期的に検索されます。 ルールの一致が見つかった場合、ルールによって分類データテーブルにキーワードが自動的に追加されます。 また、分類ルールを使用して既存のキーを上書きすることもできます。

**[!UICONTROL Analytics]**／**[!UICONTROL Admin]**／**[!UICONTROL Classification Rule Builder]**

ルールビルダーを使用すると、*`classification rule set`*（*`classification rules`* のリスト）を作成できます。ルールは、指定した条件に一致し、アクションを実行します。

分類ルールは次の用途に便利です。

* **Email** and **Display ads**:分類ルールを作成して、個々のディスプレイ広告キャンペーンをグループ化し、電子メールキャンペーンに対する表示キャンペーンのパフォーマンスを取得します。

* **追跡コード**:トラッキングコードの文字列から派生したキー値を分類し、定義した特定の条件に一致させる分類ルールを作成します。
* **検索語句**:正規の [式](/help/components/c-classifications2/crb/classification-quickstart-rules.md) 、ワイルドカードを使用して、検索用語の分類を簡単にします。 例えば、検索用語に *`baseball`* が含まれる場合、*`Sports League`* 分類を「*`MLB`*」に設定できます。

例えば、電子メールキャンペーン ID が次のトラッキングコードを持つとします。

`em:Summer:2013:Sale` を参照してください。

ここで、文字列の一部を識別する 3 つのルールをルールセットに設定し、値を分類することができます。

| ルールタイプを選択 | 一致条件を入力 | 分類を設定 | 設定値 |
|---|---|---|---|
| 次の語句で始まる | em: | Channel | 電子メール |
| 次の語句で終わる | 販売 | タイプ | 販売 |
| Contains | 2013 | 年 | 2013 |

## ルールの処理方法 {#how-rules-are-processed}

分類ルールの処理方法に関する重要な情報です。

<!-- 

about_classification_rules.xml

 -->

* [ルールに関する重要な情報](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [ルールでキーが分類されないのはいつですか。](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [ルールの優先度について](/help/components/c-classifications2/crb/classification-quickstart-rules.md)

>[!NOTE] は数値2 [!UICONTROL Rule Builder] 分類をサポートしていません。

## ルールに関する重要な情報

* で分類の [グループ権限](https://marketing.adobe.com/resources/help/ja_JP/reference/groups.html) を指定しま [!UICONTROL Admin Tools]す。

* **正規表現**:[分類ルールの正規表現](/help/components/c-classifications2/crb/classification-quickstart-rules.md)でヘルプを利用できます。

* **レポートスイート**:1つ以上のレポートスイートが選択されるまで、分類を選択することはできません。 ルールセットを作成し、変数を割り当てるまで、レポートスイートを適用できません。

   ルールセットをテストする際は、レポートのキー（分類する変数）を使用して、ルールセットがどのように影響を与えるかを確認します。 (The [key](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) is the variable being classified, or the first column in the classification upload table.)

* **ルールの優先**:キーが（列内で）同じ分類を設定する複数のルールに一致する場合は、そ [!UICONTROL Set Classification] の分類に一致する最後のルールが使用されます。 See [About Rule Priority](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

* **ルール数の制限**:作成できるルールの数に制限はありません。 ただし、多数のルールがブラウザーのパフォーマンスに影響を与える可能性があります。
* **処理**:ルールは、分類関連のトラフィックの量に応じて、頻繁に処理されます。

   アクティブなルールは4時間ごとに処理され、通常は1か月前に分類データを調べます。 ルールは、新しい値を自動的に確認し、インポーターを使用して分類をアップロードします。

* **既存の分類の上書き**：詳しくは、[ルールによるキーの分類が行われない状況を参照してください。](/help/components/c-classifications2/crb/classification-quickstart-rules.md)必要に応じて、インポーターを使用して既存の分類を削除できます。

## ルールでキーが分類されないのはいつですか。

ルールをアクティブ化すると、既存の分類を上書きできます。 次の場合、分類ルールはキー [](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)（変数）を分類しません。

* キーは既に分類されており、「分類を上書き」を選択 [していません](/help/components/c-classifications2/crb/classification-rule-definitions.md)。

   ルールの追加とアクティブ化を行う [ときや](/help/components/c-classifications2/crb/classification-quickstart-rules.md) 、Data Connectors統合をアクティブ化するときに、分類を上書きできます。 (For data connectors, rules are created by partners in the Dev Center and displayed in the [!UICONTROL Classification Rule Builder].)

* 「分類を上書き」を有効にした後でも、キーを上書きする際に指定した時間枠の後に分類されたキーがデータに表示さ [れません](/help/components/c-classifications2/crb/classification-rule-definitions.md)。
* キーが分類されず、約 1 ヶ月前から始まる時間枠が経過した後もキーが [!DNL Adobe Analytics] に渡されない。

   >[!NOTE]
   >
   >レポートでは、分類は、キーが存在するかどうかに関係なく、指定されたすべての時間枠に適用されます。レポートの日付範囲はレポートに影響しません。

![](assets/overwrite_keys.png)

## 分類ルールの正規表現 {#regex-in-classification-rules}

正規式を使用して、一貫した形式の文字列値を分類と一致させます。 例えば、トラッキングコードの特定の文字から分類を作成できます。特定の文字、単語または文字のパターンを一致させることができます。

<!-- 

regex_classification_rules.xml

 -->

* [正規表現 - トラッキングコードの例](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_2EF7951398EB4C2F8E52CEFAB4032669)
* [正規式 — 特定の文字の分類](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_5D300C03FA484BADACBFCA983E738ACF)
* [正規表現 - 様々な長さのトラッキングコードの一致](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2)
* [正規表現 - 「含まない」の例](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_FCA88A612A4E4B099458E3EF7B60B59C)
* [正規表現 - 参照テーブル](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716)

>[!NOTE]ベストプラクティスとして、正規表現は、区切り文字を使用するトラッキングコードに最も適しています。

## 正規表現 - トラッキングコードの例 {#section_2EF7951398EB4C2F8E52CEFAB4032669}

>[!NOTE]トラッキングコードが URL エンコードされている場合は、ルールビルダーで分類&#x200B;**されません**。

この例では、次のキャンペーン ID を分類することを前提とします。

[!UICONTROL Sample Key]: `em:JuneSale:20130601`

分類するトラッキングコードの一部：

* `em` = 電子メール
* `JuneSale` = キャンペーン名
* `20130601` = 日付

[!UICONTROL Regular Expression]: `^(.+)\:(.+)\:(.+)$`

正規式とキャンペーンIDとの関連：

![](assets/regex.png)

[!UICONTROL Match Groups]:正規式がキャンペーンID文字にどのように対応し、キャンペーンID内の位置を分類できるかを示します。

![](assets/regex_tracking_code.png)

この例が示しているルールでは、キャンペーンの日付 `20140601` は `$3` で識別された 3 番目のグループ `(.+)` にあります。

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| ルールタイプを選択 | 一致条件を入力 | 分類を設定 | 設定値 |
|---|---|---|---|
| 正規表現 | &amp;Hat;(.+)\:(.+)\:(.+)$ | キャンペーン日 | $3 |

**構文**

| 正規表現 | 文字列または一致結果 | 対応する一致グループ |
|--- |--- |--- |
| `^(.+)\:(.+)\:(.+)$` | em:JuneSale:20130601 | `$0`: em:JuneSale:20130601  `$1`: em  `$2`: JuneSale  `$3`: 20130601 |
| 構文の構築 | `^`= 行の先頭 () = 文字をグループ化し、括弧内の一致する文字を抽出します。`(.+)` = 1 ( .) 文字と ( + ) 任意の  \ = 文字列の先頭。`$` = 前の文字（または文字グループ）が行の末尾であることを示しています。 |

正規 [式の文字の意味については](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716) 、正規式 — 参照表を参照。

## 正規式 — 特定の文字の分類 {#section_5D300C03FA484BADACBFCA983E738ACF}

正規式の1つの使用方法は、文字列内の特定の文字を分類することです。 例えば、次のトラッキングコードに2つの重要な文字が含まれているとします。

[!UICONTROL Sample Key]: `4s3234`

* `4` = ブランド名
* `s` = Google などの検索エンジンを識別する

![](assets/regex_char_position.png)

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| ルールタイプを選択 | 一致条件を入力 | 分類を設定 | 設定値 |
|--- |--- |--- |--- |
| 正規表現 | `^.(s).*$` | ブランドおよびエンジン | `$0`（ブランド名および検索エンジンの最初の 2 文字をキャプチャします。） |
| 正規表現 | `^.(s).*$` | 検索エンジン | `$1`（Google の 2 番目の文字をキャプチャします。） |

## 正規表現 - 様々な長さのトラッキングコードの一致 {#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2}

この例では、様々な長さのトラッキングコードがある場合に、コロン区切り文字の間の特定の文字を識別する方法を示します。 各トラッキングコードに1つの正規式を使用することをお勧めします。

サンプルキー:

* `a:b`
* `a:b:c`
* `a:b:c:d`

**構文**

![](assets/regex_b.png)

![](assets/regex_varying_length.png)

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| ルールタイプを選択 | 一致条件を入力 | 分類を設定 | 設定値 |
|--- |--- |--- |--- |
| 一致文字列 a:b の正規表現 | `^([^\:]+)\:([^\:]+)$` | a | `$1` |
| 一致文字列 a:b の正規表現 | `^([^\:]+)\:([^\:]+)$` | b | `$2` |
| 一致文字列 a:b:c の正規表現 | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | a | `$1` |
| 一致文字列 a:b:c の正規表現 | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | b | `$2` |
| 一致文字列 a:b:c の正規表現 | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | c | `$3` |
| 一致文字列 a:b:c:d の正規表現 | `^([^\:]+)\:([^\:]+)\:([^\:]+)\:([^\:])$` | d | `$4` |

## 正規表現 - 「含まない」の例 {#section_FCA88A612A4E4B099458E3EF7B60B59C}

この例では、特定の文字を含まないすべての文字列を一致させる正規表現を提供します。ここでは `13` です。

正規表現：

`^(?!.*13.*).*$`

テスト文字列：

```
a:b:
a:b:1313
c:d:xoxo
c:d:yoyo
```

一致結果：

```
a:b:
c:d:xoxo
c:d:yoyo
```

この例では、`a:b:1313` は一致を示していません。

## 正規表現 - 参照テーブル {#section_0211DCB1760042099CCD3ED7A665D716}

| 式 | 説明 |
|---|---|
| `(?ms)` | 正規表現全体を複数行の入力と照合し、任意の改行文字に一致するワイルドカード |
| （`?i`） | 正規表現全体で大文字と小文字を区別しないようにする |
| [`abc`] | a、b または c の 1 文字 |
| [`^abc`] | a、b、c 以外の 1 文字 |
| [`a-z`] | a ～ z の範囲内の 1 文字 |
| [`a-zA-Z`] | a ～ z または A ～ Z の範囲内の 1 文字 |
| `^` | 行の開始（行の開始に一致） |
| `$` | 行の末尾（または末尾の新しい行の前に一致） |
| `\A` | 文字列の開始 |
| `\z` | 文字列の末尾 |
| `.` | 任意の文字の一致（改行を除く） |
| `\s` | 空白文字 |
| `\S` | 空白以外の文字 |
| `\d` | 数字 |
| `\D` | 数字以外 |
| `\w` | 任意の単語（文字、数字、アンダースコア） |
| `\W` | 任意の単語以外の文字 |
| `\b` | 任意の単語境界 |
| `(...)` | 囲まれている内容をすべてキャプチャ |
| `(a|b)` | a または b |
| `a?` | 0 または 1 個の a |
| `a*` | 0 個以上の a |
| `a+` | 1 つ以上の a |
| `a{3}` | 3 個の a |
| `a{3,}` | 3 個以上の a |
| `a{3,6}` | 3 ～ 6 個の a |

正規表現の有効性のテストに関する参考資料については、https://rubular.com/ を参照してください。

## ルールの優先度について

キーが複数のルールに一致し、列に表示される同じ分類列を設定する場合は、最 [!UICONTROL Set Classification] 後のルールが使用されます。 したがって、ルールセット内で最も重要な最後のルールをランク付けする必要がある場合があります。

<!-- 

rule_priority.xml

 -->

同じ分類を共有しない複数のルールを作成する場合、処理順序は問題になりません。

以下に示すのは、アスリートの検索タイプを分類する検索語ルールの例です。

| ルール番号 | ルールタイプ | フィルター適用条件 | 分類を設定 | 設定値 |
|---|---|---|---|---|
| 1 | Contains | カウボーイズ | 検索タイプ | チーム |
| 2 | Contains | ファンタジー | 検索タイプ | ファンタジー |
| 3 | Contains | ロモ | 検索タイプ | プレイヤー |

If a user searches for *`Cowboys fantasy Tony Romo`*, the term *`Player`* is classified, because it matches the last given classification shown in the Set Classification column.

同様に、次の検索用語の2つのルールを1つのセットに設定したとします。

| ルール番号 | ルールタイプ | フィルター適用条件 | 分類を設定 | 設定値 |
|---|---|---|---|---|
| 1 | Contains | カウボーイズ | 市区町村 | ダラス |
| 2 | Contains | ブロンコス | 市区町村 | デンバー |

ユーザーが&#x200B;*`Cowboys vs. Broncos`* を検索すると、ルールビルダーによってルールの一致に競合が発見され、この検索では 2 番目のルールの分類（Denver）が適用されます。

## ルールセットに対する分類ルールの追加 {#add-classification-to-rule-set}

<!-- 

t_classification_rule.xml

 -->

分類ルールを追加または編集する手順を説明します。

ルー追加ルを作成する必要があります。

>[!NOTE]
>
>この手順では、ルールを 1 つ以上のレポートスイートに適用する必要があります。ルールセット1つあたりのルールの数は500 ～ 1000の範囲で推奨されますが、制限はありません。 100を超えるルールがある場合は、下位分類を使用してルールセットを簡略化するこ [とを検討します](/help/components/c-classifications2/c-sub-classifications.md)。

1. [分類ルールセットを作成します](/help/components/c-classifications2/crb/classification-rule-set.md)。
1. On the rule set page, click **[!UICONTROL Add Rule]**.

   ![](assets/add_rule.png)

1. Next to **[!UICONTROL Report Suites]**, click **[!UICONTROL Add Suites]** to specify one or more report suites to assign to this rule set.

   ページが **[!UICONTROL Select Report Suites]** 表示されます。

   >[!NOTE]
   レポートスイートは、次の条件を満たした場合 *`only`* このページに表示されます。

   * レポートスイートには、その変数に対して1つ以上の分類が定義されていま [!UICONTROL Admin Tools]す。
   (See *`Variable`* in [Classification Rule Sets](/help/components/c-classifications2/crb/classification-rule-set.md) for an explanation about this prerequisite.)

   * You selected the report suite on the **[!UICONTROL Available Report Suites]** page, which displays after you click [Add Rule Set](/help/components/c-classifications2/crb/classification-rule-set.md) to create the rule set.


1. 既存の値を上書きするかどうかを指定します。

   | **ルールによって既存の値は上書きされます** | （デフォルト設定）インポーター(SAINT)を介してアップロードされた分類を含む、既存の分類キーを常に上書きします。 |
   |---|---|
   | **ルールによって未設定の値のみが上書きされます** | 空白（未設定）のセルのみを入力します。 既存の分類は変更されません。 |

1. [ルールを定義します](/help/components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529)。

   ![手順の結果](assets/classification_rules_page.png)

   ルールの作成例については、「[分類ルールビルダー](/help/components/c-classifications2/crb/classification-rule-builder.md)」および「[分類ルールの正規表現](/help/components/c-classifications2/crb/classification-quickstart-rules.md)」を参照してください。

   >[!NOTE]
   >
   >（分類を設定列で）同じ分類が設定されているルールが複数あり、それにキーが合致した場合には、分類に合致した最後のルールが使用されます。ルールの並べ替えの詳細については、**ルールの優先度について**&#x200B;を参照してください。

1. [ルールセットをテストします](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。
1. After testing, click **[!UICONTROL Active]** to validate and activate the rule.

   ルールをアクティブ化すると、自動的にファイルが構築され、アップロードされます。

   フィールド定義：このページのインターフェイスオプションの完全な定義については、[分類ルールビルダー](/help/components/c-classifications2/crb/classification-rule-definitions.md)を参照してください。

## 分類ルールセットのテスト

<!-- 

t_classifications_test_rule.xml

 -->

分類ルールまたはルールセットをテストする手順を説明します。 テストを実行すると、セット内のすべてのルールがチェックされます。

1. [分類ルールセットを作成します](/help/components/c-classifications2/crb/classification-rule-set.md)。
1. で、ルー [!UICONTROL Classification Rule Builder]ルセット名をクリックします。
1. ルールセットがレポートスイートに関連付けられていることを確認します。
1. On the rule editor, click **[!UICONTROL Test Rule Set]**.

   ![手順の結果](assets/classification_test_rule_set.png)

1. Type or paste test keys in the [!UICONTROL Sample Keys] field.

   サンプルキーには以下が含まれます。

   * トラッキングコード
   * 検索キーワードまたは語句
   See [Regular Expressions in Classification Rules](/help/components/c-classifications2/crb/classification-quickstart-rules.md) for information about testing regular expressions.
1. クリック **[!UICONTROL Run Test]**.

   Rules that match are displayed in the [!UICONTROL Results] table.
1. (Optional) Click **[!UICONTROL Activate]** to activate the rule, and to overwrite existing classifications.

   ルールを使用して既存の分類を上書きする方法の詳細を参照してください。

## 分類ルールの検証とアクティブ化

<!-- 

t_validate_rules.xml

 -->

分類ルールを検証およびアクティブ化する方法について手順を説明します。

1. [分類ルールセットを作成](/help/components/c-classifications2/crb/classification-rule-set.md)してから、セットに[分類ルールを追加](/help/components/c-classifications2/crb/classification-quickstart-rules.md)します。
1. On the rule editor, click **[!UICONTROL Activate]**.

   ![](assets/overwrite_keys.png)

1. （オプション）分類を上書きするには、を有効にしま **[!UICONTROL Overwrite classifications for]***`<selection>`*&#x200B;す。

   このオプションを使用すると、影響を受けるキーの既存の分類を上書きできます。

   このオプ [ションの定義については](/help/components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529) 、「ルールページ」を参照してください。
