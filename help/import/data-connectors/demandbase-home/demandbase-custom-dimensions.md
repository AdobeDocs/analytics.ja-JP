---
description: アドビ統合ウィザードの手順 4 で指定できる、オプションのディメンション識別子を示します。
title: Demandbase カスタムディメンション
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 100%

---


# Demandbase カスタムディメンション {#demandbase-custom-dimensions}

アドビ統合ウィザードの手順 4 で指定できる、オプションのディメンション識別子を示します。

ウィザードに入力する正確な API ID が不明な場合は、Demandbase の担当者にお問い合わせください。

>[!IMPORTANT]
>
>IP アドレスをカスタムディメンションに含めないことを強くお勧めします。ユニーク値の数が非常に多いと、レポートでパフォーマンスの問題が発生する可能性があります。また、IP アドレスは、Adobe Data Warehouse レポートを通じて、レポートオプションとして既に提供されています。

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディメンション </th> 
   <th colname="col2" class="entry"> API ID </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> isp </td> 
   <td colname="col3"> 特定された組織が ISP として分類されているかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> マーケティングエイリアス </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> 広告、メッセージ、マーケティングコピーで使用するクリーンアップされた組織名または組織名の短縮形（32 文字以下）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アカウント監視タグ </td> 
   <td colname="col2"> watch_list（カスタム） </td> 
   <td colname="col3">API 応答データに追加でき、クライアントによって定義されるタグの無制限のセット（組織別）。 <p><b>例</b>：Q4 Target という名前の監視タグがある場合、APIアプリストアフィールドは次のようになります。 </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> 組織が Fortune 1000 リストに含まれているかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> 組織が Forbes 2000 リストに含まれているかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 従業員数 </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> その組織で雇用されている人の数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年間売上高 </td> 
   <td colname="col2"> annual_sales </td> 
   <td colname="col3"> 公共団体の場合、年間の売上高は、すべての地域のグローバル HQ に対して会社が報告した公開記録に基づきます。非公開会社では、年間売上高数のコンセンサス見積もりに基づいています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 電話番号 </td> 
   <td colname="col2"> phone </td> 
   <td colname="col3"> 特定された組織の電話番号。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 住所 </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> 特定された組織の住所。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 市区町村 </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> 特定された組織の市区町村。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 都道府県 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 特定された組織の都道府県。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国コード </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> 特定された組織の ISO 国コード（2 文字）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国名 </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> 特定された組織の国を表す文字列値の国名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 郵便番号 </td> 
   <td colname="col2"> 郵便番号 </td> 
   <td colname="col3"> 特定された組織の国／都道府県の郵便番号。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Web サイト </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> 特定された組織が使用する URL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 株価情報 </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> 特定された組織が公開取引された場合は、株価情報。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プライマリ SIC コード </td> 
   <td colname="col2"> primary_sic </td> 
   <td colname="col3"> 特定された組織に割り当てられたコンセンサス SIC コード。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 緯度 </td> 
   <td colname="col2"> latitude </td> 
   <td colname="col3"> 特定された組織の所在地の緯度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 経度 </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> 特定された組織の所在地の経度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トラフィック </td> 
   <td colname="col2"> traffic </td> 
   <td colname="col3"> Web サイトトラフィックの量。「低」、「中」、「高」、または「非常に高い」として見積もられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> 特定された会社主に他の企業相手に販売していることを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> 特定された会社が主に消費者または個人相手に販売していることを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 技術インサイト </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 広告、メッセージ、マーケティングコピーのターゲティングやカスタマイズに使用するため、カテゴリ、ベンダー、製品を通じて顧客が定義する最大 75 の技術カテゴリ。 </td> 
  </tr> 
 </tbody> 
</table>

