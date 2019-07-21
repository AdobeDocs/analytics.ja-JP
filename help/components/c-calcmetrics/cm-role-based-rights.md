---
description: 計算指標の権限は、管理者レベルのユーザーと管理者以外のユーザーとで異なります。
seo-description: 計算指標の権限は、管理者レベルのユーザーと管理者以外のユーザーとで異なります。
seo-title: 計算指標に基づく権限の計算
title: 計算指標に基づく権限の計算
uuid: 7c14d32d-370c-4afa-8f80-5bbd8fc12ec7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 計算指標:役割ベースの権限

計算指標の権限は、管理者レベルのユーザーと管理者以外のユーザーとで異なります。

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> 次に、 </th> 
   <th colname="col2" class="entry"> 共有 </th> 
   <th colname="col3" class="entry"> 表示/管理 </th> 
   <th colname="col4" class="entry"> 承認 </th> 
   <th colname="col5" class="entry"> 適用 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>管理者レベルユーザー</b> </td> 
   <td colname="col02"> 管理者は、計算指標を作成できるだけでなく、<a href="https://marketing.adobe.com/resources/help/en_US/reference/groups.html" format="https" scope="external">グループ</a>を作成して、計算指標を作成するユーザーの権限を制限できます。 </td> 
   <td colname="col2"> 会社全体、ユーザーグループおよび個人ユーザーと共有できます。 </td> 
   <td colname="col3"> <span class="keyword"> [!UACROL Reports&amp; Analytics] </span>:表示/編集/削除などが可能です。表示／編集／削除などが可能です。 <p> <span class="keyword">Ad Hoc Analysis</span> および <span class="keyword">Report Builder</span>：ユーザー自身の計算指標と他のユーザーと共有している計算指標の表示／編集／削除などが可能です。 </p> </td> 
   <td colname="col4"> 計算指標を正規の指標として承認できます。 </td> 
   <td colname="col5"> 組織全体ですべての計算指標を適用できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>非管理者レベルユーザー</b> </td> 
   <td colname="col02"> デフォルトでは、ユーザーは計算指標を作成できます。ただし、管理者によってその権限が制限されることがあります。 </td> 
   <td colname="col2"> 個人ユーザーとのみ共有できます。 </td> 
   <td colname="col3"> 自身の計算指標に限り、表示／編集／削除などが可能です。 <p>管理者以外のユーザーが共有された指標を表示するには、すべてのコンポーネントイベントに対するアクセス権が必要です（管理コンソールにおける権限は引き続き適用されます）。 </p> <p>ダッシュボードまたは予定レポートを管理者以外のユーザーと共有しており、そのユーザーが他のユーザーと指標を共有していない場合は、指標が適用された状態でレポートが実行されます（イベントを表示する権限がそのユーザーに割り当てられていることを前提とします）。ただし、定義を表示したり、指標を編集したりすることはできません。 </p> </td> 
   <td colname="col4"> 承認済みの計算指標のみを使用できます。承認としてマークすることはできません。 </td> 
   <td colname="col5"> 自身の計算指標と他のユーザーと共有しているセグメントを適用できます。 </td> 
  </tr> 
 </tbody> 
</table>

