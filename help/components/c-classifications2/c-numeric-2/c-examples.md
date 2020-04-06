---
description: 数値2分類のインポートに関するガイダンスを提供する例です。
subtopic: Classifications
title: 例
topic: Admin tools
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 例

数値2分類のインポートに関するガイダンスを提供する例です。

<!-- 

c_example_1__rate.xml

 -->

この場合、マネージャーで分類を作成し、1 [!UICONTROL Classification Conversion] 月の値をインポートします。

| キー | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product 2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | 売上高 | 売上高 |
| 2010/01/01 - 2010/01/31 | 売上高 | 売上高 |

1 月の Product1 のコストは売上高の 20％（`~MyCost^~value~` に表示）で、Product2 のコストは売上高の 30％でした。新しい行をインポートするので、`~MyCost^~id~` は空にします。

## 結果 {#section_E0569289C9B34C479C7D2CD9ECBF866E}

レポートの出力例を次に示します。

期間：2010年1月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product 1 | $10,000.23 | $2000.05 |
| Product 2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| キー | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product 2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product 1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product 2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | 売上高 | 売上高 |
| 2010/01/01 - 2010/01/31 | 売上高 | 売上高 |
| 2010/02/01 - 2010/02/28 | 売上高 | 売上高 |
| 2010/02/01 - 2010/02/28 | 売上高 | 売上高 |

2 月のユーザー側の Product1 のコストは売上高の 15％に減少し、Product2 は売上高の 25％に減少しました。

## 結果 {#section_23DF5353AC1B478C88647F222703352C}

レポートの出力例を次に示します。

期間：2010年1月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product 1 | $10,000.23 | $2000.05 |
| Product 2 | $9,000.04 | $2700.01 |

期間：2010年2月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product 1 | $15,500.75 | $2325.11 |
| Product 2 | $12,300.52 | $3075.13 |

期間：2010年1月1日～2010年2月28日

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product 1 | $25,500.98 | $4325.16 |
| Product 2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

したがって、次のデータをインポートします。

| キー | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product 2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 特定日 | なし |
| 2010/03/01 - 2010/03/31 | 特定日 | なし |

## 結果 {#section_674B57ADB8284B878F9E670038C31464}

レポートの出力例を次に示します。

期間：2010年3月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product 1 | $11,023.75 | $3000.00 |
| Product 2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

この例では、1月のProduct1に$500の配送料を追加し、2月に$600の配送料を追加します。

| キー | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product 1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product 1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product 1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | 売上高 | 売上高 |
| 2010/01/01 - 2010/01/31 | 特定日 | なし |
| 2010/02/01 - 2010/01/31 | 売上高 | 売上高 |
| 2010/02/01 - 2010/01/31 | 特定日 | なし |

以前にインポートされた行にはIDが付いており、新しいコストではないことを示します。

## 結果 {#section_2096084176614B9AA60F97D5853CB9EA}

レポートの出力例を次に示します。

期間：2010年1月

レポート：製品

| 製品 | 売上高 | MyCost |
|---|---|---|
| Product 1 | $10,000.23 | $2500.05 |

>[!NOTE]この機能は、上級のユーザーが概算値の計算に使用するものです。結果のデータは、正確な値として使用しないでください。

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

次に例を示します。

| キー | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 購入回数 | 購入回数 |

## 結果 {#section_39E24ECCC3B34C9AADC25572662750E5}

レポートの出力例を次に示します。

期間：2010年3月

レポート：製品（ページ別）

| 製品（ページ別） | 注文件数 | MyCost |
|---|---|---|
| Product 1 | 1000 | $1000.00 |
| ホームページ | 600 | $600 |
| 買い物かご | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| キー | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product 2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 特定日 | なし |
| 2010/03/01 - 2010/03/31 | 特定日 | なし |

## 結果 {#section_7F5F5970077D4E14A5DC91495E23540D}

レポートの出力例を次に示します。

期間：2010年3月

レポート：製品（ページ別）

| 製品（ページ別） | 注文件数 | MyCost |
|---|---|---|
| Product 1 | 1000 | $3000.00 |
| ホームページ | 600 | 0 |
| 買い物かご | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

この場合、次のデータをインポートします。

| キー | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product 2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 特定日 | 売上高 |
| 2010/03/01 - 2010/03/31 | 特定日 | 売上高 |

## 結果 {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

レポートの出力例を次に示します。

期間：2010年3月

レポート：製品（ページ別）

| 製品（ページ別） | 注文件数 | MyCost |
|---|---|---|
| Product 1 | 1000 | $3000.00 |
| ホームページ | 600 | $1800.00 |
| 買い物かご | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

この場合、次のファイルデータを読み込みます。

| キー | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product 1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 購入回数 | 売上高 |

## 結果 {#section_6E2604D9A3B0455585EFF0F80FF54127}

レポートの出力例を次に示します。

期間：2010年3月

レポート：製品（ページ別）

| 製品（ページ別） | 注文件数 | MyCost |
|---|---|---|
| Product 1 | 1000 | $3000.00 |
| ホームページ | 600 | $1,000.00 |
| 買い物かご | 400 | $2,000.00 |

