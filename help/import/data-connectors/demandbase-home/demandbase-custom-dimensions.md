---
description: アドビ統合ウィザードの手順4で指定できる、オプションのディメンション識別子を示します。
seo-description: アドビ統合ウィザードの手順4で指定できる、オプションのディメンション識別子を示します。
seo-title: Demandbaseカスタムディメンション
title: Demandbaseカスタムディメンション
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Demandbaseカスタムディメンション{#demandbase-custom-dimensions}

アドビ統合ウィザードの手順4で指定できる、オプションのディメンション識別子を示します。

ウィザードに入力する正確なAPI IDが不明な場合は、Demandbaseの担当者にお問い合わせください。

>[!IMPORTANT]
>
>IPアドレスをカスタムディメンションとして含めないことを強くお勧めします。 ユニーク値の数が非常に多いと、レポートでパフォーマンスの問題が発生する可能性があります。 また、IPアドレスは、Adobe Data Warehouseレポートを通じて、レポートオプションとして既に提供されています。

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
   <td colname="col3"> 識別された組織がISPとして分類されているかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> マーケティングエイリアス </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> 広告、メッセージ、マーケティングコピーで使用する組織名（32文字以下）のクリーニングまたは短縮。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アカウント監視タグ </td> 
   <td colname="col2"> watch_list (custom) </td> 
   <td colname="col3">API応答データに追加できる、クライアントによって定義されるタグの無制限のセット（組織別）。 <p><b>例</b>:q4 targetという名前の監視タグがある場合、APIフィールドは </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> 組織がFortune 1000リストに含まれているかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> フォーブス2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> 組織がForbes 2000リストにあるかどうかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 従業員数 </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> その組織で雇用されている人の数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年間販売 </td> 
   <td colname="col2"> annual_sales </td> 
   <td colname="col3"> 公共団体の場合、年間の売上高は、会社が報告したすべての地域のグローバルHQの公開記録に基づきます。 非公開の組織では、年間売上高数のコンセンサス見積もりに基づいています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 電話番号 </td> 
   <td colname="col2"> 電話 </td> 
   <td colname="col3"> 識別された組織の電話番号。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 住所 </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> 識別された組織の住所。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 市区町村 </td> 
   <td colname="col2"> 都市 </td> 
   <td colname="col3"> 識別された組織の市区町村。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 都道府県 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 識別された組織の状態。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国コード </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> 識別された組織のISO 2文字の国コード。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国名 </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> 識別された組織の国の文字列値の国名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 郵便番号 </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> 識別された組織の国/都道府県の郵便番号。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Web サイト </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> 識別された組織が使用するURL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 株券 </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> 特定された組織が公開取引された場合は、株価ティッカー。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プライマリSICコード </td> 
   <td colname="col2"> primary_sic </td> 
   <td colname="col3"> 識別された組織に割り当てられたコンセンサスSICコード。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 緯度 </td> 
   <td colname="col2"> 緯度 </td> 
   <td colname="col3"> 識別された組織の場所の緯度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 経度 </td> 
   <td colname="col2"> 経度 </td> 
   <td colname="col3"> 識別された組織の場所の経度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> トラフィック </td> 
   <td colname="col2"> 交通 </td> 
   <td colname="col3"> 低、中、高または非常に高いと推定されるWebサイトトラフィックの量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> 特定した会社が主に他の企業に販売していることを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> 識別された会社が主に消費者または個人に販売することを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 技術インサイト </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 広告、メッセージ、マーケティングコピーのターゲット設定やカスタマイズのために、カテゴリ、ベンダ、製品を通じて顧客が定義する最大75の技術カテゴリ。 </td> 
  </tr> 
 </tbody> 
</table>

