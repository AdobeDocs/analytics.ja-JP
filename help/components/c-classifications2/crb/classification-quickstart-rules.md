---
description: 分類ルールを設定すると、分類されていない語句が定期的に検索されます。ルールとの一致が検出されると、ルールによってその語句が分類データテーブルに自動的に追加されます。分類ルールを使用して既存のキーを上書きすることもできます。
subtopic: Classifications
title: 分類ルール
topic: Admin tools
uuid: 08685919-216d-448b-b886-3adf5ff5405e
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 分類ルール

分類ルールを設定すると、分類されていない語句が定期的に検索されます。ルールとの一致が検出されると、ルールによってその語句が分類データテーブルに自動的に追加されます。分類ルールを使用して既存のキーを上書きすることもできます。

**[!UICONTROL Analytics]**／**[!UICONTROL Admin]**／**[!UICONTROL Classification Rule Builder]**

ルールビルダーを使用すると、*`classification rule set`*（*`classification rules`* のリスト）を作成できます。ルールは、指定された条件との照合を行い、アクションを実行します。

分類ルールは、次の項目に使用すると便利です。

* **電子メール**&#x200B;および&#x200B;**ディスプレイ広告**：電子メールキャンペーンと比較したディスプレイ広告キャンペーンのパフォーマンスを確認するために、個々のディスプレイ広告キャンペーンをグループ化する分類ルールを作成できます。

* **トラッキングコード**：トラッキングコードの文字列から派生するキー値を分類するための分類ルールを作成し、定義した特定の条件と照合します。
* **検索用語**：[正規表現](/help/components/c-classifications2/crb/classification-quickstart-rules.md)とワイルドカードを使用して、検索用語の分類を簡略化できます。例えば、検索用語に *`baseball`* が含まれる場合、*`Sports League`* 分類を「*`MLB`*」に設定できます。

例えば、電子メールキャンペーン ID が次のトラッキングコードを持つとします。

`em:Summer:2013:Sale` を参照してください。

ここで、文字列の一部を識別する 3 つのルールをルールセットに設定し、値を分類することができます。

| ルールタイプを選択 | 一致条件を入力 | 分類を設定 | 設定値 |
|---|---|---|---|
| 次の語句で始まる | em: | Channel | 電子メール |
| 次の語句で終わる | Sale | タイプ | Sale |
| Contains | 2013 | 年 | 2013 |

## ルールの処理方法 {#how-rules-are-processed}

分類ルールの処理方法に関する重要な情報。

<!-- 

about_classification_rules.xml

 -->

* [ルールに関する重要な情報](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [ルールによるキーの分類が行われない状況](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [ルールの優先度について](/help/components/c-classifications2/crb/classification-quickstart-rules.md)

>[!NOTE] は数値2 [!UICONTROL Rule Builder] 分類をサポートしていません。

## ルールに関する重要な情報

*     の分類 [のグループ権限](https://docs.adobe.com/content/help/ja-JP/analytics/admin/user-product-management/user-groups/groups.html)[!UICONTROL Admin Tools]。

* **正規表現**:[分類ルールの正規表現](/help/components/c-classifications2/crb/classification-quickstart-rules.md)でヘルプを利用できます。

* **レポートスイート**：分類を選択するには、1 つ以上のレポートスイートが選択されている必要があります。レポートスイートは、ルールセットが作成され変数が割り当てられていないと、適用できません。

   ルールセットをテストするときは、レポートのキー（分類する変数）を使用して、ルールセットによる影響を確認します（[キー](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)は、分類する変数、または分類アップロードテーブルの最初の列です）。

* **ルールの優先**:キーが（列内で）同じ分類を設定する複数のルールに一致する場合は、そ [!UICONTROL Set Classification] の分類に一致する最後のルールが使用されます。 See [About Rule Priority](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

* **ルールの数に関する制限**：作成できるルールの数に制限はありません。ただし、大量にルールを作成すると、ブラウザーのパフォーマンスに影響が及ぶことがあります。
* **処理**：ルールは、分類に関連するトラフィックのボリュームに応じた頻度で処理されます。

   アクティブなルールは 4 時間ごとに処理され、通常、分類データの調査は月に 1 回行われます。ルールでは、自動的に新しい値がチェックされ、インポーターを使用して分類がアップロードされます。

* **既存の分類の上書き**：詳しくは、[ルールによるキーの分類が行われない状況を参照してください。](/help/components/c-classifications2/crb/classification-quickstart-rules.md)必要に応じて、インポーターを使用して既存の分類を削除できます。

## ルールによるキーの分類が行われない状況

ルールをアクティブにするとき、既存の分類を上書きできます。次の場合、分類ルールによる[キー](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)（変数）の分類は行われません。

* キーが既に分類済みで、「[分類を上書き](/help/components/c-classifications2/crb/classification-rule-definitions.md)」を選択していない。

   分類の上書きは、[ルールを追加およびアクティブ化する](/help/components/c-classifications2/crb/classification-quickstart-rules.md)ときと、データコネクタの統合をアクティブ化するときに行うことができます(For data connectors, rules are created by partners in the Dev Center and displayed in the [!UICONTROL Classification Rule Builder].)

* 「[分類を上書き](/help/components/c-classifications2/crb/classification-rule-definitions.md)」を有効にした後であっても、キーを上書きするときに指定された時間枠が経過した後、分類されたキーがデータに表示されていない。
* キーが分類されず、約 1 ヶ月前から始まる時間枠が経過した後もキーが [!DNL Adobe Analytics] に渡されない。

   >[!NOTE]
   >
   >レポートでは、分類は、キーが存在するかどうかに関係なく、指定されたすべての時間枠に適用されます。レポートの日付範囲はレポートに影響しません。

![](assets/overwrite_keys.png)

## 分類ルールの正規表現 {#regex-in-classification-rules}

正規表現を使用すると、一貫した形式の文字列値を分類に一致させることができます。例えば、トラッキングコードの特定の文字から分類を作成できます。特定の文字、単語または文字パターンを一致させることができます。

<!-- 

regex_classification_rules.xml

 -->

* [正規表現 - トラッキングコードの例](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_2EF7951398EB4C2F8E52CEFAB4032669)
* [正規表現 - 特定の文字の分類](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_5D300C03FA484BADACBFCA983E738ACF)
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

正規表現とキャンペーン ID の相関関係：

![](assets/regex.png)

[!UICONTROL Match Groups]:正規式がキャンペーンID文字にどのように対応し、キャンペーンID内の位置を分類できるかを示します。

![](assets/regex_tracking_code.png)

この例が示しているルールでは、キャンペーンの日付 `20140601` は `$3` で識別された 3 番目のグループ `(.+)` にあります。

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| ルールタイプを選択 | 一致条件を入力 | 分類を設定 | 設定値 |
|---|---|---|---|
| 正規表現 | &amp;Hat;(.+)\:(.+)\:(.+)$ | キャンペーンの日付 | $3 |

**構文**

| 正規表現 | 文字列または一致結果 | 対応する一致グループ |
|--- |--- |--- |
| `^(.+)\:(.+)\:(.+)$` | em:JuneSale:20130601 | `$0`: em:JuneSale:20130601  `$1`: em  `$2`: JuneSale  `$3`: 20130601 |
| 構文の構築 | `^`= 行の先頭 () = 文字をグループ化し、括弧内の一致する文字を抽出します。`(.+)` = 1 ( .) 文字と ( + ) 任意の  \ = 文字列の先頭。`$` = 前の文字（または文字グループ）が行の末尾であることを示しています。 |

正規表現の文字が何を意味しているかについては、[正規表現 - 参照表](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716)を参照してください。

## 正規表現 - 特定の文字の分類 {#section_5D300C03FA484BADACBFCA983E738ACF}

正規表現を使用する 1 つの方法は、文字を含む文字列内の特定の文字を分類することです。例えば、次のトラッキングコードに 2 つの重要な文字が含まれているとします。

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

この例では、様々な長さのトラッキングコードがある場合に、コロン区切りの間の特定の文字を識別する方法を示しています。Adobe では、各トラッキングコードに 1 つの正規表現を使用することをお勧めします。

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
| `(?ms)` | 正規表現全体を複数行の入力と照合し、ワイルドカードがあらゆる改行文字と一致できるようにする |
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

If a key is matched to multiple rules, and it sets the same classification column shown in the [!UICONTROL Set Classification] column, the last rule is used. したがって、ルールセット内の最後のルールが最も重要になります。

<!-- 

rule_priority.xml

 -->

分類が同じでないルールを複数作成している場合には、処理の順番は関係ありません。

以下に示すのは、アスリートの検索タイプを分類する検索語ルールの例です。

| ルール番号 | ルールタイプ | 一致 | 分類を設定 | 設定値 |
|---|---|---|---|---|
| 1 | Contains | カウボーイズ | 検索タイプ | チーム |
| 2 | Contains | ファンタジー | 検索タイプ | ファンタジー |
| 3 | Contains | Romo | 検索タイプ | プレーヤー |

ユーザーが「*`Cowboys fantasy Tony Romo`*」を検索すると、「分類を設定」列に表示する「最後に指定した分類」と一致するため、*`Player`*」が分類されます。

同じように、以下の検索語についてルールを 2 つ設定している場合を考えます。

| ルール番号 | ルールタイプ | 一致 | 分類を設定 | 設定値 |
|---|---|---|---|---|
| 1 | Contains | カウボーイズ | 市区町村 | Dallas |
| 2 | Contains | ブロンコス | 市区町村 | Denver |

ユーザーが&#x200B;*`Cowboys vs. Broncos`* を検索すると、ルールビルダーによってルールの一致に競合が発見され、この検索では 2 番目のルールの分類（Denver）が適用されます。

## ルールセットに対する分類ルールの追加 {#add-classification-to-rule-set}

<!-- 

t_classification_rule.xml

 -->

分類ルールを追加または編集する方法について手順を説明します。

分類に条件を対応させることによってルールを追加し、そのアクションを指定します。

>[!NOTE]
>
>この手順では、ルールを 1 つ以上のレポートスイートに適用する必要があります。ルールセットあたりのルール数に制限はありませんが、500 ～ 1000 件にすることをお勧めします。ルールが 100 以上ある場合には、[下位分類](/help/components/c-classifications2/c-sub-classifications.md)を使ってルールセットを簡素化する方法の検討が必要です。

1. [分類ルールセットを作成します](/help/components/c-classifications2/crb/classification-rule-set.md)。
1. On the rule set page, click **[!UICONTROL Add Rule]**.

   ![](assets/add_rule.png)

1. Next to **[!UICONTROL Report Suites]**, click **[!UICONTROL Add Suites]** to specify one or more report suites to assign to this rule set.

   ページが **[!UICONTROL Select Report Suites]** 表示されます。

   >[!NOTE]
   レポートスイートは、次の条件を満たした場合 *`only`* このページに表示されます。

   * The report suites have at least one classification defined for that variable in [!UICONTROL Admin Tools].
   (See *`Variable`* in [Classification Rule Sets](/help/components/c-classifications2/crb/classification-rule-set.md) for an explanation about this prerequisite.)

   * You selected the report suite on the **[!UICONTROL Available Report Suites]** page, which displays after you click [Add Rule Set](/help/components/c-classifications2/crb/classification-rule-set.md) to create the rule set.


1. 既存の値を上書きするかどうかを指定します。

   | **ルールによって既存の値は上書きされます** | （デフォルト設定）インポーター（SAINT）を使用してアップロードされた分類を含む、既存の分類キーを常に上書きします。 |
   |---|---|
   | **ルールによって未設定の値のみが上書きされます** | 空欄（未設定）のセルにのみ記入します。既存の分類は、変更されません。 |

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

分類ルールまたはルールセットをテストする方法について手順を説明します。テストを実行すると、セット内のすべてのルールがチェックされます。

1. [分類ルールセットを作成します](/help/components/c-classifications2/crb/classification-rule-set.md)。
1. で、ルー [!UICONTROL Classification Rule Builder]ルセット名をクリックします。
1. ルールセットがレポートスイートに関連付けられていることを確認します。
1. On the rule editor, click **[!UICONTROL Test Rule Set]**.

   ![手順の結果](assets/classification_test_rule_set.png)

1. Type or paste test keys in the [!UICONTROL Sample Keys] field.

   サンプルキーには以下が含まれています。

   * トラッキングコード
   * 検索キーワードまたは語句
   詳しくは、[分類ルールの正規表現](/help/components/c-classifications2/crb/classification-quickstart-rules.md)を参照してください。
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

   このオプションの定義については、[ルールページ](/help/components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529)を参照してください。
