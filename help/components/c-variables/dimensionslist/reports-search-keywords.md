---
description: 検索キーワードの分類を表示します。
seo-description: 検索キーワードの分類を表示します。
seo-title: 検索キーワード
solution: Analytics
title: 検索キーワード
topic: レポート
uuid: db9d477b- b711-4b93-9c25-3aem5f2ace6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 検索キーワード

検索キーワードの分類を表示します。

**検索キーワード - すべて**：訪問者がサイトを見つけた時に使用した検索キーワードの詳細を示します。リスト上部にある列見出しをクリックすると、ページビュー数または検索キーワード順にリストを並べ替えることができます。検索キーワードの隣にある虫眼鏡をクリックすると、サイトの検索結果を見ることができます。

**検索キーワード - 有料**：訪問者がサイトを見つけたときに使用した各有料検索キーワードの分類を表示します。リスト上部にある列見出しをクリックすると、ページビュー数または検索キーワード順にリストを並べ替えることができます。検索キーワードの隣にある虫眼鏡をクリックすると、サイトの検索結果を見ることができます。

**検索キーワード - 自然**：訪問者がサイトを見つけたときに使用した各自然検索キーワードの分類を表示します。リスト上部にある列見出しをクリックすると、ページビュー数または検索キーワード順にリストを並べ替えることができます。検索キーワードの隣にある虫眼鏡をクリックすると、サイトの検索結果を見ることができます。

>[!IMPORTANT]
>
>有料検索と自然検索の場合、検索エンジンはリファラーの一部として検索キーワードを提供しなくなりました。その結果、Google（または Bing、Yahoo）ドメインは常に検索として分類されます。アドビでは、（キーワードがなくても）リファラーの形式と内容に基づいてそれが検索の結果であることを認識できるので、検索は「キーワードなし」としてカウントされます。[詳細情報...](https://helpx.adobe.com/analytics/kb/keyword-unavailable.html)

## 配分、有効期限および特別な値 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 指標配分 </td> 
   <td colname="col2"> <p>元の値（デフォルト） </p> <p> 線形に変更できます。 </p> </td> 
   <td colname="col3"> 最新（指標の線形バージョンを使用して線形に変更可能） </td> 
   <td colname="col4"> <p>元の値（デフォルト） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 有効期限 </td> 
   <td colname="col2"> 訪問 - 短縮可能ですが、延長はできません。 </td> 
   <td colname="col3"> 訪問 </td> 
   <td colname="col4"> 訪問 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 値の制限 </td> 
   <td colname="col2"> 無制限（今後のリリースで変更される可能性があります） </td> 
   <td colname="col3"> 無制限（今後のリリースで変更される可能性があります） </td> 
   <td colname="col4"> なし </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特別な値 </td> 
   <td colname="col2"> <p>「なし」：訪問中にキーワードがなかったサイト全体での合計。 </p> 「キーワードを使用できません」は、検索からキーワードが削除された検索で、データコレクションに送信されません。これは、一般に、顧客が Google アカウントにサインインしている場合に発生します。有料検索と自然検索に適用されます。 </td> 
   <td colname="col3"> （低トラフィック）は、受け取るトラフィックが少量でレポートされない、最初の 500,000 件を超過した値を表します。 </td> 
   <td colname="col4"> <p> 空 - 「なし」と同じです。訪問中にキーワードがなかったサイト全体での合計。 </p> <p>「キーワードを使用できません」は、検索からキーワードが削除された検索で、データコレクションに送信されません。これは、一般に、顧客が Google アカウントにサインインしている場合に発生します。有料検索と自然検索に適用されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## レポート履歴 {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| 日付 | 変更 |
|---|---|
| 2014 年 1 月 16 日 | data warehouse が Reports &amp; Analytics で使用されるロジックと一致するように更新されました。これまで、検索キーワードは訪問間で保持されませんでした。 |

