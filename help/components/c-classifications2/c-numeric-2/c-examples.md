---
description: 以下の例で、数値 2 分類のインポートについて説明します。
seo-description: 以下の例で、数値 2 分類のインポートについて説明します。
seo-title: 例
solution: Analytics
subtopic: '分類      '
title: 例
topic: 管理ツール
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 例

以下の例で、数値 2 分類のインポートについて説明します。

<!-- 

c_example_1__rate.xml

 -->

ここでは、[!UICONTROL 分類変換]マネージャーで分類を作成済みで、以下に示す 1 月の値をインポートするとします。

| Key | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |

In January, Product1 had a cost of 20% of its revenue (shown in `~MyCost^~value~`) and Product2 had a cost of 30% of its revenue. Because you are importing a new row, `~MyCost^~id~` is blank.

## 結果 {#section_E0569289C9B34C479C7D2CD9ECBF866E}

レポートからの出力の例を次に示します。

期間：2010 年 1 月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| Key | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |

2 月のユーザー側の Product1 のコストは売上高の 15％に減少し、Product2 は売上高の 25％に減少しました。

## 結果 {#section_23DF5353AC1B478C88647F222703352C}

レポートからの出力の例を次に示します。

期間：2010 年 1 月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

期間：2010 年 2 月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product1 | $15,500.75 | $2325.11 |
| Product2 | $12,300.52 | $3075.13 |

期間：2010 年 1 月 1 日～2010 年 2 月 28 日

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product1 | $25,500.98 | $4325.16 |
| Product2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

したがって、次のデータをインポートします。

| Key | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## 結果 {#section_674B57ADB8284B878F9E670038C31464}

レポートからの出力の例を次に示します。

期間：2010 年 3 月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product1 | $11,023.75 | $3000.00 |
| Product2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

この例では、Product1 の 1 月のデータに $500 の配送料を追加し、2 月のデータに $600 の配送料を追加します。

| Key | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | fixed | none |
| 2010/02/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/01/31 | fixed | none |

以前にインポートした行には ID が表示され、これらの行が新しいコストではないことがわかります。

## 結果 {#section_2096084176614B9AA60F97D5853CB9EA}

レポートからの出力の例を次に示します。

期間：2010 年 1 月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2500.05 |

>[!NOTE]
>
>この機能は、上級ユーザーが値を概算するために使用します。結果のデータは、正確な値として使用しないでください。

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

次に例を示します。

| Key | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | order |

## 結果 {#section_39E24ECCC3B34C9AADC25572662750E5}

レポートからの出力の例を次に示します。

期間：2010 年 3 月

レポート：製品（ページ別）

| 製品（ページ別） | 注文件数 | MyCost |
|---|---|---|
| Product1 | 1000 | $1000.00 |
| ホームページ | 600 | $600 |
| 買い物かご | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| Key | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## 結果 {#section_7F5F5970077D4E14A5DC91495E23540D}

レポートからの出力の例を次に示します。

期間：2010 年 3 月

レポート：製品（ページ別）

| 製品（ページ別） | 注文件数 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| ホームページ | 600 | 0 |
| 買い物かご | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

ここでは、次のデータをインポートします。

| Key | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | revenue |
| 2010/03/01 - 2010/03/31 | fixed | revenue |

## 結果 {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

レポートからの出力の例を次に示します。

期間：2010 年 3 月

レポート：製品（ページ別）

| 製品（ページ別） | 注文件数 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| ホームページ | 600 | $1800.00 |
| 買い物かご | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

次のファイルデータをインポートします。

| Key | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | revenue |

## 結果 {#section_6E2604D9A3B0455585EFF0F80FF54127}

レポートからの出力の例を次に示します。

期間：2010 年 3 月

レポート：製品（ページ別）

| 製品（ページ別） | 注文件数 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| ホームページ | 600 | $1,000.00 |
| 買い物かご | 400 | $2,000.00 |

